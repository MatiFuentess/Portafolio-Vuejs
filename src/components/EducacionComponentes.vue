<script setup>
import { ref } from 'vue';
const fechaColor = ref([]);
fechaColor.value = [
    {color: "#41516c"},
    {color: "#FBCA3E"}
];
const educacion = ref ([
    {fecha: "2024", title: "Tecnicatura Universitaria en Programacion", descripcion: "Incumbencias profesionales: Operacion y programacion de computadoras, desarrollo de programas en distintos lenguajes, analisis y control de sistemas informaticos."},
    {fecha: "2023", title: "Programacion y POO en Java", descripcion: "Incumbencias profesionales: Curso basico de POO en Java con NetBeans y introduccion a la programación con Pseint."},
]);
</script>

<template>
    <ul>
        <li v-for="(item,index) in educacion" :key="index" :style="{'--fecha-color': fechaColor[index].color}">
        <div class="fecha">{{ item.fecha }}</div>
        <h3 class="title">{{ item.title }}</h3>
        <div class="descripcion">{{ item.descripcion }}</div>
        <!--Aqui vemos con el uso de b-vind (:) que brindemos el atributo href de html con el item.enlace-->
        <a class="enlace" :href="item.enlace" target="_blank">Saber más</a>
    </li>
    </ul>
</template>

<style scoped>
/* Estilos generales*/
@import url("https://fonts.googleapis.com/css2?family=poppins:wght@300;500;700&display=swap");
/* Reseteo de estilos basicos para todos los elementos y pseudo-elementos*/
*,
*::before,
*::after {
    margin: 0; /*Elimina el margen predeterminado*/
    padding: 0; /*Elimina el padding predeterminado*/
    box-sizing: border-box; /*Incluye el padding y el borde en el tamaño total del elemento*/
}

/*Estilo para el cuerpo de la pagina*/
body {
    --color: rgba(30,30,30); /*Variable para el color de texto*/
    --bgColor:rgba(245,245,245); /*Variable para el color de fondo*/
    min-height: 100vh; /*Asegura que el cuerpo ocupe al menos el 100% de la altura de la ventana*/
    display: grid; /*Utiliza el modelo de caja de cuadricula*/
    align-content: center; /*Centra verticalmente el contenido dentro de la matricula*/
    gap: 2rem; /*Espaciado interno alrededor del cuerpo*/
    font-family: "Poppins",sans-serif; /*Fuente para todo el texto en la pagina*/
    color: var(--color); /*Aplica el color de texto definido en la variable*/
    background: var(--bgcolor); /*Aplica el color de fondo definido en la variable*/
}

/*Estilos para la lista*/
ul {
    margin-top: 2rem;
    --col-gap: 2rem; /*Espacio entre las columnas de la cuadricula*/
    --row-gap: 2rem; /*Espacio entre las filas de la cuadricula*/
    --line-w: 0.25rem; /*Ancho de la linea que conecta los elementos de la lista*/
    display: grid; /*Usa un layout de cuadricula*/
    grid-template-columns: var(--line-w) 1fr; /*Define las columnas de la cuadricula: la primera es la linea y la segunda es el contenido*/
    grid-auto-columns: max-content; /*Las columnas se ajustan automaticamente al contenido*/
    column-gap: var(--col-gap); /*Espacio entre las columnas*/
    list-style: none; /*Elimina las viñetas predeterminados de la lista*/
    width: min(60rem, 90%); /*Limita el ancho de la lista al minimo entre 60rem y el 90% del ancho de la ventana */
    margin-inline: auto; /*Centra la lista horizontalmente*/
}

/*Estilo para la linea vertical que conecta los elementos de la lista*/
ul::before {
    content: ""; /*Elemento vacio para crear la linea*/
    grid-column: 1; /*Coloca la linea en la primera columna de la cuadricula*/
    grid-row: 1 / span 20; /*La linea se extiende sobre varias filas*/
    background: rgb(225, 225, 225); /*Color de la linea*/
    border-radius: calc(var(--line-w) / 2); /*Bordes redondeados para la linea*/
}

/*Estilo para los elementos de la lista que no son el ultimo*/
ul li:not(:last-child) {
    margin-bottom: var(--row-gap); /*Espacio entre los elementos de la lista*/
}

/*Estilo para cada item de la lista*/
ul li {
    grid-column: 2; /*Coloca el contenido en la segunda columna de la cuadricula*/
    --inlineP: 1,5rem; /*Espacio interno horizontal dentro de cada item*/
    margin-inline: var(--inlineP); /*Margen horizontal para los items*/
    grid-row: span 2; /*Cada item ocupa dos filas en la cuadricula*/
    display: grid; /*Usa un layout de cuadricula dentro de cada item*/
    grid-template-rows: min-content min-content min-content; /*Define tres filas de altura minima*/
}

