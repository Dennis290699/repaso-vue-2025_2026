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

.list-container ul {
    list-style: none;
    padding: 0;
}

.list-container li {
    margin: 15px;
    padding: 8px;
    box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.75);
    border-radius: 5px;
    text-align: center;
    cursor: pointer;
}
</style>