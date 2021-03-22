<template>
  <div class="py-5">
    <!-- contact us text -->
    <v-row>
      <v-col cols="12" md="12" sm="12" class="my-5 text-center">
        <h2>Contact Us</h2>
      </v-col>
    </v-row>

    <!-- Contact form -->

    <v-row>
      <v-col md="8" offset-md="2">
        <v-row>
          <v-col cols="12" md="4" sm="4" class="text-left">
            <h3>Support/Work Hours</h3>
            <span>Our support services are available
              </span>
            <p>10 Hours a day : + 123-456-789-890</p>
            <p style="opacity: 0.8;font-size: 15px"><span style="font-weight: bold">Monday-Friday:</span> 09am - 18pm
            </p>
            <p style="opacity: 0.8;font-size: 15px"><span style="font-weight: bold">Saturday:</span>09am - 1pm</p>
            <p style="opacity: 0.8;font-size: 15px"><span style="font-weight: bold">Sunday:</span>closed</p>
          </v-col>
          <v-col cols="12" md="8" sm="8" class="text-left">
            <h3>Get In Touch With Us</h3>
            <span>Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris
              nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit ut et voluptates repudiandae sint et molestiae non recusandae.
            </span>

            <v-row>
              <v-col class="mt-4">
                <span class="font-weight-bold">Name *</span>
                <v-text-field
                  v-model="formData.name"
                  :rules="nameRules"
                  outlined
                  dense
                  required
                ></v-text-field>
              </v-col>
            </v-row>
            <v-row>
              <v-col class="">
                <span class="font-weight-bold">Email *</span>
                <v-text-field
                  v-model="formData.email"
                  :rules="emailRules"
                  outlined
                  dense
                  required
                ></v-text-field>
              </v-col>
            </v-row>
            <v-row>
              <v-col class="">
                <span class="font-weight-bold">Subject *</span>
                <v-text-field
                  v-model="formData.subject"
                  outlined
                  dense
                ></v-text-field>
              </v-col>
            </v-row>
            <v-row>
              <v-col class="">
                <span class="font-weight-bold">Message *</span>
                <v-textarea
                  v-model="formData.message"
                  type="text"
                  outlined
                  dense
                ></v-textarea>
              </v-col>
            </v-row>

            <!-- send message btn -->
            <v-row>
              <v-col>
                <v-btn @click="sendMessageClick" color="white" class="border-none" elevation="0"
                       style="border: 2px solid black!important">
                  <v-icon dense small>mdi-message</v-icon>
                  Send Message
                </v-btn>
              </v-col>
            </v-row>
            <v-snackbar
              v-model="snackbar"
              :timeout="4000"
              :color="colorSnackbar"
            >
              {{ snackText }}

              <template v-slot:action="{ attrs }">
                <v-btn
                  color="white"
                  text
                  v-bind="attrs"
                  @click="snackbar = false"
                >
                  Close
                </v-btn>
              </template>
            </v-snackbar>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  name: "Contact",

  data: () => ({
    snackbar: false,
    snackText: '',
    colorSnackbar: '',
    nameRules: [
      v => !!v || '' +
        'required',
    ],
    emailRules: [
      v => /.+@.+/.test(v) || 'E-mail must be valid',
    ],
    formData: {
      name: '',
      email: '',
      subject: '',
      message: ''
    }
  }),
  methods: {
    async sendMessageClick() {
      this.snackbar = true
      const {name, email} = this.formData
      if (name === '' || email === '') {
        this.colorSnackbar = 'red'
        this.snackText = "Enter text !"
      } else {
        this.colorSnackbar = 'green'
        this.snackText = "Ok, data sent."
      }
    }
  }
}
</script>

<style scoped>

</style>
