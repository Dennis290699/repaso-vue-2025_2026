<template>
  <div class="container">
    <PersonasView />
  </div>
</template>

<script>
  import PersonasView from './views/PersonasView.vue'

export default {
  components: {
    PersonasView
  }
};
</script>

<style>

body {
  font-family: 'Times New Roman', Times, serif;
}

.container,
.form-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

button {
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    background-color: #007BFF;
    color: #fff;
    font-weight: bold;
    cursor: pointer;
    transition: ease all 0.3s;
}

button:hover {
    background-color: #0056b3;
}
</style>
