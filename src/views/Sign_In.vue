<script setup>
import { ref, computed } from 'vue'
import Navbar from '@/components/Navbar.vue'

const name = ref('')
const email = ref('')
const password = ref('')
const agree = ref(false)

const isFormValid = computed(() => {
  return (
    name.value.trim() !== '' &&
    email.value.trim() !== '' &&
    password.value.trim() !== '' &&
    agree.value === true
  )
})
</script>

<template>
  <div class="min-h-screen flex flex-col overflow-hidden">
    <!-- ✅ Navbar Reusable -->
    <Navbar />

    <!-- Main content -->
    <main class="flex flex-1 bg-white min-h-screen overflow-hidden pt-14 pl-35">
      <!-- Left form section -->
      <div class="w-full md:w-[55%] flex flex-col justify-center px-24">
        <div class="max-w-md">
          <h1 class="text-5xl font-bold mb-5 text-black">Selamat Datang</h1>

          <form class="w-full space-y-4" @submit.prevent="() => {}">
            <div>
              <label class="block text-sm font-semibold">Name</label>
              <input
                v-model="name"
                type="text"
                placeholder="Name.."
                class="w-full border rounded-md px-3 py-2 focus:ring-2 focus:ring-green-500"
              />
            </div>

            <div>
              <label class="block text-sm font-semibold">Email address</label>
              <input
                v-model="email"
                type="email"
                placeholder="Email.."
                class="w-full border rounded-md px-3 py-2 focus:ring-2 focus:ring-green-500"
              />
            </div>

            <div>
              <label class="block text-sm font-semibold">Password</label>
              <input
                v-model="password"
                type="password"
                placeholder="Password.."
                class="w-full border rounded-md px-3 py-2 focus:ring-2 focus:ring-green-500"
              />
            </div>

            <div class="flex items-center space-x-2 text-sm">
              <input v-model="agree" type="checkbox" class="accent-green-600" />
              <span>I agree to the terms & policy</span>
            </div>

            <button
              type="submit"
              :disabled="!isFormValid"
              :class="[
                'w-full text-white py-2 rounded-md transition-colors duration-200',
                isFormValid
                  ? 'bg-green-600 hover:bg-green-700'
                  : 'bg-[#EDF2F7] text-gray-400 cursor-not-allowed',
              ]"
            >
              Sign In
            </button>

            <div class="flex items-center my-4">
              <div class="flex-1 h-px bg-[#EDF2F7]"></div>
              <p class="mx-3 text-sm text-gray-500">or</p>
              <div class="flex-1 h-px bg-[#EDF2F7]"></div>
            </div>

            <div class="flex justify-center gap-3">
              <button
                class="flex items-center gap-2 border rounded-md px-3 py-2 text-sm hover:bg-gray-50"
              >
                <img src="https://www.svgrepo.com/show/355037/google.svg" class="w-4 h-4" />
                Sign in with Google
              </button>
              <button
                class="flex items-center gap-2 border rounded-md px-3 py-2 text-sm hover:bg-gray-50"
              >
            <img src="https://cdn.jsdelivr.net/npm/simple-icons@v9/icons/apple.svg" class="w-4 h-4" />
                Sign in with Apple
              </button>
            </div>

            <p class="text-center text-sm mt-4">
              Have an account?
              <router-link to="/Sign_Up" class="text-green-600 font-semibold">Sign Up</router-link>
            </p>
          </form>
        </div>
      </div>

      <!-- Right green section -->
      <div class="hidden md:block md:w-[45%] bg-[#69BD79] rounded-l-[3rem] h-screen"></div>
    </main>


  </div>
</template>
