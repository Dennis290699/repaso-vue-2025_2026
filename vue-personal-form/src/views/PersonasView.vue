<template>
    <h1>{{ titulo }}</h1>
    <div class="container">
        <FormPersona @agregar-persona="agregarPersona"/>
        <ListaPersonas :personas="personas"/>
        <TablaPersonas :personas="personas"/>
    </div>
</template>

<script>
import ListaPersonas from '@/components/ListaPersonas.vue';
import FormPersona from '@/components/FormPersona.vue'
import TablaPersonas from '@/components/TablaPersonas.vue';

export default {
    components: {
        FormPersona,
        ListaPersonas,
        TablaPersonas
    },
    data() {
        return {
            titulo: 'Gestion de Personas',
            personas: [],
        }
    },
    methods: {
        agregarPersona(persona) {
            this.personas.push(persona);
        }
    }
};
</script>

<style>

</style>