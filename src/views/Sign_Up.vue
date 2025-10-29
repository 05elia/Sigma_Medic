<script setup>
import { ref, computed } from 'vue'
import Navbar from '@/components/Navbar.vue'
import Footer from '@/components/Footer.vue'

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
  <div class="flex flex-col min-h-screen bg-white overflow-x-hidden">
    <!-- ✅ Navbar -->
    <Navbar />

    <!-- ✅ Main Content (Full screen height) -->
    <main
      class="relative flex flex-col md:flex-row items-center justify-center md:justify-between bg-white h-screen overflow-hidden"
    >
      <!-- ✅ Background hijau kanan -->
      <div
        class="hidden md:block absolute top-0 right-0 w-[45%] h-full bg-[#69BD79] rounded-l-[3rem] z-0"
      ></div>

      <!-- ✅ Left (Form) -->
      <div
        class="relative z-10 w-full md:w-[55%] flex flex-col justify-center px-8 sm:px-12 md:px-20 lg:px-28 py-12 md:py-0"
      >
        <div class="max-w-md mx-auto md:mx-0">
          <h1 class="text-4xl sm:text-6xl font-bold mb-8 text-black">Ayo Daftar Sekarang</h1>

          <form class="w-full space-y-4" @submit.prevent="() => {}">
            <div>
              <label class="block text-sm font-semibold">Name</label>
              <input
                v-model="name"
                type="text"
                placeholder="your name"
                class="w-full border rounded-md px-3 py-2 focus:ring-2 focus:ring-green-500"
              />
            </div>

            <div>
              <label class="block text-sm font-semibold">Email address</label>
              <input
                v-model="email"
                type="email"
                placeholder="your email"
                class="w-full border rounded-md px-3 py-2 focus:ring-2 focus:ring-green-500"
              />
            </div>

            <div>
              <label class="block text-sm font-semibold">Password</label>
              <input
                v-model="password"
                type="password"
                placeholder="password"
                class="w-full border rounded-md px-3 py-2 focus:ring-2 focus:ring-green-500"
              />
            </div>

            <div class="flex items-center space-x-2 text-sm">
              <input v-model="agree" type="checkbox" class="accent-green-600" />
              <span>I agree to the terms & policy</span>
            </div>

            <!-- ✅ Tombol Sign Up -->
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
              Sign Up
            </button>

            <!-- Garis abu + teks "or" -->
            <div class="flex items-center my-4">
              <div class="flex-1 h-px bg-[#EDF2F7]"></div>
              <p class="mx-3 text-sm text-gray-500">or</p>
              <div class="flex-1 h-px bg-[#EDF2F7]"></div>
            </div>

            <!-- Tombol sosial -->
            <div class="flex justify-center gap-3">
              <button
                class="flex items-center gap-2 border rounded-md px-3 py-2 text-sm hover:bg-gray-50"
              >
                <img src="https://www.svgrepo.com/show/355037/google.svg" class="w-4 h-4" />
                Sign up with Google
              </button>
              <button
                class="flex items-center gap-2 border rounded-md px-3 py-2 text-sm hover:bg-gray-50"
              >
                <img src="https://www.svgrepo.com/show/349494/apple.svg" class="w-4 h-4" />
                Sign up with Apple
              </button>
            </div>

            <p class="text-center text-sm mt-4">
              Already have an account?
              <router-link to="/Sign_In" class="text-green-600 font-semibold">Sign In</router-link>
            </p>
          </form>
        </div>
      </div>
    </main>

    <!-- ✅ Footer (baru kelihatan pas scroll) -->
    <Footer />
  </div>
</template>
