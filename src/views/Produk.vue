<template>
  <div class="flex flex-col min-h-screen bg-white">
    <!-- ✅ Navbar -->
    <Navbar />

    <!-- ✅ Hero Section -->
    <section class="bg-[#E7F4E4] py-22 px-6 md:px-20 flex flex-col md:flex-row items-center gap-10">
      <div class="flex-1">
        <h1 class="text-4xl md:text-5xl font-semibold text-gray-800 mb-4 leading-tight">
          Solusi medis terdepan untuk kebutuhan kesehatan anda
        </h1>
        <p class="text-gray-600 mb-6">
          Sigma Medic menyediakan peralatan medis berkualitas tinggi untuk profesional kesehatan.
          Kami berkomitmen memberikan teknologi terbaik yang mendukung diagnosis dan perawatan
          pasien.
        </p>
        <div class="flex gap-3">
          <button class="bg-[#A5C79B] text-white px-5 py-2 rounded hover:bg-[#8EBB82] transition">
            Selengkapnya
          </button>
          <button>
            <router-link
  to="/kontak"
  class="border border-[#A5C79B] text-[#5B8A62] px-5 py-2 rounded hover:bg-[#A5C79B]/10 transition text-center"
>
  Kontak
</router-link>

          </button>
        </div>
      </div>

      <div class="flex-1">
        <img
          src="@/assets/image-page-produk.jpg"
          alt="Peralatan Medis"
          class="rounded-2xl w-full object-cover shadow-md"
        />
      </div>
    </section>

    <!-- ✅ Produk Section -->
    <section class="py-16 px-6 md:px-20 bg-white text-center">
      <h2 class="text-sm uppercase text-gray-500 mb-2">Produk</h2>
      <h1 class="text-3xl font-semibold text-gray-800 mb-10">Produk Unggulan Sigma Medic</h1>

      <div
        class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-8 justify-items-center"
      >
        <!-- ✅ Card Produk -->
        <div
          v-for="(item, index) in produkList"
          :key="index"
          class="border rounded-xl shadow-sm hover:shadow-md transition bg-white p-4 w-full max-w-[250px]"
        >
          <img :src="item.img" :alt="item.name" class="w-full h-40 object-cover rounded-md mb-3" />
          <h3 class="text-lg font-semibold mb-1">{{ item.name }}</h3>
          <p class="text-sm text-gray-600 mb-3 line-clamp-2">{{ item.desc }}</p>
          <button
            class="border border-gray-300 text-sm px-3 py-1.5 rounded hover:bg-gray-50 transition"
          >
            Lihat detail →
          </button>
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

const produkList = [
  {
    name: 'SafeTouch InjectPro',
    desc: 'Disposable syringe jarum suntik steril dan aman digunakan.',
    img: new URL('@/assets/SafeTouch-InjectPro.jpg', import.meta.url).href,
  },
  {
    name: 'Surgical Set',
    desc: 'Set instrumen pembedahan dengan kualitas tinggi.',
    img: new URL('@/assets/Surgical-set.jpg', import.meta.url).href,
  },
  {
    name: 'Walker',
    desc: 'Rangka aluminium ringan membantu mobilitas pasien.',
    img: new URL('@/assets/Walker.jpg', import.meta.url).href,
  },
  {
    name: 'Walker Set',
    desc: 'Dilengkapi tambahan roda dan pegangan empuk.',
    img: new URL('@/assets/Walker-set.jpg', import.meta.url).href,
  },
  {
    name: 'Dental Equipment',
    desc: 'Perangkat gigi berkualitas tinggi untuk klinik.',
    img: new URL('@/assets/Dental-equipment.jpg', import.meta.url).href,
  },
  {
    name: 'Hospital Bed',
    desc: 'Tempat tidur rumah sakit elektrik multifungsi.',
    img: new URL('@/assets/Hospital-bed.jpg', import.meta.url).href,
  },
  {
    name: 'Bed Screen',
    desc: 'Peralatan modern untuk mendeteksi kondisi pasien.',
    img: new URL('@/assets/Bed-screen.jpg', import.meta.url).href,
  },
  {
    name: 'First Aid Kit',
    desc: 'Perlengkapan medis darurat lengkap dan portabel.',
    img: new URL('@/assets/First-aid-kit.jpg', import.meta.url).href,
  },
]
</script>

<style scoped>
/* Biar teks deskripsi produk rapi dan gak kepanjangan */
.line-clamp-2 {
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
</style>
