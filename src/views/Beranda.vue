<template>
  <div class="flex flex-col min-h-screen bg-[#F7FAF8]">
    <!-- ✅ Navbar -->
    <Navbar />

    <!-- 🩺 Hero Section -->
    <section
      class="flex flex-col md:flex-row items-center justify-between px-8 md:px-30 lg:px-30 py-45 bg-[#E7F2E5]"
    >
      <!-- Teks kiri -->
      <div class="max-w-xl space-y-6 text-center md:text-left">
        <h1 class="text-4xl md:text-5xl font-bold text-gray-800 leading-tight">
          Solusi medis <br />
          terdepan untuk kebutuhan <br />
          kesehatan anda
        </h1>
        <p class="text-gray-600">
          Sigma Medic menyediakan peralatan medis berkualitas tinggi untuk mendukung pelayanan
          kesehatan. Kami berkomitmen memberikan teknologi terbaik yang modern, responsif,
          diagnosis, dan perawatan pasien.
        </p>
        <div class="flex justify-center md:justify-start gap-4">
          <router-link
            to="/layanan"
            class="bg-[#69BD79] hover:bg-[#58a86a] text-white px-6 py-2 rounded-full shadow transition"
          >
            Selengkapnya
          </router-link>
          <router-link
            to="/kontak"
            class="border border-[#69BD79] text-[#69BD79] px-6 py-2 rounded-full hover:bg-[#69BD79] hover:text-white transition"
          >
            Kontak
          </router-link>
        </div>
      </div>

      <!-- Gambar kanan -->
      <div class="mt-10 md:mt-0 md:w-[45%]">
        <img
          src="@/assets/hero-medis.jpg"
          alt="Solusi Medis"
          class="rounded-3xl shadow-md object-cover w-full h-[350px] md:h-[420px]"
        />
      </div>
    </section>

    <!-- 🏥 Produk Unggulan -->
    <section class="px-8 md:px-16 lg:px-24 py-20 bg-white">
      <div class="text-center mb-12">
        <p class="text-sm uppercase tracking-widest text-[#69BD79]">Produk</p>
        <h2 class="text-3xl md:text-4xl font-bold text-gray-800">Produk Unggulan Sigma Medic</h2>
        <p class="text-gray-600 mt-2">
          Teknologi canggih untuk mendukung diagnosis dan perawatan pasien
        </p>
      </div>

      <!-- Grid produk -->
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
        <!-- Card 1 -->
        <div class="bg-[#F7FAF8] rounded-2xl shadow hover:shadow-lg transition overflow-hidden">
          <img src="@/assets/icu-monitor.jpg" alt="ICU Monitor" class="w-full h-56 object-cover" />
          <div class="p-6">
            <h3 class="text-lg font-semibold mb-2">ICU Monitor</h3>
            <p class="text-sm text-gray-600 mb-4">
              Menyajikan monitor ICU untuk diagnosis real-time pasien dengan teknologi akurat.
            </p>
            <div class="flex justify-between text-sm">
              <button class="text-[#69BD79] font-medium hover:underline">Lihat detail</button>
              <button class="text-[#69BD79] font-medium hover:underline">Diagnosis</button>
            </div>
          </div>
        </div>

        <!-- Card 2 -->
        <div class="bg-[#F7FAF8] rounded-2xl shadow hover:shadow-lg transition overflow-hidden">
          <img src="@/assets/kursi-roda.jpg" alt="Kursi Roda" class="w-full h-56 object-cover" />
          <div class="p-6">
            <h3 class="text-lg font-semibold mb-2">Kursi Roda</h3>
            <p class="text-sm text-gray-600 mb-4">
              Ringkas, nyaman, dan tahan lama untuk penggunaan harian pasien.
            </p>
            <div class="flex justify-between text-sm">
              <button class="text-[#69BD79] font-medium hover:underline">Lihat detail</button>
              <button class="text-[#69BD79] font-medium hover:underline">Katalog</button>
            </div>
          </div>
        </div>

        <!-- Card 3 -->
        <div class="bg-[#F7FAF8] rounded-2xl shadow hover:shadow-lg transition overflow-hidden">
          <img
            src="@/assets/sarung-tangan.jpg"
            alt="Sarung Tangan Latex"
            class="w-full h-56 object-cover"
          />
          <div class="p-6">
            <h3 class="text-lg font-semibold mb-2">Sarung Tangan Latex</h3>
            <p class="text-sm text-gray-600 mb-4">
              Sarung tangan steril dan anti bakteri untuk menjaga kebersihan tenaga medis.
            </p>
            <div class="flex justify-between text-sm">
              <button class="text-[#69BD79] font-medium hover:underline">Lihat detail</button>
              <button class="text-[#69BD79] font-medium hover:underline">Detail</button>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- ⭐ Testimoni -->
    <section class="bg-[#E7F2E5] py-20 px-8 md:px-16 lg:px-24 rounded-t-[3rem]">
      <h2 class="text-3xl font-bold text-center mb-10 text-gray-800">Testimoni Pelanggan</h2>

      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <div class="bg-white rounded-2xl shadow p-6 text-center">
          <p class="text-gray-600 mb-4">
            Pelayan dari Sigma Medic sangat membantu meningkatkan akurasi diagnosis dan perawatan
            pasien kami.
          </p>
          <p class="font-semibold text-[#69BD79]">Dr. Erika</p>
          <p class="text-sm text-gray-500">Dokter Rumah Sakit Jakarta</p>
        </div>

        <div class="bg-white rounded-2xl shadow p-6 text-center">
          <p class="text-gray-600 mb-4">
            Kualitas produk luar biasa dan desain ergonomis, sangat membantu di lapangan.
          </p>
          <p class="font-semibold text-[#69BD79]">Budi</p>
          <p class="text-sm text-gray-500">Kepala Laboratorium</p>
        </div>

        <div class="bg-white rounded-2xl shadow p-6 text-center">
          <p class="text-gray-600 mb-4">
            Sigma Medic memberikan solusi lengkap untuk kebutuhan peralatan medis rumah sakit kami.
          </p>
          <p class="font-semibold text-[#69BD79]">Dr. Rahmat</p>
          <p class="text-sm text-gray-500">Pemilik Klinik Sehat</p>
        </div>
      </div>
    </section>

    <!-- ✅ Footer -->
    <Footer />
  </div>
</template>

<script setup>
import Navbar from '@/components/Navbar.vue'
import Footer from '@/components/Footer.vue'
</script>
