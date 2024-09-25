<template>
  <!-- Header (Nama dan Job Title) -->
  <header class="text-center border-b pb-8 mb-8">
    <h1 class="text-4xl font-bold text-gray-700">{{ name }}</h1>
    <p class="text-xl text-gray-700">{{ jobTitle }}</p>
    <p class="text-medium text-gray-600">{{ emailNoTelephone }}</p>
  </header>

  <div class="cv-page">
    <section class="profile">
      <h3>Profil</h3>
      <h2 class="text-2xl font-semibold text-gray-700 border-b pb-2 mb-6">Tentang Saya</h2>
      <p class="text-gray-600">{{ about }}</p>
    </section>

    <section class="education">
      <h3>Pendidikan</h3>
      <ul>
        <li v-for="(edu, index) in educationList" :key="index">
          <h4>{{ edu.degree }}</h4>
          <p>{{ edu.institution }} - {{ edu.date }}</p>
        </li>
      </ul>
    </section>

    <section class="project">
      <h3>Pengalaman Proyek</h3>
      <ul>
        <li v-for="(project, index) in ProjectList" :key="index">
          <h4>{{ project.Title }}</h4>
          <p>{{ project.name }} - {{ project.date }}</p>
          <p>{{ project.description }}</p>
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: 'Assyfaul Khoiriyah',
      jobTitle: 'Software Engineer',
      emailNoTelephone: 'assyfaassyfa0@gmail.com | 085655623610',
      about: `Saya adalah seorang Software Engineer yang bersemangat dan berdedikasi, dengan pengalaman dalam pengembangan aplikasi web dan mobile. 
              Memiliki keterampilan yang kuat dalam berbagai teknologi dan bahasa pemrograman, termasuk JavaScript, Vue.js, dan Java. 
              Saya senang bekerja dalam tim dan memiliki kemampuan untuk memecahkan masalah dengan kreatif. 
              Dengan latar belakang pendidikan di Teknologi Informasi, saya telah terlibat dalam beberapa proyek yang berfokus pada pengalaman pengguna dan desain yang responsif. 
              Saya berkomitmen untuk terus belajar dan mengikuti perkembangan teknologi terbaru untuk memberikan solusi yang inovatif dan efisien. 
              Di luar pekerjaan, saya menyukai tantangan baru, berkolaborasi dengan orang-orang berbakat, dan berkontribusi dalam proyek yang berdampak positif. 
              Saya percaya bahwa dengan dedikasi dan kerja keras, kita dapat mencapai tujuan yang lebih tinggi dan memberikan nilai lebih kepada pengguna.`,
      educationList: [
        { degree: 'D3 Teknologi Informasi', institution: 'Universitas Brawijaya', date: '2023 - 2026' },
        { degree: 'Matematika, dan Ilmu Pengetahuan Alam', institution: 'MA Darul Madinah', date: '2020 - 2023' }
      ],
      ProjectList: [
        { 
          Title: 'Project 1', 
          name: 'Contact Form', 
          date: '2024', 
          description: 'Proyek Formulir Kontak JavaScript dirancang untuk menyediakan pengguna dengan formulir kontak yang intuitif dan responsif untuk situs web atau aplikasi berbasis JavaScript.' 
        },
        { 
          Title: 'Project 2', 
          name: 'Slider App', 
          date: '2024', 
          description: 'Aplikasi Slider Vue.js adalah sebuah komponen interaktif yang memungkinkan pengguna untuk melihat koleksi gambar, konten, atau elemen lain secara bergulir atau otomatis.' 
        },
        { 
          Title: 'Project 3', 
          name: 'UI/UX Aplikasi NutriGo', 
          date: '2024', 
          description: 'NutriGo adalah aplikasi inovatif yang dirancang untuk memberikan informasi dan dukungan nutrisi kepada orang tua, khususnya bagi mereka yang memiliki anak usia dini. Dengan fokus pada pencegahan stunting, aplikasi ini membantu orang tua memastikan bahwa anak-anak mereka mendapatkan asupan gizi yang cukup dan seimbang..' 
        },
        { 
          Title: 'Project 4', 
          name: 'UI/UX Aplikasi Halal Palate', 
          date: '2023', 
          description: 'Halal Palate adalah sebuah aplikasi seluler yang membantu pengguna menemukan restoran, kafe, dan makanan halal di lokasi terdekat mereka.' 
        }
      ],
    };
  }
};
</script>

<style scoped>
.cv-page {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  max-width: 800px;
  margin: 0 auto;
  padding: 30px;
  background-color: #ffffff;
  border-radius: 10px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}

h3 {
  color: #007BFF; /* Biru */
  font-size: 20px;
  margin-bottom: 15px;
  border-bottom: 2px solid #007BFF;
  padding-bottom: 5px;
}

h4 {
  color: #000; /* Hitam */
  font-size: 16px;
  margin-bottom: 5px;
  font-weight: bold;
}

p {
  color: #333; /* Abu-abu gelap */
  font-size: 14px;
  margin: 0;
  line-height: 1.5;
}

.profile ul, 
.education ul, 
.project ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.profile li, 
.education li, 
.project li {
  margin-bottom: 20px;
  padding: 15px;
  border-left: 5px solid #007BFF; /* Border biru */
  background-color: #f0f8ff; /* Background biru muda */
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  border-radius: 5px;
  transition: background-color 0.3s, transform 0.2s;
}

.profile li:hover, 
.education li:hover, 
.project li:hover {
  background-color: #e6f0ff; /* Warna hover */
  transform: scale(1.02); /* Efek zoom saat hover */
}

.project li p {
  margin-bottom: 10px;
}

.cv-page section {
  margin-bottom: 40px;
}

/* Style untuk bagian deskripsi project */
.project li p:last-child {
  font-size: 12px; /* Font deskripsi diperkecil */
  color: #555; /* Abu-abu untuk deskripsi */
  line-height: 1.6;
}

/* Responsif untuk layar kecil */
@media (max-width: 600px) {
  .cv-page {
    padding: 20px;
  }
  
  h3 {
    font-size: 18px; /* Font lebih kecil untuk mobile */
  }

  h4 {
    font-size: 16px; /* Font lebih kecil untuk mobile */
  }

  p {
    font-size: 12px; /* Font lebih kecil untuk mobile */
  }
}
</style>
