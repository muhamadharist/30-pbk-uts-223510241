<template>
  <div class="home-container">
    <div class="home-content">
      <img src="../assets/logo.png" alt="Logo Universitas" class="logo">
      <h1 class="home-title">UNIVERSITAS ISLAM RIAU</h1>
      <p class="home-description">Menjadi Sarjana Yang Berlandaskan Iman Dan Taqwa</p>
      <router-link to="/about" class="btn" @click="handleAboutClick">Tentang Kami</router-link>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    handleAboutClick() {
      this.$router.push('/about');
    }
  }
}
</script>

<style>
.home-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #28a745; 
  background-size: cover;
  background-position: center;
}

.home-content {
  text-align: center;
}

.logo {
  width: 200px; 
  margin-bottom: 10px;
}

.home-title {
  font-size: 48px; 
  font-weight: bold;
  color: #fff;
  margin-bottom: 20px;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5); 
  transition: color 0.3s; 
}

.home-title:hover {
  color: #ffd700; 
}

.home-description {
  font-size: 20px; 
  color: #fff;
  margin-bottom: 30px;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5); 
}

.btn {
  padding: 12px 24px; 
  font-size: 16px; 
  background-color: #007bff;
  color: white;
  text-decoration: none;
  border-radius: 25px; 
  transition: background-color 0.3s;
}

.btn:hover {
  background-color: #0056b3;
}
</style>
