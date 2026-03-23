<script setup lang="ts">
import AdminCardLegacy from './components/AdminCardLegacy.vue';
import AdminCardModern from './components/AdminCardModern.vue';
</script>
<template>
  <div class="dashboard_container">
    <h1>後臺管理系統</h1>
    <div class="card_grid">
      <AdminCardLegacy />
      <AdminCardModern />
    </div>
  </div>
</template>
<style scoped>
body {
  margin: 0;
  font-family: sans-serif;
  background: #f0f2f5;
}

.dashboard_container {
  padding: 20px;
}

.card_grid {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
}
</style>
