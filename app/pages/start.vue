<script lang="ts" setup>
  import { ref } from 'vue';

// Create a reactive variable to track the state of the drawer
const drawer = ref(false);

const tags = ref([
  'All', 'Photography', 'Meet', 'Excursion'
]);
</script>

<template>
  <v-app>

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
    <!-- Main -->
    <v-main style="background-color: white">
       <!-- Tags Area -->
      <v-container style="padding-top: 40px; padding-bottom: 40px;">
        <v-row class="tags-area" justify="left">
          <v-col v-for="(tag, index) in tags" :key="index" cols="auto">
            <v-chip class="ma-2" color="primary" text-color="white">
              {{ tag }}
            </v-chip>
          </v-col>
        </v-row>
      </v-container>

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
    


    
    
  </v-app>
</template>





<!-- 
App Bar
Tabs
Carousel
Form
    Form Inputs
    Button -->
