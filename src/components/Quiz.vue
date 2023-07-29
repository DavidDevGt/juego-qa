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
                        {
                            pregunta: '¿Qué significa HTML?',
                            opciones: ['Hyper Text Markup Language', 'Hyperlinks and Text Markup Language', 'Home Tool Markup Language'],
                            respuestaCorrecta: 'Hyper Text Markup Language'
                        },
                        {
                            pregunta: '¿Qué significa CSS?',
                            opciones: ['Cascading Style Sheets', 'Computer Style Sheets', 'Creative Style Sheets'],
                            respuestaCorrecta: 'Cascading Style Sheets'
                        },
                        {
                            pregunta: '¿Cuál es el elemento de HTML que se utiliza para especificar el pie de página de un documento o sección?',
                            opciones: ['<footer>', '<section>', '<bottom>', '<end>'],
                            respuestaCorrecta: '<footer>'
                        },
                        {
                            pregunta: '¿Cuál es la etiqueta correcta para crear un enlace en HTML?',
                            opciones: ['<link>', '<href>', '<a>', '<url>'],
                            respuestaCorrecta: '<a>'
                        },
                        {
                            pregunta: '¿Cuál es la propiedad de CSS que se utiliza para cambiar el color del texto?',
                            opciones: ['color', 'font-color', 'text-color', 'text-style'],
                            respuestaCorrecta: 'color'
                        },
                        {
                            pregunta: '¿Qué propiedad de CSS se utiliza para establecer el espaciado entre las líneas de texto?',
                            opciones: ['line-height', 'spacing', 'line-spacing', 'text-spacing'],
                            respuestaCorrecta: 'line-height'
                        },
                        {
                            pregunta: '¿Cuál es el elemento de HTML que se utiliza para crear una lista numerada?',
                            opciones: ['<list>', '<ul>', '<ol>', '<dl>'],
                            respuestaCorrecta: '<ol>'
                        },
                        {
                            pregunta: '¿Cuál es la etiqueta de HTML utilizada para insertar una imagen en una página web?',
                            opciones: ['<image>', '<img>', '<picture>', '<src>'],
                            respuestaCorrecta: '<img>'
                        },
                        {
                            pregunta: '¿Qué propiedad de CSS se utiliza para agregar sombra alrededor de un elemento?',
                            opciones: ['shadow', 'box-shadow', 'element-shadow', 'style-shadow'],
                            respuestaCorrecta: 'box-shadow'
                        },
                        {
                            pregunta: '¿Cuál es el elemento de HTML que se utiliza para agrupar elementos en una sección con estilos comunes?',
                            opciones: ['<group>', '<div>', '<section>', '<block>'],
                            respuestaCorrecta: '<div>'
                        },
                        {
                            pregunta: '¿Qué propiedad de CSS se utiliza para cambiar el tamaño de fuente de un texto?',
                            opciones: ['font-size', 'text-size', 'size', 'text-font'],
                            respuestaCorrecta: 'font-size'
                        },
                        {
                            pregunta: '¿Cuál es la etiqueta correcta para crear un salto de línea en HTML?',
                            opciones: ['<break>', '<nl>', '<br>', '<lb>'],
                            respuestaCorrecta: '<br>'
                        },
                        {
                            pregunta: '¿Qué atributo de HTML se utiliza para establecer una imagen de fondo en un elemento?',
                            opciones: ['background', 'img-background', 'bg-image', 'background-image'],
                            respuestaCorrecta: 'background-image'
                        },
                        {
                            pregunta: '¿Cuál es la propiedad de CSS que se utiliza para alinear el texto a la derecha?',
                            opciones: ['text-align', 'align', 'text-right', 'align-right'],
                            respuestaCorrecta: 'text-align'
                        }

            ],
            respuestas: []
        };
    },
    methods: {
        responder(respuesta) {
            this.respuestas[this.preguntaActual] = respuesta;
        },
        siguientePregunta() {
            this.preguntaActual++;
        }
    }
}
</script>