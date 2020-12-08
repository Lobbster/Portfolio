<template>
  <v-snackbar v-model="snackbar" color="blue" :timeout="timeout">
    {{ text }}
    <template v-slot:action="{ attrs }">
      <v-btn color="white" text v-bind="attrs" @click="snackbar = false">
        Close
      </v-btn>
    </template>
  </v-snackbar>
</template>

<script>
import { bus } from "@/main";

export default {
  data: () => ({
    snackbar: false,
    text: "Email Copied to Clipboard 😎",
    timeout: 3000
  }),

  mounted() {
    bus.$on("copiedEmail", data => {
      this.snackbar = data;
    });
  }
};
</script>
