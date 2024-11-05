<script setup>
import icono1 from '/src/assets/imagen.svg';
import {ref} from 'vue';
const titulo="Writting Expert IA";
const fecha = "Desde Junio 2024- hasta la actualidad";
const experiencias = ref([
    {id:1, src: icono1, parrafo: "Consiste en realizar correcciones gramaticales, evaluaciones, analisis, introduccion de promts y correccion de respuestas de la IA"},
]);
</script>

<template>
    <div class="card">
        <h3 class="titulo">{{ titulo.toLocaleUpperCase()}}</h3>
        <p class="fecha">{{ fecha }}</p>
        <ul class="listado">
            <li class="item" v-for="experiencia in experiencias" :key="experiencia.id"> 
               <img class="imagen-svg" :src="experiencia.src" width="45rem" :alt="experiencia.parrafo">
               <p>{{ experiencia.parrafo }}</p>
            </li>
        </ul>
    </div>
</template>

<style scoped>
.card{
    display: flex;
    flex-direction: column;
    padding: 2rem;
    background-color: rgb(28, 41, 52);
    border-radius: 15px;
}

.titulo{
    font-size: 1.5rem;
    color: coral;
}

.fecha{
    font-size: 1rem;
    color: burlywood;
    margin-bottom: 1rem;
}

.listado{
    display: flex;
    flex-direction: column;
}

.item{
    align-items: center;
    display: flex;
    padding: 1rem;
    gap: 1.5rem;
}
</style>