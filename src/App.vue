<template>
  <div>
    <header class="header-green">
      <nav class="menu">
        <ul>
          <li><router-link to="/">Home</router-link></li>
          <li><router-link to="/todos">Todos</router-link></li>
          <li><router-link to="/posts">Posts</router-link></li>
          <li><router-link to="/albums">Albums</router-link></li>
          <li><router-link to="/about">About</router-link></li>
        </ul>
      </nav>
    </header>
    <router-view></router-view>
  </div>
</template>

<style>
.header-green {
  background-color: #006400; /* Warna hijau tua */
  padding: 20px;
  text-align: center;
}

.menu ul {
  display: flex;
  justify-content: center;
  list-style: none;
  padding: 0;
  margin: 0;
}

.menu ul li {
  margin: 0 15px;
}

.menu ul li a {
  text-decoration: none;
  color: #ffffff; /* Warna teks putih */
  font-weight: bold;
  font-size: 30px;
  padding: 10px 20px;
  border-radius: 20px;
  transition: background-color 0.3s, transform 0.3s;
}

.menu ul li a:hover {
  background-color: #004d00; /* Warna hijau tua sedikit lebih gelap saat hover */
  transform: scale(1.05);
}
</style>
