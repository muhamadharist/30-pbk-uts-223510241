<template>
  <div class="about-container">
    <div class="about-content">
      <img src="../assets/logo.png" alt="Logo Web" class="logo">
      <h1 class="about-title">Tentang Kami</h1>
      <p class="about-description">
        Universitas Islam Riau (UIR) adalah salah satu Perguruan Tinggi Swasta yang berkedudukan di Pekanbaru, Riau, Indonesia berdiri pada 4 September 1962. Pada saat didirikan Universitas Islam Riau hanya memiliki satu fakultas, yaitu Fakultas Agama dengan dua Jurusan yaitu jurusan Hukum dan Tarbiyah, dengan Dekan Pertama H.A. Kadir Abbas,S.H. Terletak di Pusat Kota Pekanbaru Jl. Prof. Mohd. Yamin, S.H, bangunan gedung Tingkat dua. UIR terus mengembangkan pembangunan dibidang fisik di lokasi kedua Jl. Kaharuddin Nasution KM 11 Perhentian Marpoyan.
      </p>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
.about-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: linear-gradient(135deg, #a8e063, #56ab2f); /* Gradient hijau */
}

.about-content {
  text-align: center;
  background: rgba(255, 255, 255, 0.8); /* Putih dengan transparansi */
  padding: 40px;
  border-radius: 15px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2); /* Bayangan */
  animation: fadeIn 2s ease-in-out; /* Animasi masuk */
}

.logo {
  width: 150px; /* Sesuaikan ukuran logo sesuai kebutuhan */
  margin-bottom: 20px;
}

.about-title {
  font-size: 36px;
  font-weight: bold;
  color: #2e7d32; /* Warna hijau solid */
  margin-bottom: 20px;
  animation: slideIn 1s ease-out; /* Animasi geser masuk */
}

.about-description {
  font-size: 18px;
  color: #2e7d32; /* Warna hijau solid */
  margin-bottom: 30px;
  animation: fadeIn 2s ease-in-out; /* Animasi masuk */
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@keyframes slideIn {
  from {
    transform: translateY(-20px);
    opacity: 0;
  }
  to {
    transform: translateY(0);
    opacity: 1;
  }
}
</style>
