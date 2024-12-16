<script lang="ts" setup>
  import { ref } from 'vue';

// Create a reactive variable to track the state of the drawer
const drawer = ref(false);

const tags = ref([
  'All', 'Photography', 'Meet', 'Excursion','All', 'Photography', 'Meet', 'Excursion'
]);

</script>

<template >

    <!-- Navbar (AppBar) -->
    <v-app-bar class="custom-app-bar" style="background-color: #006CE4; padding-top: 20px;">
      <template v-slot:append>
        <v-btn icon="mdi-bell"></v-btn>
        <v-btn icon="mdi-email"></v-btn>
        <v-btn icon="mdi-account"></v-btn>
        <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      </template>
      <v-app-bar-title>Azamaza.com</v-app-bar-title>
    </v-app-bar>

    <!-- Navigation Drawer -->
    <v-navigation-drawer v-model="drawer" app right>
      <v-list>
        <v-list-item title="My Application" subtitle="Vuetify"></v-list-item>
        <v-divider></v-divider>
        <v-list-item link title="List Item 1"></v-list-item>
        <v-list-item link title="List Item 2"></v-list-item>
        <v-list-item link title="List Item 3"></v-list-item>
      </v-list>
    </v-navigation-drawer>
    
    <!-- Main (contains all other elements)-->
    <v-main class="bg-white ma-4">
      
      <!-- Tags Area -->
      <v-container>
        <v-sheet class="py-4 px-1">
          <v-chip-group
            selected-class="text-deep-purple-accent-4"
            mandatory
          >
            <v-chip
              prepend-icon="mdi-account-circle"
              v-for="tag in tags"
              :key="tag"
              :text="tag"
              variant="outlined"
            ></v-chip>
          </v-chip-group>
        </v-sheet>
      </v-container>

      <main-card>fff</main-card>
      <!-- Carousel-->
      <v-container>
        <v-carousel>
          <v-carousel-item
            src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
            cover
          ></v-carousel-item>

          <v-carousel-item
            src="https://cdn.vuetifyjs.com/images/cards/hotel.jpg"
            cover
          ></v-carousel-item>

          <v-carousel-item
            src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
            cover
          ></v-carousel-item>
        </v-carousel>
      </v-container>

      <!-- Text item-->
      <v-container>
        <h1 style="color: #006CE4;">Discounts. Connections. Freedom!</h1>
        <p class="text-secondary">Travel and meet, save and enjoy, rent, communicate, discover the world!</p>
      </v-container>
    </v-main>
    
    <!-- Footer -->
    <v-footer height="50" app>
        <v-container class="d-flex align-center justify-center">
            <p>Copyright {{ (new Date()).getFullYear() }} Azamaza.com All rights reserved.</p>
        </v-container>
    </v-footer>
</template>





<!-- 
App Bar
Tabs
Carousel
Form
    Form Inputs
    Button -->

