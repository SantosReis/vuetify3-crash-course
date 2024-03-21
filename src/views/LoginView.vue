<script setup lang="ts">
import { ref } from 'vue'
const form = ref({
  email: '',
  password: '',
  remember: false,
})

const isLoading = ref(false)

function submit() {
  isLoading.value = true

  setTimeout(() => {
    isLoading.value = false
  }, 2000)

  alert(JSON.stringify(form.value))
}
</script>
<template>
  <v-container fluid>
    <v-card class="pa-4 mx-auto" width="300">
      <v-card-title class="text-center">Login</v-card-title>
      <v-card-item>
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

          <v-btn color="red-darken-1" class="mt-2" type="submit" block>
            <v-progress-circular v-if="isLoading" indeterminate color="white">
            </v-progress-circular>
            <span v-else>Submit</span>
          </v-btn>
        </v-form>
      </v-card-item>

      <v-card-action>
        <div class="mx-4">
          <v-btn block to="/register"> Register </v-btn>
        </div>
      </v-card-action>
    </v-card>
  </v-container>
</template>
