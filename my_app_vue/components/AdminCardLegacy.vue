<script lang="ts">
import {
  defineComponent,
  ref
} from 'vue';
export default defineComponent({
  name: 'AdminCardLegacy',
  setup() {
    const username = ref('admin_legacy');
    const status = ref('offline');
    const lastLogin = ref('2025-02');

    const toggleLogin = () => {
      if (status.value === 'offline') {
        status.value = 'online';
        lastLogin.value = new Date().toLocaleDateString();
      } else {
        status.value = 'offline';
      }
    };

    return {
      username,
      status,
      lastLogin,
      toggleLogin
    };
  }
});
</script>
<template>
  <div class="card legacy">
    <div class="header">Vue 3.0 標準</div>
    <div class="content">
      <p>Account : {{ username }}</p>
      <p>Status : <span :class="{ online: status === 'online' }">{{ status }}</span></p>
      <p>Last Login : {{ lastLogin }}</p>
      <button @click="toggleLogin">
        {{ status === 'offline' ? 'Login' : 'Logout' }}
      </button>
    </div>
  </div>
</template>
<style scoped>
.card {
  border: 1px solid #ccc;
  border-radius: 8px;
  overflow: hidden;
  margin: 10px;
  max-width: 300px;
}

.header {
  background: #555;
  color: white;
  padding: 10px;
  font-weight: bold;
}

.content {
  padding: 15px;
}

.online {
  color: green;
  font-weight: bold;
}

button {
  margin-top: 10px;
  padding: 5px 15px;
  cursor: pointer;
}
</style>
