<script setup>
import Navbar from './components/NavBar.vue';
import DatosPersonales from './components/DatosPersonales.vue';
import Educacion from './components/EducacionComponentes.vue';
import ExperienciaComponentes from './components/ExperienciaComponentes.vue';
import ProyectosComponente from './components/ProyectosComponente.vue';
import HabilidadesComponentes from './components/HabilidadesComponentes.vue';
</script>

<template>
    <header>
        <!--Barra de navegacion-->
        <Navbar/>
        <!--Componente Datos Personales-->
        <DatosPersonales/>
    </header>
    <main>
        <!--El estilo section css de section se encuentra en base.css-->
        <section id="educacion">
            <h2>Educación - Cursos</h2>
            <!--Componente Educacion-->
            <Educacion />
        </section>
        <section id="experiencia">
            <h2>Experiencia</h2>
            <!--Componente Experiencia-->
            <ExperienciaComponentes />
        </section>
        <section id="proyectos">
            <h2>Proyectos</h2>
            <!--Componente Proyectos-->
            <ProyectosComponente />
        </section>
        <section id="habilidades">
            <h2>Habilidades</h2>
            <!--Componente Habilidades-->
            <HabilidadesComponentes />
        </section>
            
        <section id="intereses"><h2>Intereses</h2></section>
    </main>
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
    box-shadow: 0 0 5px rgba(251, 249, 249, 0.934);
}

h3 {
    font-size: 1.2rem;
    font-weight: 600;
}
</style>
