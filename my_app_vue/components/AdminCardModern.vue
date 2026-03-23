<script setup lang="ts">
import { ref } from 'vue';
const username = ref('admin_modern');
const status = ref('offline');
const lastLogin = ref('2026-02-12');

const toggleLogin = () => {
  if (status.value === 'offline') {
    status.value = 'online';
    const now = new Date();
    lastLogin.value = `${now.getHours()}:${now.getMinutes()}`;
  } else {
    status.value = 'offline';
  }
};
</script>

<template>
  <div class="card modern">
    <div class="header">Vue 3.2 現代版</div>
    <div class="content">
      <p>Account:{{ username }}</p>
      <p>Status:<span :class="{ online: status === 'online' }">{{ status }}</span></p>
      <p>Last Login : {{ lastLogin }}</p>
      <button @click="toggleLogin">
        {{ status === 'offline' ? 'Login' : 'Logout' }}
      </button>
    </div>
  </div>
</template>

<style scoped>
.card {
  border: 2px solid #42b883;
  border-radius: 8px;
  overflow: hidden;
  margin: 10px;
  max-width: 300px;
}

.header {
  background: #42b883;
  color: white;
  padding: 10px;
  font-weight: bold;
}

.content {
  padding: 15px;
}

.online {
  color: #42b883;
  font-weight: bold;
}

button {
  margin-top: 10px;
  padding: 5px 15px;
  cursor: pointer;
}
</style>
