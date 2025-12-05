<template>
    <div class="form-container">
        <h1 class="title">{{ titulo }}</h1>

        <form @submit.prevent="enviarFormulario">
            <div class="data-form">
                <label>Nombre:</label>
                <input v-model.trim="nombre" type="text" placeholder="Jhon">
            </div>

            <div class="data-form">
                <label>Apellido:</label>
                <input v-model.trim="apellido" type="text" placeholder="Doe">
            </div>

            <div class="btn-container">
                <button type="submit">Agregar</button>
            </div>
        </form>

        <!-- Mensajes -->
        <div class="msg-container">
            <p v-if="msgExito" class="msg-exito">{{ msgExito }}</p>
            <p v-if="msgError" class="msg-error">{{ msgError }}</p>
        </div>
    </div>
</template>

<script>
export default {
    emits: ['agregar-persona'],
    data() {
        return {
            nombre: '',
            apellido: '',
            titulo: 'Agregar Persona',
            msgExito: '',
            msgError: '',
            timer: null
        }
    },
    methods: {
        enviarFormulario() {
            if (!this.nombre || !this.apellido) {
                this.mostrarMensaje('error');
                return;
            }

            const persona = {
                nombre: this.nombre,
                apellido: this.apellido
            };

            this.$emit('agregar-persona', persona);
            this.limpiarFormulario();
            this.mostrarMensaje('exito');
        },
        limpiarFormulario() {
            this.nombre = '';
            this.apellido = '';
        },
        limpiarMsg() {
            this.msgExito = '';
            this.msgError = '';
        },
        mostrarMensaje(tipo) {
            this.limpiarMsg();

            if (tipo === 'exito') {
                this.msgExito = 'Datos guardados exitosamente';
            } else {
                this.msgError = 'Complete todos los campos';
            }

            clearTimeout(this.timer);
            this.timer = setTimeout(() => {
                this.msgExito = '';
                this.msgError = '';
            }, 2000);
        }
    }
}
</script>

<style scoped>
.form-container {
  margin: 25px;
  padding: 30px;
  border-radius: 16px;
  background: #ffffff;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.06);
  width: 100%;
  max-width: 400px;
}

.title {
  margin-bottom: 20px;
  text-align: center;
  font-size: 24px;
  font-weight: 600;
  color: #495057;
}

.data-form {
  margin-bottom: 20px;
}

.data-form label {
  display: block;
  margin-bottom: 6px;
  font-weight: 500;
  color: #555;
}

.data-form input {
  width: 100%;
  padding: 10px 12px;
  border: 1px solid #e0e0e0;
  border-radius: 10px;
  font-size: 15px;
  transition: border-color 0.25s ease;
}

.data-form input:focus {
  outline: none;
  border-color: #81c784;
  box-shadow: 0 0 0 3px rgba(129, 199, 132, 0.15);
}

.btn-container {
  text-align: center;
  margin-top: 25px;
}
.btn-container button {
  background-color: #81c784;
  color: white;
  padding: 11px 24px;
  border: none;
  border-radius: 10px;
  font-weight: 600;
  font-size: 15px;
  cursor: pointer;
  transition: background-color 0.25s ease, transform 0.15s ease;
}

.btn-container button:hover {
  background-color: #a3d9a5;
  transform: translateY(-2px);
}

.msg-container {
    margin-top: 15px;
    text-align: center;
}

.msg-exito {
    color: #0a7a13;
    background: #d4f8d7;
    padding: 8px;
    border-radius: 6px;
    font-weight: bold;
}

.msg-error {
    color: #b00020;
    background: #ffd6d9;
    padding: 8px;
    border-radius: 6px;
    font-weight: bold;
}
</style>
