<script setup lang="ts">
import { ref } from 'vue'
const form = ref({
  email: '',
  password: '',
  remember: false,
})

const isLoading = ref(false)

function submit() {
  if (form.value.email === '') {
    return
  }

  isLoading.value = true

  setTimeout(() => {
    isLoading.value = false
  }, 2000)

  alert(JSON.stringify(form.value))
}

const rules = {
  required: (value: any) => !!value || 'Required.',
  email: (value: any) => {
    const pattern =
      /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
    return pattern.test(value) || 'Invalid e-mail.'
  },
}
</script>
<template>
  <v-container fluid>
    <v-row justify="center">
      <v-col md="4">
        <v-overlay :model-value="isLoading">
          <v-progress-circular v-if="isLoading" indeterminate color="white">
          </v-progress-circular>
        </v-overlay>

        <v-card class="pa-4 mx-auto" width="300">
          <v-card-title class="text-center">Login</v-card-title>
          <v-card-item>
            <v-form @submit.prevent="submit">
              <v-text-field
                variant="solo"
                prepend-inner-icon="mdi-email"
                :rules="[rules.required, rules.email]"
                v-model="form.email"
                label="Email"
              ></v-text-field>

              <v-text-field
                variant="solo"
                prepend-inner-icon="mdi-key"
                :rules="[rules.required]"
                v-model="form.password"
                label="Password"
              ></v-text-field>

              <v-checkbox
                v-model="form.remember"
                label="Remember me"
                color="red"
                hide-details
              ></v-checkbox>

              <v-btn
                color="red-darken-1 block"
                class="mt-2"
                type="submit"
                block
              >
                <span>Submit</span>
              </v-btn>
            </v-form>
          </v-card-item>

          <v-card-action>
            <div class="mx-4">
              <v-btn variant="outlined" block to="/register"> Register </v-btn>
            </div>
          </v-card-action>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>
