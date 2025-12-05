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
    border-radius: 15px;
    box-shadow: 0px 0px 5px rgba(0,0,0,0.3);
}

.title {
    margin-bottom: 15px;
    text-align: center;
    font-size: 25px;
    font-weight: bold;
}

.data-form label {
    display: block;
    margin-bottom: 5px;
    font-weight: bold;
}

.data-form input {
    display: block;
    margin-bottom: 10px;
    padding: 7px;
    border: 1px solid #ccc;
    border-radius: 5px;
    width: 100%;
}

.btn-container {
    text-align: center;
    margin-top: 15px;
}

button {
    padding: 10px 18px;
    border: none;
    border-radius: 8px;
    background-color: #4f81c7;
    color: white;
    cursor: pointer;
    font-size: 15px;
}

button:hover {
    background-color: #3b68a0;
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
