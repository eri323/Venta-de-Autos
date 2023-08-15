<template>
  <div class="barra">

    <h2>*Nombre de la tienda*</h2>
    <h2>Buscar</h2>

    <img src="./img/image-removebg-preview (29).png" alt="" class="img">

    <h2></h2>

  </div>
  <div class="carros">
    <div v-for=" (tarje, i ) in tarjetas" :key="i" class="tarjeta">
      <div>
        <img :src="tarje.img" alt="img" id="carrostarjetas">
      </div>
      <h1 class="km">{{ tarje.Modelo }}</h1>
      <div class="textos">
        <h1 class="km">{{ tarje.Kilometraje }}</h1>
        <h1>{{ tarje.Año }}</h1>
        <h1>{{ tarje.Placa }}</h1>
      </div>
      <div class="boton" style="display: flex; justify-content: center;">
        <button style="padding: 10px; border-radius: 15px; background-color: #ffffff;" >Comprar</button>
      </div>
    </div>
  </div>
</template> 

<script setup>
import { ref } from "vue";
const tarjetas = ref([
  { Kilometraje: "10.000", Modelo: "Audi R8", Año: 2020, Placa:"ABC-201", img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQKM7E2zDI8453KjKfJWaT3ZKjZNYz_9uv85yEwWnrP35cXiQiXKgEArcalLDAY6xSx0Vg&usqp=CAU" },
  { Kilometraje: "22.000", Modelo: "BMW", Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/4c299415-f710-45e8-8173-9006c042aaf2/mX2lwI-removebg-preview.png" },
  { Kilometraje: "10.000", Modelo: 2020, Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/86844b9f-5b38-4e3f-af3a-4204748838fe/RT_V_00651e33182149d2a79512a957703e6e-removebg-preview.png" },
  { Kilometraje: "10.000", Modelo: 2020, Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/3464cdf9-18e2-4546-b451-a9044c5cb17e/AUDI-A3-LOS-COCHES-removebg-preview.png" },
  { Kilometraje: "22.000", Modelo: 2022, Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/3464cdf9-18e2-4546-b451-a9044c5cb17e/AUDI-A3-LOS-COCHES-removebg-preview.png" },
  { Kilometraje: "10.000", Modelo: 2020,   Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/3464cdf9-18e2-4546-b451-a9044c5cb17e/AUDI-A3-LOS-COCHES-removebg-preview.png" },
  { Kilometraje: "10.000", Modelo: 2020, Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/3464cdf9-18e2-4546-b451-a9044c5cb17e/AUDI-A3-LOS-COCHES-removebg-preview.png" },
  { Kilometraje: "22.000", Modelo: 2022, Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/3464cdf9-18e2-4546-b451-a9044c5cb17e/AUDI-A3-LOS-COCHES-removebg-preview.png" },
  { Kilometraje: "10.000", Modelo: 2020, Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/3464cdf9-18e2-4546-b451-a9044c5cb17e/AUDI-A3-LOS-COCHES-removebg-preview.png" },
  { Kilometraje: "10.000", Modelo: 2020, Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/3464cdf9-18e2-4546-b451-a9044c5cb17e/AUDI-A3-LOS-COCHES-removebg-preview.png" },
  { Kilometraje: "22.000", Modelo: 2022, Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/3464cdf9-18e2-4546-b451-a9044c5cb17e/AUDI-A3-LOS-COCHES-removebg-preview.png" },
  { Kilometraje: "10.000", Modelo: 2020, Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/3464cdf9-18e2-4546-b451-a9044c5cb17e/AUDI-A3-LOS-COCHES-removebg-preview.png" },
])



</script>

<style scoped>
.barra {
  background-color: #4E4FEB;
  display: flex;
  padding: 20px 20px;
  align-items: center;
  gap: 20px;
  color: #EEEEEE;
  justify-content: space-around;
}

.img {
  width: 50px;
}
#boto:hover {
  background-color: rgb(0, 0, 0);
}
.carros {

  padding: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 15px;
}
.textos{
  display: flex;
  gap: 10px;
  justify-content: space-around;
}
#carrostarjetas {
  width: 200px;
}

.tarjeta {
  
  background-color: #93ceff;
  border-radius: 20px;
  border: 3px solid #4E4FEB;
  display: grid;
  gap: 15px;
  padding: 25px;
  font-size: 7px;
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}

.km {
  color: rgb(0, 0, 0);
}</style>