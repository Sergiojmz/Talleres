<template>
    <div class="contenedor">

        <div v-for="pais in paises" :key="pais.id" class="carta">
            <img :src="require(`@/assets/${pais.url}`)" alt="" class="imagen-contenedor">
            <div @click="mostrarPais(pais.nombre)" class="nombre-contenedor">{{ pais.nombre }}</div>
            <div v-if="pais.habitantes > tazaHabitantesMinima" class="habitantes-contenedor verde">{{ pais.habitantes }}</div>
            <div v-else class="habitantes-contenedor rojo">{{ pais.habitantes }}</div>
        </div>

      
    </div>
</template>

<script>
export default {
    name: 'MiCards',

    //   Aquí inicializo mis variables
    data() {
    return {
        tazaHabitantesMinima: 10000000,
        paises: [
            {
                id: 1,
                nombre: "NORUEGA",
                url: "paisaje-1.png",
                habitantes: 9567890
            },
            {
                id: 2,
                nombre: "DINAMARCA",
                url: "paisaje-2.jpg",
                habitantes: 11567890
            },
            {
                id: 3,
                nombre: "CANADA",
                url: "paisaje-3.jpg",
                habitantes: 16590890
            },
            {
                id: 4,
                nombre: "SUIZA",
                url: "suiza.jpg",
                habitantes: 8000000
            },
            {
                id: 5,
                nombre: "PERU",
                url: "peru.jpg",
                habitantes: 33000000
            },
            {
                id: 6,
                nombre: "COLOMBIA",
                url: "colommbia.jpg",
                habitantes: 52000000
            },
            {
                id: 7,
                nombre: "VENEZUELA",
                url: "venezzuela.jpg",
                habitantes: 28000000
            },
            {
                id: 8,
                nombre: "REPUBLICA DOMINICANA",
                url: "republica.jpg",
                habitantes: 11000000
            },
            {
                id: 9,
                nombre: "CUBA",
                url: "cubba.jpg",
                habitantes: 11300000
            },
            {
                id: 10,
                nombre: "PUERTO RICO",
                url: "puerto.jpg",
                habitantes: 3200000
            },
        ]
    }
},

    //Aquí van las funciones
    methods: {
        mostrarPais(pais) {
            alert("CLIC EN EL PAIS " + pais);
            // alert("HOLA " + this.nombre);
        }
    },

    //INICIALIZADOR
    created() {
        // this.hola();
    }
}
</script>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.contenedor {
    display: grid;
    grid-template-columns: repeat(6, 1fr); 
    grid-template-rows: repeat(2, 1fr);   
    gap: 2rem;
    justify-items: center;
    align-items: center;
    width: 100%;
    max-width: 1300px;
    margin: 0 auto;
    min-height: 650px;
}

.carta {
    width: 220px;
    height: 320px;
    box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
    border-radius: 5% 5% 0 0;
    margin-bottom: 0;
}

@media (max-width: 1200px) {
    .contenedor {
        grid-template-columns: repeat(3, 1fr);
        grid-template-rows: repeat(4, 1fr);
    }
    .carta {
        width: 160px;
        height: 240px;
    }
}

@media (max-width: 800px) {
    .contenedor {
        grid-template-columns: repeat(2, 1fr);
        grid-template-rows: repeat(5, 1fr);
    }
    .carta {
        width: 140px;
        height: 200px;
    }
}

.imagen-contenedor {
    width: 100%;
    height: 80%;
    margin: 0;
    object-fit: cover;
    object-position: center center;
    border-radius: 5% 5% 0 0;
}

.imagen-contenedor:hover {
    background-image: rgba(0, 0, 0, 0.6);
    cursor: pointer;
}

.nombre-contenedor {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 10%;
    background-color: darkgreen;
    color: white;
    cursor: pointer;
}

.habitantes-contenedor {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 10%;
    color: white;
}

.verde{
    background-color: rgb(0, 69, 0);
}

.rojo{
     background-color: rgb(241, 5, 5);
}
</style>
