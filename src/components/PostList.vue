<script setup>
import { ref, onMounted } from 'vue'

const selectedUser = ref(null)
const users = ref([])
const posts = ref([])
const selectedUserName = ref('')

const fetchUsers = async () => {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/users')
    users.value = await response.json()
  } catch (error) {
    console.error('Error fetching users:', error)
  }
}

const fetchPosts = async () => {
  if (!selectedUser.value) return
  try {
    const response = await fetch(`https://jsonplaceholder.typicode.com/posts?userId=${selectedUser.value}`)
    posts.value = await response.json()
    selectedUserName.value = users.value.find(user => user.id === selectedUser.value)?.name || ''
  } catch (error) {
    console.error('Error fetching posts:', error)
  }
}

onMounted(fetchUsers)
</script>

<template>
  <section class="post-section">
    <h2>Postingan Pengguna</h2>
    <div class="select-user">
      <label>Pilih Pengguna:</label>
      <select v-model="selectedUser" @change="fetchPosts" class="select-box">
        <option v-for="user in users" :key="user.id" :value="user.id">{{ user.name }}</option>
      </select>
    </div>
    <div v-if="posts.length > 0" class="user-posts">
      <h3>Postingan Pengguna: {{ selectedUserName }}</h3>
      <table class="post-table">
        <thead>
          <tr>
            <th>Judul</th>
            <th>Isi</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="post in posts" :key="post.id">
            <td>{{ post.title }}</td>
            <td>{{ post.body }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </section>
</template>

<style scoped>
body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #28a745;
  background-image: url('https://fiverr-res.cloudinary.com/images/q_auto,f_auto/gigs/129325364/original/afaddcb9d7dfaaf5bff7ef04101935814665ac16/design-an-attractive-background-for-your-website.png');
  background-size: cover;
  background-position: center;
  color: white;
  font-family: 'Poppins', sans-serif;
  margin: 0;
  padding: 20px;
  box-sizing: border-box;
}

.post-section {
  width: 100%;
  max-width: 800px;
  background: rgba(255, 255, 255, 0.9);
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
  text-align: center;
}

.select-user {
  margin-bottom: 20px;
}

.select-box {
  padding: 12px 16px;
  font-size: 16px;
  border: 2px solid #ccc;
  border-radius: 5px;
  background-color: #f8f8f8;
  transition: border-color 0.3s, background-color 0.3s;
}

.select-box:focus {
  outline: none;
  border-color: #007bff;
  background-color: white;
}

.user-posts {
  background-color: #f9f9f9;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  overflow-x: auto;
}

.post-table {
  width: 100%;
  border-collapse: collapse;
}

.post-table th,
.post-table td {
  padding: 12px;
  border: 1px solid #ddd;
  text-align: left;
}

.post-table th {
  background-color: #4CAF50;
  color: white;
}

.post-table td {
  background-color: white;
}

.post-table tr:hover {
  background-color: #f0f0f0;
}

h2, h3, h4, label {
  color: #333;
  font-family: 'Poppins', sans-serif;
}

h2 {
  font-size: 2rem;
  margin-bottom: 20px;
  position: relative;
  display: inline-block;
  padding-bottom: 5px;
}

h2::after {
  content: '';
  width: 50px;
  height: 3px;
  background-color: #4CAF50;
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
}

h3 {
  font-size: 1.5rem;
  margin-bottom: 15px;
  position: relative;
  display: inline-block;
  padding-bottom: 5px;
}

h3::after {
  content: '';
  width: 50px;
  height: 3px;
  background-color: #4CAF50;
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
}

label {
  font-size: 1rem;
  margin-bottom: 10px;
}

/* Media Queries */
@media (max-width: 768px) {
  .post-section {
    padding: 15px;
  }

  .select-box, .post-table th, .post-table td {
    font-size: 14px;
  }

  h2 {
    font-size: 1.75rem;
  }

  h3 {
    font-size: 1.25rem;
  }

  .select-box {
    width: 100%;
  }
}

@media (max-width: 480px) {
  .post-section {
    padding: 10px;
  }

  .select-box, .post-table th, .post-table td {
    font-size: 12px;
  }

  h2 {
    font-size: 1.5rem;
  }

  h3 {
    font-size: 1rem;
  }
}
</style>
