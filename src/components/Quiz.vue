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
                            title: '¿Qué significa HTML?',
                            options: ['Lenguaje de Marcado de HiperTexto', 'Lenguaje de Marcado de Texto Avanzado', 'Lenguaje de Marcado de Tablas HiperTexto', 'Ninguna de las anteriores'],
                            answer: 0
                        },
                        {
                            title: '¿Qué elemento de HTML se utiliza para especificar el pie de página de un documento o sección?',
                            options: ['<footer>', '<section>', '<bottom>', '<end>'],
                            answer: 2
                        },
                        {
                            title: '¿Qué significa CSS?',
                            options: ['Hojas de Estilo en Cascada', 'Estilos Creativos de Sistema', 'Hojas de Estilo Computacionales', 'Colores y Tamaños de Hoja'],
                            answer: 0
                        },
                        {
                            title: '¿Cuál es la etiqueta correcta para crear un enlace en HTML?',
                            options: ['<link>', '<href>', '<a>', '<url>'],
                            answer: 2
                        },
                        {
                            title: '¿Cómo se llama el atributo de HTML que se utiliza para especificar la dirección de un enlace?',
                            options: ['enlace', 'url', 'dirección', 'href'],
                            answer: 3
                        },
                        {
                            title: '¿Cuál es la propiedad de CSS que se utiliza para cambiar el color del texto?',
                            options: ['color', 'font-color', 'text-color', 'text-style'],
                            answer: 0
                        },
                        {
                            title: '¿Qué propiedad de CSS se utiliza para establecer el espaciado entre las líneas de texto?',
                            options: ['line-height', 'spacing', 'line-spacing', 'text-spacing'],
                            answer: 0
                        },
                        {
                            title: '¿Cuál es el elemento de HTML que se utiliza para crear una lista numerada?',
                            options: ['<list>', '<ul>', '<ol>', '<dl>'],
                            answer: 2
                        },
                        {
                            title: '¿Cuál es la etiqueta de HTML utilizada para insertar una imagen en una página web?',
                            options: ['<image>', '<img>', '<picture>', '<src>'],
                            answer: 1
                        },
                        {
                            title: '¿Qué propiedad de CSS se utiliza para agregar sombra alrededor de un elemento?',
                            options: ['shadow', 'box-shadow', 'element-shadow', 'style-shadow'],
                            answer: 1
                        },
                        {
                            title: '¿Cuál es el elemento de HTML que se utiliza para agrupar elementos en una sección con estilos comunes?',
                            options: ['<group>', '<div>', '<section>', '<block>'],
                            answer: 1
                        },
                        {
                            title: '¿Qué propiedad de CSS se utiliza para cambiar el tamaño de fuente de un texto?',
                            options: ['font-size', 'text-size', 'size', 'text-font'],
                            answer: 0
                        },
                        {
                            title: '¿Cuál es la etiqueta correcta para crear un salto de línea en HTML?',
                            options: ['<break>', '<nl>', '<br>', '<lb>'],
                            answer: 2
                        },
                        {
                            title: '¿Qué atributo de HTML se utiliza para establecer una imagen de fondo en un elemento?',
                            options: ['background', 'img-background', 'bg-image', 'background-image'],
                            answer: 3
                        },
                        {
                            title: '¿Cuál es la propiedad de CSS que se utiliza para alinear el texto a la derecha?',
                            options: ['text-align', 'align', 'text-right', 'align-right'],
                            answer: 0
                        }
            ],
            respuestas
        }
    }
}
</script>