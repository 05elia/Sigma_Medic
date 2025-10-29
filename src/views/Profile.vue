<template>
  <div class="min-h-screen flex flex-col bg-[#F8FBF7]">
    <!-- Navbar -->
    <Navbar />

    <!-- Main Content -->
    <main class="flex-grow pt-24 pb-20 px-6 lg:px-24">
      <!-- Profil Perusahaan -->
      <section
        class="bg-[#EAF5E7] rounded-2xl p-6 lg:p-10 flex flex-col lg:flex-row items-center lg:items-start gap-8 shadow-md"
      >
        <img
          src="@/assets/profil-team.jpg"
          alt="Tim Sigma Medic"
          class="rounded-xl w-full lg:w-1/3 object-cover shadow"
        />
        <div class="flex-1">
          <h2 class="text-2xl font-semibold mb-3 text-gray-800">PT. SIGMA MEDIC</h2>
          <p class="text-gray-700 leading-relaxed mb-3">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
            incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
            exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
          </p>
          <p class="text-gray-700 leading-relaxed mb-3">
            Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat
            nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui
            officia deserunt mollit anim id est laborum.
          </p>
        </div>
      </section>

      <!-- Visi & Misi -->
      <section class="mt-12 grid grid-cols-1 lg:grid-cols-2 gap-8">
        <!-- VISI -->
        <div class="bg-[#EAF5E7] rounded-2xl p-6 shadow-md">
          <h3 class="text-xl font-semibold mb-3 text-gray-800">VISI PERUSAHAAN</h3>
          <p class="text-gray-700 leading-relaxed">
            Menjadi perusahaan teknologi kesehatan terpercaya yang menghadirkan inovasi digital dan
            produk alat medis berkualitas tinggi untuk mendukung peningkatan layanan kesehatan di
            Indonesia.
          </p>
        </div>

        <!-- MISI -->
        <div class="bg-[#EAF5E7] rounded-2xl p-6 shadow-md">
          <h3 class="text-xl font-semibold mb-3 text-gray-800">MISI PERUSAHAAN</h3>
          <ul class="list-disc list-inside text-gray-700 space-y-2">
            <li>
              Mengembangkan sistem digital terpadu untuk mempermudah proses pengadaan alat
              kesehatan.
            </li>
            <li>
              Menyediakan alat kesehatan berkualitas sesuai standar nasional dan internasional.
            </li>
            <li>
              Membangun hubungan kemitraan jangka panjang dengan rumah sakit, klinik, dan tenaga
              kesehatan.
            </li>
            <li>Memberikan pelayanan yang profesional dan berintegritas tinggi.</li>
          </ul>
        </div>
      </section>
    </main>

    <!-- Footer -->
    <Footer />
  </div>
</template>

<script setup>
import Navbar from '@/components/Navbar.vue'
import Footer from '@/components/Footer.vue'
</script>

<style scoped>
/* Biar lebih smooth */
html {
  scroll-behavior: smooth;
}
</style>
