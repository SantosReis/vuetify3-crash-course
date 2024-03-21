<script setup lang="ts"></script>

<template>
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
</template>
