<template>
  <h1>{{ titulo }}</h1>

  <table>
    <thead>
      <tr>
        <th>Nombre</th>
        <th>Apellido</th>
      </tr>
    </thead>

    <tbody>
      <tr v-for="(p, index) in personas" :key="index">
        <td>{{ p.nombre }}</td>
        <td>{{ p.apellido}}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
    data() {
        return {
            titulo: 'Tabla de Personas'
        }
    },
    props: {
        nombre: String,
        apellido: String,
        personas: {
            type: Array,
            default: () => []
        }
    }
}
</script>

<style scoped>
table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
  padding: 6px;
}

table {
  width: 100%;
}

th {
  background-color: #87b0e9;
  color: black;
  font-weight: bold;
}

td {
  text-align: center;
}
</style>