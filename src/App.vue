<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <v-app>
    <v-toolbar density="compact">
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>
        <RouterLink to="/"> Vuefify </RouterLink>
      </v-toolbar-title>

      <v-spacer></v-spacer>
      <v-btn
        to="/login"
        variant="outlined"
        size="x-small"
        color="pink-darken-4"
        text="Login"
      ></v-btn>
    </v-toolbar>

    <v-main>
      <v-fade-transition>
        <RouterView />
      </v-fade-transition>
    </v-main>
  </v-app>
</template>
