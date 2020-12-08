<template>
  <div>
    <v-app-bar app>
      <v-container>
        <v-row class="justify-center">
          <v-col lg="10" xl="8" class="d-flex justify-space-between">
            <div>
              <h4>Thomas Hendrikz</h4>
              <h5>UX/UI Designer</h5>
            </div>
            <div class="d-flex align-center">
              <v-tooltip bottom>
                <template v-slot:activator="{ on, attrs }">
                  <v-btn
                    @click="scroll()"
                    elevation="0"
                    v-bind="attrs"
                    v-on="on"
                    class="d-none d-md-flex"
                    >Work</v-btn
                  >
                </template>
                <span>My Projects</span>
              </v-tooltip>

              <v-tooltip bottom>
                <template v-slot:activator="{ on, attrs }"
                  >``
                  <v-btn
                    elevation="0"
                    class="mx-5 d-none d-md-flex"
                    v-bind="attrs"
                    v-on="on"
                    href="https://www.linkedin.com/in/tom-hendrikz/"
                    target="_blank"
                    >LinkedIn</v-btn
                  >
                </template>
                <span>Go to LinkedIn</span>
              </v-tooltip>

              <v-tooltip bottom>
                <template v-slot:activator="{ on, attrs }">
                  <v-btn
                    elevation="0"
                    class="d-none d-md-flex"
                    v-clipboard:copy="email"
                    v-bind="attrs"
                    v-on="on"
                    @click="copiedEmail()"
                    >Thomashendrikz@Gmail.com</v-btn
                  >
                </template>
                <span>Copy Email</span>
              </v-tooltip>
              <v-app-bar-nav-icon
                class="d-md-none"
                @click.stop="changeDrawer"
              ></v-app-bar-nav-icon>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </v-app-bar>
  </div>
</template>

<script>
import { bus } from "@/main";
export default {
  data: () => ({
    email: "Thomashendrikz@Gmail.com",
  }),
  methods: {
    changeDrawer: function() {
      bus.$emit("changeDrawer", !this.drawer);
    },
    copiedEmail: function() {
      bus.$emit("copiedEmail", true);
    },
    scroll() {
      this.$vuetify.goTo(340);
    },
  },
};
</script>
