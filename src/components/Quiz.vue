<template>
    <div>
        <question
            v-if="preguntas[preguntaActual]"
            :pregunta="preguntas[preguntaActual].pregunta"
            :opciones="preguntas[preguntaActual].opciones"
            @respuesta-seleccionada="responder"
        />
        <button @click="siguientePregunta" v-if="preguntaActual < preguntas.length - 1">Siguiente</button>
        <p v-else>¡Has terminado el Quiz!</p>
    </div>
</template>


<script>
import Question from './Question.vue';

export default {
    components:  {  Question },
    data() {
        return {
            preguntaActual: 0,
            preguntas: [

            ],
        }
    }
}
</script>