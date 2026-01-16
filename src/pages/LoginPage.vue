<template>
  <q-page class="bg-black text-white flex flex-center">
    <div class="row full-width" style="max-width: 1100px; min-height: 80vh;">
      <!-- Left Side: Image/Info (Hide on small screens) -->
      <div class="col-md-6 gt-sm flex flex-center">
        <div class="q-pa-xl">
           <div class="text-h2 text-weight-bolder text-white q-mb-md" style="line-height: 1.1;">
             Welcome Back to EduManager
           </div>
           <p class="text-h6 text-grey-5 text-weight-regular q-mb-xl">
             Log in to manage your institute, track attendance, and analyze performance with our all-in-one platform.
           </p>
           <q-img 
              src="~assets/hero-dark.png" 
              class="rounded-borders shadow-20 glowing-border"
              style="border-radius: 20px; opacity: 0.8;"
            />
        </div>
      </div>

      <!-- Right Side: Login Form -->
      <div class="col-12 col-md-6 flex flex-center">
        <q-card class="bg-grey-10 text-white q-pa-lg shadow-10 border-grey-9" style="width: 100%; max-width: 450px; border-radius: 16px; border: 1px solid #333;">
          <q-card-section>
            <div class="text-h4 text-weight-bold text-center q-mb-lg">Login</div>
          </q-card-section>

          <q-card-section>
            <q-form @submit="handleLogin" class="q-gutter-md">
              <q-input
                filled
                dark
                v-model="email"
                label="Email"
                type="email"
                lazy-rules
                :rules="[ val => val && val.length > 0 || 'Please type something']"
              >
                <template v-slot:prepend>
                  <q-icon name="email" color="grey-5" />
                </template>
              </q-input>

              <q-input
                filled
                dark
                v-model="password"
                label="Password"
                type="password"
                lazy-rules
                :rules="[ val => val && val.length > 0 || 'Please type your password']"
              >
                <template v-slot:prepend>
                  <q-icon name="lock" color="grey-5" />
                </template>
              </q-input>

              <div class="row justify-between items-center q-mt-sm">
                <q-checkbox dark v-model="rememberMe" label="Remember me" color="white" />
                <a href="#" class="text-grey-5" style="text-decoration: none;">Forgot Password?</a>
              </div>

              <div class="q-mt-lg">
                <q-btn 
                  unelevated 
                  color="white" 
                  text-color="black" 
                  label="Login" 
                  type="submit" 
                  class="full-width text-weight-bold" 
                  size="lg"
                  no-caps
                  :loading="loading"
                />
              </div>
            </q-form>
          </q-card-section>

          <q-card-section class="text-center q-mt-md">
            <div class="text-grey-5">
              Don't have an account? 
              <router-link to="/register" class="text-white text-weight-bold" style="text-decoration: none;">Register</router-link>
            </div>
          </q-card-section>
        </q-card>
      </div>
    </div>
  </q-page>
</template>

<script setup>
import { ref } from 'vue'
import { useRouter } from 'vue-router'
import { useQuasar } from 'quasar'
import { supabase } from 'boot/supabase'

const $q = useQuasar()
const router = useRouter()

const email = ref('')
const password = ref('')
const rememberMe = ref(false)
const loading = ref(false)

const handleLogin = async () => {
  loading.value = true
  
  const { data, error } = await supabase.auth.signInWithPassword({
    email: email.value,
    password: password.value,
  })

  loading.value = false

  if (error) {
    $q.notify({
      color: 'red-5',
      textColor: 'white',
      icon: 'warning',
      message: error.message
    })
  } else {
    $q.notify({
      color: 'green-4',
      textColor: 'white',
      icon: 'check_circle',
      message: 'Logged in successfully'
    })
    router.push('/')
  }
}
</script>

<style scoped>
.glowing-border {
  box-shadow: 0 0 20px rgba(255, 255, 255, 0.05);
}
</style>
