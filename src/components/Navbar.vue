<template>
  <nav
    class="bg-[#A5C79B] text-sm w-full fixed top-0 left-0 z-50 opacity-0 -translate-y-5 transition-all duration-700 ease-[cubic-bezier(0.22,1,0.36,1)]"
    :class="{ 'opacity-100 translate-y-0': navbarVisible }"
  >
    <!-- ✅ Top contact bar -->
    <div class="flex justify-center items-center px-6 py-2 text-white text-center">
      <div class="flex items-center gap-2 flex-wrap justify-center">
        <span>📧 contact@sigmamedic.com</span>
        <span>| ☎ Tel: 888.688.6822</span>
      </div>
    </div>

    <!-- ✅ Main Navbar -->
    <div class="bg-white flex items-center justify-between px-6 md:px-10 py-3 shadow-sm relative">
      <!-- ✅ Logo -->
      <router-link to="/" class="flex items-center gap-[4px] group">
        <img
          :src="logoSigma"
          alt="Sigma Medic Logo"
          class="w-10 h-10 object-contain transition-transform duration-200 group-hover:scale-105"
        />
        <span
          class="font-bold text-lg tracking-tight leading-none transition-colors duration-200"
          :style="{ color: logoColor }"
        >
          Sigma&nbsp;Medic
        </span>
      </router-link>

      <!-- ✅ Hamburger (mobile only) -->
      <button
        @click="menuOpen = !menuOpen"
        class="md:hidden focus:outline-none"
        aria-label="Toggle Menu"
      >
        <svg
          v-if="!menuOpen"
          xmlns="http://www.w3.org/2000/svg"
          class="w-6 h-6 text-gray-700"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
        </svg>
        <svg
          v-else
          xmlns="http://www.w3.org/2000/svg"
          class="w-6 h-6 text-gray-700"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
        </svg>
      </button>

      <!-- ✅ Menu (desktop) -->
      <ul class="hidden md:flex items-center gap-8 font-medium">
        <li>
          <router-link
            to="/"
            class="relative transition-colors duration-300"
            :class="{
              'text-[#5B8A62] after:absolute after:left-0 after:bottom-[-3px] after:w-full after:h-[2px] after:bg-[#5B8A62] after:rounded-full':
                route.path === '/',
              'text-gray-700 hover:text-[#5B8A62]': route.path !== '/'
            }"
          >
            Beranda
          </router-link>
        </li>

        <li>
          <router-link
            to="/Profile"
            class="relative transition-colors duration-300"
            :class="{
              'text-[#5B8A62] after:absolute after:left-0 after:bottom-[-3px] after:w-full after:h-[2px] after:bg-[#5B8A62] after:rounded-full':
                route.path === '/Profile',
              'text-gray-700 hover:text-[#5B8A62]': route.path !== '/Profile'
            }"
          >
            Profile
          </router-link>
        </li>

        <li>
          <router-link
            to="/Produk"
            class="relative transition-colors duration-300"
            :class="{
              'text-[#5B8A62] after:absolute after:left-0 after:bottom-[-3px] after:w-full after:h-[2px] after:bg-[#5B8A62] after:rounded-full':
                route.path === '/Produk',
              'text-gray-700 hover:text-[#5B8A62]': route.path !== '/Produk'
            }"
          >
            Produk
          </router-link>
        </li>

        <li>
          <router-link
            to="/kontak"
            class="relative transition-colors duration-300"
            :class="{
              'text-[#5B8A62] after:absolute after:left-0 after:bottom-[-3px] after:w-full after:h-[2px] after:bg-[#5B8A62] after:rounded-full':
                route.path === '/kontak',
              'text-gray-700 hover:text-[#5B8A62]': route.path !== '/kontak'
            }"
          >
            Kontak
          </router-link>
        </li>
      </ul>

      <!-- ✅ Tombol kanan -->
      <div class="hidden md:block">
        <router-link
          :to="buttonLink"
          class="bg-[#A5C79B] text-white px-5 py-2 rounded-full shadow hover:shadow-lg transition"
        >
          {{ buttonText }}
        </router-link>
      </div>
    </div>

    <!-- ✅ Dropdown Menu (mobile) -->
    <transition name="slide">
      <div
        v-if="menuOpen"
        class="md:hidden bg-white shadow-lg flex flex-col items-center gap-4 py-4 border-t border-gray-200"
      >
        <router-link to="/" class="hover:text-green-600" @click="closeMenu">Beranda</router-link>
        <router-link to="/Profile" class="hover:text-green-600" @click="closeMenu">Profile</router-link>
        <router-link to="/Produk" class="hover:text-green-600" @click="closeMenu">Produk</router-link>
        <router-link to="/kontak" class="hover:text-green-600" @click="closeMenu">Kontak</router-link>

        <router-link
          :to="buttonLink"
          class="bg-[#A5C79B] text-white px-5 py-2 rounded-full shadow hover:shadow-lg transition"
          @click="closeMenu"
        >
          {{ buttonText }}
        </router-link>
      </div>
    </transition>
  </nav>
</template>

<script setup>
import { ref, computed, onMounted } from 'vue'
import { useRoute } from 'vue-router'
import logoSigma from '@/assets/Logo.png'

const route = useRoute()
const menuOpen = ref(false)
const logoColor = '#5B8A62'
const navbarVisible = ref(false)

const closeMenu = () => (menuOpen.value = false)

const buttonText = computed(() => {
  if (route.name === 'Sign In') return 'Sign Up'
  if (route.name === 'Sign Up') return 'Sign In'
  return 'Login'
})

const buttonLink = computed(() => {
  if (route.name === 'Sign In') return '/Sign_Up'
  if (route.name === 'Sign Up') return '/Sign_In'
  return '/Sign_In'
})

// ✅ animasi fade-down saat pertama kali halaman dimuat
onMounted(() => {
  setTimeout(() => {
    navbarVisible.value = true
  }, 100)
})
</script>

<style scoped>
.slide-enter-active,
.slide-leave-active {
  transition: all 1s ease;
}
.slide-enter-from,
.slide-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
</style>
