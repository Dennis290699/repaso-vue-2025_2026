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
table {
  width: 100%;
  border-collapse: separate;
  border-spacing: 0;
  margin-top: 10px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.04);
  border-radius: 12px;
  overflow: hidden;
}

th, td {
  padding: 12px 16px;
  text-align: center;
}

th {
  background-color: #f1f8e9; /* verde muy suave */
  color: #555;
  font-weight: 600;
}

tr:nth-child(even) {
  background-color: #fcfcfc;
}

tr:hover {
  background-color: #f5f5f5;
}
</style>