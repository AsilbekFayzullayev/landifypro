<template>
  <div>
    <v-app-bar app fixed class="navbar" clipped-right>
      <v-spacer></v-spacer>
      <h2 @click="$vuetify.goTo('#slider')">New</h2>
      <v-spacer></v-spacer>
      <v-app-bar-nav-icon class="barIcon" @click="clickBarIcon"></v-app-bar-nav-icon>
      <v-spacer></v-spacer>
      <div class="linkes">
        <span
          class="mx-2"
          :class="link.isActive ? 'linkss' : ''"
          v-for="link of links" :key="link.id"
          @click="borderBottom(link); $vuetify.goTo(link.goTo)"
        >
          {{ link.title }}
        </span>
      </div>
      <v-spacer></v-spacer>
      <div>
        <span><v-icon>mdi-facebook</v-icon></span>
      </div>
    </v-app-bar>

    <div class="linkClass pt-2" :class="drawer ? 'd-none' : 'd-block'">
      <p v-for="i of links" :key="i" class="text-center links" @click="clicked(i)">{{ i.title }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",
  data: () => ({
    links: [
      {id: 1, title: 'About Us', isActive: false, goTo: '#about'},
      {id: 2, title: 'Services', isActive: false, goTo: '#services'},
      {id: 3, title: 'Portfolio', isActive: false, goTo: '#portfolio'},
      {id: 3, title: 'Contact', isActive: false, goTo: '#contact'}
    ],
    drawer: true,
  }),
  methods: {
    borderBottom(link) {
      link.isActive = true
      this.links.forEach(l => {
        if (l.id !== link.id) {
          l.isActive = false
        }
      })
    },
    clickBarIcon() {
      this.drawer = false
    },
    clicked(item) {
      this.$vuetify.goTo(item.goTo)
      this.$store.dispatch('changeDrawer')
      this.drawer = true
    },
  }
}
</script>

<style lang="scss" scoped>
.navbar {
  background-color: white !important;
  box-shadow: none !important;
  border-bottom: 1px solid lavender;
  color: black;
}

.linkes {
  cursor: pointer;
}

.barIcon {
  display: none;
}

@media (max-width: 1024px) {
  .linkes {
    display: none;
  }
  .barIcon {
    display: block;
  }
}

.linkClass {
  position: fixed;
  top: 0;
  width: 100% !important;
  z-index: 1100;
  background-color: darkslategray;
  opacity: 0.9
}
.linkss{
  border-bottom: 2px solid black;
}
.links:hover {
  background-color: darkslategray;
  color: white;
  cursor: pointer;
}
</style>
