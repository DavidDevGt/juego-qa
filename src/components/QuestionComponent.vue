<template>
    <div>
        <h2>{{ pregunta }}</h2>
        <div v-for="(opcion, index) in opciones" :key="index">
            <input type="radio" :value="opcion" v-model="respuestaSeleccionada" :id="'opcion' + index">
            <label :for="'opcion' + index">{{ opcion }}</label>
        </div>
    </div>
</template>

<script>
export default {
    props: ['pregunta', 'opciones'],
    data() {
        return {
            respuestaSeleccionada: null
        };
    },
    watch: {
        respuestaSeleccionada(nuevaRespuesta) {
            this.$emit('respuesta-seleccionada', nuevaRespuesta);
        }
    }
}
</script>