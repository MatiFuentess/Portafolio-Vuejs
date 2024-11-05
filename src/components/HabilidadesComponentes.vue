<script setup>
import img1 from '/src/components/icons/python1.svg';
import img2 from '/src/components/icons/javascript.svg';
import img3 from '/src/components/icons/html.svg';
import img4 from '/src/components/icons/css.svg';
import img5 from '/src/components/icons/sql.svg';
import img6 from '/src/components/icons/java.svg';
import img7 from '/src/components/icons/vue.svg';
import img8 from '/src/components/icons/git.svg';
import img9 from '/src/components/icons/visualstudiocode.svg';
import img10 from '/src/components/icons/mysql.svg';
import img11 from '/src/components/icons/arg.svg';
import img12 from '/src/components/icons/eeuu.svg' ;
import { ref } from "vue"

// Definir las habilidades en la constante 'habilidades'
const habilidades = ref([
    {
       id: 1, nombre: "Lenguajes de programacion", habilidades: [
            { id: 1, nombre: "Python", nivel: "Avanzado", icono: img1 },
            { id: 2, nombre: "JavaScript", nivel: "Avanzado", icono: img2 },
            { id: 3, nombre: "Html", nivel: "Avanzado", icono: img3 },
            { id: 4, nombre: "Css", nivel: "Avanzado", icono: img4 },
            { id: 5, nombre: "Sql", nivel: "Avanzado", icono: img5 },
            { id: 6, nombre: "Java", nivel: "Avanzado", icono: img6},
        ]
    },
    {
        id: 2, nombre: "Framework y Librerias", habilidades: [
            { id: 1, nombre: "Vue.js", nivel: "Avanzado", icono: img7 },
        ]
    },
    {
        
        id: 3, nombre: "Herramientas y Software", habilidades: [
            { id: 1, nombre: "Git", nivel: "Avanzado", icono: img8 },
            { id: 2, nombre: "Visual Studio Code", nivel: "Avanzado", icono: img9},
        ]
    },
    {
         id: 4, nombre: "Base de Datos", habilidades: [
            { id: 1, nombre: "MySQL", nivel: "Avanzado", icono: img10 },
        ]
    },
    {
            id: 5, nombre: "Idiomas", habilidades: [
            { id: 1, nombre: "Español", nivel: "Nativo", icono: img11 },
            { id: 2, nombre: "Inglés", nivel: "Intermedio", icono: img12 },
        ]
    }
]);

</script>

<template>
    <div class="skills-contenedor">
        <!-- Iterar sobre las categorías de habilidades -->
        <div v-for="habilidad in habilidades" :key="habilidad.id" class="skills-categoria">
            <h3>{{ habilidad.nombre }}</h3>
            <ul class="skills">
                <!-- Iterar sobre los items dentro de cada categoría -->
                <li v-for="habilidad in habilidad.habilidades" :key="habilidad.id" class="skill">
                    <img :src="habilidad.icono" :alt="habilidad.nombre">
                    <span>{{ habilidad.nombre }}: {{ habilidad.nivel }}</span>
                </li>
            </ul>
        </div>
    </div>
</template>



<!-- <template>
    <div class="skills-contenedor">
        <div class="skills-categoria">
            <h3>Lenguajes de programacion</h3>
            <ul class="skills">
                <li class="skill">
                    <img src="/src/components/icons/python1.svg" alt="Python">
                    <span>Python: Intermedio</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/javascript.svg" alt="JavaScript">
                    <span>JavaScript: Intermedio</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/html.svg" alt="Html">
                    <span>Html: Intermedio</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/css.svg" alt="Css">
                    <span>Css: Intermedio</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/sql.svg" alt="Sql">
                    <span>Sql: Intermedio</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/java.svg" alt="Java">
                    <span>Java: Intermedio</span>
                </li>
            </ul>
        </div>
    

    <div class="skills-categoria">
        <h3>Frameworks y Librerias</h3>
        <ul class="skills">
            <li class="skill">
                <img src="/src/components/icons/vue.svg" alt="Vue.js">
                <span>Vue.js: Intermedio</span>
            </li>
        </ul>
    </div>

    <div class="skills-categoria">
        <h3>Herramienta y Software</h3>
        <ul class="skills">
            <li class="skill">
                <img src="/src/components/icons/git.svg" alt="Git">
                <span>Git: Intermedio</span>
            </li>
            <li class="skill">
                <img src="/src/components/icons/visualstudiocode.svg" alt="Visual Studio Code">
                <span>Visual Studio Code: Intermedio</span>
            </li>
        </ul>
    </div>

    <div class="skills-categoria">
        <h3>Base de Datos</h3>
        <ul class="skills">
            <li class="skill">
                <img src="/src/components/icons/mysql.svg" alt="MySQL">
                <span>MySQL: Intermedio</span>
            </li>
        </ul>
    </div>

    <div class="skills-categoria">
        <h3>Idiomas</h3>
        <ul class="skills">
            <li class="skill">
                <img src="/src/components/icons/arg.svg" alt="Español">
                <span>Español: Nativo</span>
            </li>
            <li class="skill">
                <img src="/src/components/icons/eeuu.svg" alt="Inglés">
                <span>Inglés: Intermedio</span>
            </li>
        </ul>
     </div>
   </div>
</template>
-->
<style scoped>
.skills-contenedor {
    padding: 2rem;
    background: linear-gradient(-45deg, #021526, #03346E, #6EACDA, #E2E2B6);
}

.skills-categoria {
    margin-bottom: 20px;
}

.skills-categoria h3 {
    display: flex;
    justify-content: left;
    margin-bottom: 10px;
    font-size: 1.5em;
    color: aliceblue;
    font-size: 1.5em;
    font-weight: bold;
}

.skills {
    display: flex;
    justify-content: space-evenly;
    flex-wrap: wrap;
    gap: 20px;
}

.skill {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;
    background-color: rgba(241, 245, 243, 0.856);
    padding: 0.3em;
    border-radius: 8px;
    box-shadow: 0px 4px 12px rgba(2, 151, 151, 0.963);
    flex: 1 1 200px;
    max-width: 250px;
}

.skill:hover {
    background-color: rgba(2, 151, 151, 0.963);
}

.skill img {
    width: 35px;
    height: 35px;
}

.skill span {
    font-size: 1em;
    color: #333;
}

.skill:hover {
    font-size: 1.3em;
    transition: 2s ease;
}

@media (max-width: 768px) {
    .skills-categoria h3 {
        justify-content: center;
    }

    .skill {
        justify-content: center;
    }
}
</style>