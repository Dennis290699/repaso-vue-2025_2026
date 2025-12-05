<template>
  <div class="container">
    <PersonasView />
  </div>
</template>

<script>
  import PersonasView from '@/views/PersonasView.vue'

export default {
  components: {
    PersonasView
  }
};
</script>

<style>

body {
  font-family: 'Inter', 'Segoe UI', 'Roboto', sans-serif;
  background-color: #f9f9f9;
  color: #333;
  margin: 0;
  padding: 20px;
}

.container,
.form-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.container {
  max-width: 900px;
  margin: 0 auto;
  width: 100%;
  gap: 30px;
}
</style>
