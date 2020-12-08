<template>
  <div class="project-container">
    <div v-for="(project, inx) in projects" :key="inx" class="pa-3">
      <v-card elevation="2" outlined max-width="800" class="mx-auto">
        <v-container class="pa-1">
          <v-row no-gutters>
            <!-- Top -->
            <v-col xs="12" sm="6">
              <v-img
                min-height="100%"
                class="rounded"
                :src="require('../assets/image/' + project.id + '.jpg')"
              ></v-img>
            </v-col>
            <!-- Bottom -->
            <v-col xs="12" sm="6">
              <v-list-item three-line>
                <v-list-item-content>
                  <div class="overline mb-4">
                    {{ project.topics }}
                  </div>
                  <v-list-item-title class="headline mb-1">
                    {{ project.nameOfProject }}
                  </v-list-item-title>
                  <v-list-item-subtitle>
                    {{ project.description }}
                  </v-list-item-subtitle>
                  <v-btn
                    outlined
                    rounded
                    text
                    class="mt-4"
                    :href="project.link"
                    target="_blank"
                  >
                    Behance
                  </v-btn>
                </v-list-item-content>
              </v-list-item>
            </v-col>
          </v-row>
        </v-container>
      </v-card>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    projects: [
      {
        nameOfProject: "Bemo",
        id: "bemo",
        link:
          "https://www.behance.net/gallery/106761399/Bemo-App-UX-Case-Study",
        image: "../assets/image/bemo.jpg",
        topics: "UX / CASE STUDY / APP DESIGN",
        description: "Cool bemo app"
      },
      {
        nameOfProject: "VanORan",
        id: "van",
        link:
          "https://www.behance.net/gallery/106662673/New-Zealand-Rental-Car-Project",
        image: "../assets/image/van.jpg",
        topics: "UX / UI / WEB DESIGN",
        description:
          "VanORan is vehicle rental company based in New Zealand. This was a class project to exercise the use of jQuery."
      },
      {
        nameOfProject: "Edible Canterbury",
        id: "garden",
        link: "https://www.behance.net/gallery/109198249/Edible-Canterbury",
        image: "../assets/image/garden.jpg",
        topics: "UX / UI / WEB DESIGN",
        description:
          "Edible Canterbury was a class project aimed at designing and programming a WordPress template website. The website was programmed in PHP and used Tailwind for the styling."
      }
    ]
  })
};
</script>
