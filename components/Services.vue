<template>
  <div class="py-5">
    <!--our services text-->
    <v-row>
      <v-col cols="12" md="12" sm="12" class="mt-5 text-center">
        <h2>OUR SERVICES</h2>
      </v-col>
    </v-row>
    <!--our services-->
    <v-row>
      <v-col md="8" offset-md="2">
        <v-row>
          <v-col cols="12" sm="4" v-for="item of professions" :key="item.id" class="my-4 px-4">
            <v-icon color="black">{{ item.icon }}</v-icon>
            <span class="font-weight-bold">{{ item.title }}</span>
            <p class="text-center">{{ item.text }}</p>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
    <!--    image-->

    <v-parallax
      dark
      src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
      height="300"
    >
      <v-row style="height: 50%">
        <v-col md="6" offset-md="3">
          <v-card color="transparent">
            <v-carousel cycle hide-delimiters height="150">
              <v-carousel-item
                v-for="(i) in data"
                :key="i"
              >
                <v-row
                  class="fill-height"
                  align="center"
                  justify="center"
                >
                  <div class="display-3">
                    Slide {{ i }}
                  </div>
                </v-row>
              </v-carousel-item>
            </v-carousel>
          </v-card>
        </v-col>
      </v-row>
      <v-row style="height: 50%;background-color: aliceblue; opacity: 0.8;" >
        <v-col md="8" offset-md="2"  style="color: black">
          <v-row>
            <v-col  cols="12" md="6"  sm="6" class="text-left py-4">
              <h4>Our Client</h4>
              <p>At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium
                voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati et.</p>
            </v-col>
            <v-col cols="12" md="6" sm="6" class="py-4" >
              <v-card style="background-color: transparent;box-shadow: none">

                <v-carousel
                            cycle hide-delimiter-background :show-arrows="false"  height="120">
                  <v-carousel-item
                    v-for="(i) in data"
                    :key="i"
                  >
                    <v-row
                      class="fill-height"
                      align="center"
                      justify="center"
                      style="color: black!important"
                    >
                      <div class="display-3">
                        Slide {{ i }}
                      </div>
                    </v-row>
                  </v-carousel-item>
                </v-carousel>
              </v-card>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-parallax>
  </div>

</template>

<script>
export default {
  name: "Services",
  data: () => ({
    data: [
      'text 1', 'text2', 'text3', 'text4'
    ],
    professions: [
      {
        id: 1,
        icon: 'mdi-cloud',
        title: 'Web Design',
        text: '  sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud\n' +
          '          exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit\n' +
          '          in voluptate velit ut et voluptates repudiandae sint et molestiae non recusandae.\n' +
          ' '
      },
      {
        id: 2,
        icon: '\'mdi-cloud',
        title: 'Web Design2',
        text: '  sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud\n' +
          '          exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit\n' +
          '          in voluptate velit ut et voluptates repudiandae sint et molestiae non recusandae.\n' +
          ' '
      },
      {
        id: 3,
        icon: '\'mdi-telegram',
        title: 'Web Design3',
        text: '  sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud\n' +
          '          exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit\n' +
          '          in voluptate velit ut et voluptates repudiandae sint et molestiae non recusandae.\n' +
          ' '
      },
      {
        id: 4,
        icon: '\'mdi-cloud',
        title: 'Web Design4',
        text: '  sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud\n' +
          '          exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit\n' +
          '          in voluptate velit ut et voluptates repudiandae sint et molestiae non recusandae.\n' +
          ' '
      },
      {
        id: 5,
        icon: 'mdi-telegram',
        title: 'Web Design5',
        text: '  sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud\n' +
          '          exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit\n' +
          '          in voluptate velit ut et voluptates repudiandae sint et molestiae non recusandae.\n' +
          ' '
      },
      {
        id: 6,
        icon: '\'mdi-cloud',
        title: 'Web Design6',
        text: '  sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud\n' +
          '          exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit\n' +
          '          in voluptate velit ut et voluptates repudiandae sint et molestiae non recusandae.\n' +
          ' '
      }
    ]
  })

}
</script>

<style scoped>

</style>
