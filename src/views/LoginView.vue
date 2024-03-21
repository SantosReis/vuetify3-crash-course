<script setup lang="ts">
import { ref } from 'vue'
const form = ref({
  email: '',
  password: '',
  remember: false,
})

function submit() {
  alert(JSON.stringify(form.value))
}
</script>
<template>
  <v-sheet class="mx-auto" width="300">
    <v-form @submit.prevent="submit">
      <v-text-field
        variant="solo"
        prepend-inner-icon="mdi-email"
        v-model="form.email"
        label="Email"
      ></v-text-field>

      <v-text-field
        variant="solo"
        prepend-inner-icon="mdi-key"
        v-model="form.password"
        label="Password"
      ></v-text-field>

      <v-checkbox
        v-model="form.remember"
        label="Remember me"
        color="red"
        hide-details
      ></v-checkbox>

      <v-btn color="red-darken-1" class="mt-2" type="submit" block
        >Submit</v-btn
      >
    </v-form>
  </v-sheet>
</template>
