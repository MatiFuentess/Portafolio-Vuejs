<script setup>
import linkedin from '/src/assets/linkedin-icon.svg';
import Instagram from '/src/assets/instagram-icon.svg';
import Github from '/src/assets/github-icon.svg';
import Curriculum from '/src/assets/curriculum-vitae-icon.svg';

const title = "Matias Fuentes";
const descripcion = "Tecnico Universitario en programacion - UTN";
const residencia = "Guaymallén, San Jose, Mendoza, Argentina";
const presentacion = "Hola, bienvenido a mi portafolio de proyectos. Soy un desarrollador web con experiencia en el desarrollo de aplicaciones web y moviles";
const redesSociales = [
    {id: 1, name: "Linkedin", src: linkedin, url: "https://www.linkedin.com/in/matias-fuentes-490420209/"},
    {id: 2, name: "Instagram", src: Instagram, url: "https://www.instagram.com/matiasfuentes.07/"},
    {id: 3, name: "GitHub", src: Github, url: "https://github.com/MatiFuentess"},
    {id: 4, name: "Curriculum", src: Curriculum, url:" " },
];
const telefono = "+54 2612497770";
</script>

<template>
<section class="datos-personales">
<div class="card">
    <h1>{{ title }}</h1>
    <h2>{{ descripcion }}</h2>
    <P>{{ presentacion }}</P>
    <ul class="container-lista">
        <li v-for="red in redesSociales" :key="red.id">
            <a href="red.url"><img class="icon-redsocial" :src="red.src" width="35rem" :alt="red.name"></a>
        </li>
    </ul>
    <h3>Mi telefono personal: {{ telefono }}</h3>
    <h4>{{residencia}}</h4>
</div>
</section> 

</template>

<style scoped>
h1 {
    font-size: 2.5rem;
}
p {
    font-size: 1.2rem;
    font-weight: 600;
    margin-bottom: 1rem;
}
.card {
    background-color: rgb(28, 41, 52);
    border-radius: 10px;
    padding: 10px;
    margin: 10px;
    text-align: center;
}
.container-lista {
    display: flex;
    justify-content: center;
    list-style: none;
    padding: 0%;
    margin: 0%;
    text-align: center;
}
.icon-redsocial {
    align-items: center;
    background-color: aliceblue;
    border-radius: 50%;
    padding: 2px;
    margin: 5px;
    box-shadow: 0 0 5px rgba(95, 124, 205, 0.934);
}
.icon-redsocial:hover {
    background-color: rgb(28, 41, 52);
    box-shadow: 0 0 5px rgba(95, 124, 205, 0.934);
}
h3 {
    font-size: 1.2rem;
    font-weight: 600;
}

</style>