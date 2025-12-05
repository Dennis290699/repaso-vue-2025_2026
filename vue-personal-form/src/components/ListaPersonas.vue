<template>
  <h1>{{ titulo }}</h1>
    <div class="list-container">
        <ul>
            <li v-for="(p, index) in personas" :key="index">
                {{ p.nombre }} {{ p.apellido }}
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    data() {
        return {
            titulo: 'Lista de Personas',
        }
    },
    props: {
        personas: {
            type: Array,
            default: () => []
        }
    }
}
</script>

<style scoped>
.list-container li {
  margin: 12px 0;
  padding: 12px;
  background: #ffffff;
  border-radius: 12px;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.05);
  text-align: center;
  font-size: 16px;
  color: #495057;
  transition: transform 0.2s ease;
}

.list-container li:hover {
  transform: scale(1.02);
}
</style>