/*Estilo para la fecha dentro de cada item*/
ul li .fecha {
--dateH: 3rem; /*Altura de la seccion de la fecha*/
height: var(--dateH); /*Aplica la altura definida*/
margin-inline: calc(var(--inlineP) * -1); /*Ajusta el margen horizontal para que la fecha sobresalga*/
text-align: center; /*Centra el texto dentro de la fecha*/
background-color: var(--fecha-color); /*Color de fondo, usando una variable personalizada*/
color: white; /*Color del texto en la fecha*/
font-size: 1.25rem; /*Tamaño del texto*/
font-weight: 700; /*Hace el texto en negrita*/
display: grid; /*Usa un layout de cuadricula*/
place-content: center; /*Centra el contenido de la fecha*/
position: relative; /*Posiciona la fecha relativa a su contenedor*/
border-radius: calc(var(--dateH) / 2) 0 0 calc(var(--dateH) / 2); /*Bordes redondeados para la fecha*/
}

ul li .fecha::before {
    content: ""; /*Elemento vacio para crear el triangulo*/
    width: var(--inlineP); /*Ancho igual al espacio interno definido*/
    aspect-ratio: 1; /*Mantiene una relacion de aspecto 1:1 para crear un cuadrado*/
    background: var(--fecha-color); /*Uso el color de fondo de la fecha*/
    background-image: linear-gradient(rgba(0,0,0,0.2) 100%, transparent); /*Aplica un degradado sutil para dar un efecto de sombra*/
    position: absolute; /*Posiciona el triangulo respecto al contenedor de la fecha*/
    top: 100%; /*Coloca el triangulo justo debajo de la fecha*/
    clip-path: polygon(0 0, 100% 0,0 100%); /*Recorta el cuadrado para convertirle en un triangulo*/
    right: 0; /*Alinea el triangulo a la derecha de la fecha*/
}

/*Estilo para el circulo que conecta la fecha con la linea*/
ul li .fecha::after {
    content: "";
    position: absolute;
    width: 1rem;
    aspect-ratio: 1;
    background: var(--bgColor);
    border: 0.3rem solid var(--fecha-color);
    border-radius: 50%;
    top: 50%;
    transform: translate(50%, -50%);
    right: calc(100% + var(--col-gap) + var(--line-w) / 2);
}
/*Estilos para el titulo y la descripcion dentro de cada item*/
ul li .title,
ul li .descripcion {
    background: var(--bgColor);
    position: relative;
    padding-inline: 1.5rem;
}

ul li .title {
    overflow: hidden;
    padding-block-start: 1.5rem;
    padding-block-end: 1rem;
    font-weight: 500;
}

ul li .descripcion {
    padding-block-end: 1.5rem;
    font-weight: 300;
}

/*Estilos para las sombras debajo del titulo y la descripcion*/
ul li .title::before,
ul li .descripcion::before {
    content: "";
    position: absolute;
    width: 90%;
    height: 0.5rem;
    background: rgba(0,0,0,0.5);
    left: 50%;
    border-radius: 50%;
    filter: blur(4px);
    transform: translate(-50%, 50%);
}

ul li .title::before {
    bottom: calc(100% + 0.125rem);
}

ul li .descripcion::before {
    z-index: -1;
    bottom: 0.25rem;
}

/*Media Query para las pantallas anchas (40rem o mas)*/
@media (min-width: 40rem) {
    ul {
        grid-template-columns: 1fr var(--line-w) 1fr;
    }
    ul::before {
        grid-column: 2;
    }
    ul li:nth-child(odd) {
        grid-column: 1;
    }
    ul li:nth-child(even) {
        grid-column: 3;
    }
    /*Ajuste para que el segundo item abarque dos filas*/
    ul li:nth-child(2) {
        grid-row: 2/4;
    }

    /*Ajustes especificos para los items impares*/
    ul li:nth-child(odd) .fecha::before {
        clip-path: polygon(0 0, 100% 0, 100% 100%);
        left: 0;
    }

    ul li:nth-child(odd) .fecha::after {
        transform: translate(-50%, -50%);
        left: calc(100% + var(--col-gap) + var/--line-w) / 2;
    }

    ul li:nth-child(odd) .fecha {
        border-radius: 0 calc(var(--dateH) / 2) calc(var(--dateH) / 2) 0;
    }
}

/*Estilos para los creditos*/
.credits {
    margin-top: 1rem;
    text-align: right;
}

.credits a {
    color: var(--color);
}
</style>
