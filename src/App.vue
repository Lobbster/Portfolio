<template>
  <v-app>
    <Drawer />
    <NavBar />
    <v-main class="grey lighten-4">
      <v-card elevation="3">
        <Bio />
      </v-card>
      <Project />
    </v-main>
    <Snackbar />
  </v-app>
</template>

<script>
import NavBar from "@/components/NavBar.vue";
import Drawer from "@/components/Drawer.vue";
import Bio from "@/components/Bio.vue";
import Project from "@/components/Project.vue";
import Snackbar from "@/components/Snackbar.vue";

export default {
  name: "App",

  components: {
    NavBar,
    Drawer,
    Bio,
    Project,
    Snackbar,
  },
};
</script>
