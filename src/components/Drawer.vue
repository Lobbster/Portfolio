<template>
  <v-navigation-drawer v-model="drawer" app>
    <v-list nav dense>
      <v-list-item-group v-model="group">
        <!-- Start -->
        <v-list-item>
          <!-- Icon -->
          <v-list-item-icon @click="scroll">
            <v-icon>mdi-bomb</v-icon>
          </v-list-item-icon>
          <!-- Name -->
          <v-list-item-content>
            <v-list-item-title>Work </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <!-- End -->
        <!-- Start -->
        <v-list-item
          href="https://www.linkedin.com/in/tom-hendrikz/"
          target="_blank"
        >
          <!-- Icon -->
          <v-list-item-icon @click="$vuetify.goTo(target, options)">
            <v-icon>mdi-linkedin </v-icon>
          </v-list-item-icon>
          <!-- Name -->
          <v-list-item-content>
            <v-list-item-title>LinkedIn</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <!-- End -->

        <!-- Start -->
        <v-list-item>
          <!-- Icon -->
          <v-list-item-icon>
            <v-icon>mdi-email-plus </v-icon>
          </v-list-item-icon>
          <!-- Name -->
          <v-list-item-content v-clipboard:copy="email" @click="copiedEmail()">
            <v-list-item-title>Contact </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <!-- End -->
      </v-list-item-group>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
import { bus } from "@/main";
export default {
  data: () => ({
    email: "Thomashendrikz@Gmail.com",
    drawer: false,
    group: null,
  }),
  methods: {
    copiedEmail: function () {
      bus.$emit("copiedEmail", true);
    },
    scroll() {
      console.log("try to scroll");
      this.$vuetify.goTo(999);
    },
  },
  mounted() {
    bus.$on("changeDrawer", (data) => {
      this.drawer = data;
    });
  },
  watch: {
    group() {
      this.drawer = false;
    },
  },
};
</script>
