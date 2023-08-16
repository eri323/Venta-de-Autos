<template>
  <div class="barras">
    <div class="barra1">

      <h2>*Nombre de la tienda*</h2>


    </div>
    <div class="barra2">
      <img src="https://o.remove.bg/downloads/ad6b86be-0ccf-483b-a90d-473a77af4449/redbo-cart-removebg-preview.png" alt=""
        class="img">
    </div>
  </div>

  <div class="B">
    <div class="Buscar">
      <input type="text" placeholder="Busqueda avanzada">

    </div>
    <div class="carros">
      <div v-for=" (tarje, i ) in tarjetas" :key="i" class="tarjeta">
        <div class="divimg">
          <img :src="tarje.img" alt="img" id="carrostarjetas">
        </div>
        <h1 class="modelo" >{{ tarje.Modelo }}</h1>
        <div class="textos">
          <h1 class="km" id="datos">{{ tarje.Kilometraje }}</h1>
          <h1 class="año" id="datos">{{ tarje.Año }}</h1>
          <h1 class="placa" id="datos">{{ tarje.Placa }}</h1>
        </div>
        <div class="botones" >
          <button class="boto1" id="boto">Comprar</button>
          <button class="boto2" id="boto">Mas info</button>
        </div>
      </div>
    </div>
  </div>
</template> 

<script setup>
import { ref } from "vue";
const tarjetas = ref([
  { Kilometraje: "10.000 Km", Modelo: "Audi R8", Año: 2020, Placa: "ABC-201", img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQKM7E2zDI8453KjKfJWaT3ZKjZNYz_9uv85yEwWnrP35cXiQiXKgEArcalLDAY6xSx0Vg&usqp=CAU" },
  { Kilometraje: "22.000 Km", Modelo: "BMW", Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/4c299415-f710-45e8-8173-9006c042aaf2/mX2lwI-removebg-preview.png" },
  { Kilometraje: "10.000 Km", Modelo: "Chevrolet Sprk", Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/86844b9f-5b38-4e3f-af3a-4204748838fe/RT_V_00651e33182149d2a79512a957703e6e-removebg-preview.png" },
  { Kilometraje: "10.000 Km", Modelo: "Toyota Fourtuner", Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/3464cdf9-18e2-4546-b451-a9044c5cb17e/AUDI-A3-LOS-COCHES-removebg-preview.png" },
  { Kilometraje: "22.000 Km", Modelo: "Nissan Patrol", Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/3464cdf9-18e2-4546-b451-a9044c5cb17e/AUDI-A3-LOS-COCHES-removebg-preview.png" },
  { Kilometraje: "10.000 Km", Modelo: "Mazada 3", Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/3464cdf9-18e2-4546-b451-a9044c5cb17e/AUDI-A3-LOS-COCHES-removebg-preview.png" },
  { Kilometraje: "10.000 Km", Modelo: "Skopa", Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/3464cdf9-18e2-4546-b451-a9044c5cb17e/AUDI-A3-LOS-COCHES-removebg-preview.png" },
  { Kilometraje: "22.000 Km", Modelo: "Ford Scape", Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/3464cdf9-18e2-4546-b451-a9044c5cb17e/AUDI-A3-LOS-COCHES-removebg-preview.png" },
  { Kilometraje: "10.000 Km", Modelo: "Ford Raptor", Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/3464cdf9-18e2-4546-b451-a9044c5cb17e/AUDI-A3-LOS-COCHES-removebg-preview.png" },
  { Kilometraje: "10.000 Km", Modelo: "Renault 12", Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/3464cdf9-18e2-4546-b451-a9044c5cb17e/AUDI-A3-LOS-COCHES-removebg-preview.png" },
  { Kilometraje: "22.000 Km", Modelo: "Renault Duster", Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/3464cdf9-18e2-4546-b451-a9044c5cb17e/AUDI-A3-LOS-COCHES-removebg-preview.png" },
  { Kilometraje: "10.000 Km", Modelo: "Volkswagen Golf", Año: 2020, Placa: "ABC-201", img: "https://th.bing.com/th/id/R.adecd608f2b2534a41d4ffc7776a4734?rik=rsogiHGjUIvIXg&pid=ImgRaw&r=0" },
])



</script>

<style scoped>
.barras {
  display: flex;
  flex-direction: column;
}

.barra1 {
  background-color: #1d1d4f;
  padding: 20px;
  text-align: center;
}

.barra2 {
  background-color: #32329f;
  display: flex;
  padding: 10px 20px;
  align-items: center;
  text-align: center;

  color: #EEEEEE;
  justify-content: space-around;
}
.divimg{
  display: flex;
  justify-content: center;
}
.B {
  display: flex;
}

.Buscar {
  background-color: #9a9a9a;
  padding: 10px;
}

.img {
  width: 50px;
}
.botones{
  display: flex;
  justify-content: space-around;
}
#boto {
  padding: 10px;
  border-radius: 15px;
  background-color: #ffffff;
  border: none;
}

#boto:hover {
  background-color: #8080d5;
  border: 3px solid #1d1d4f;
}

.carros {

  padding: 20px 200px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 15px;
}

.textos {
  display: flex;
  gap: 10px;
  justify-content: space-around;
}

#carrostarjetas {
  width: 200px;
}

.tarjeta {

  background-color: #e6f4ff;

  border: 3px solid #727272;
  display: flex;
  flex-direction: column;
  gap: 15px;
  padding: 25px;
  font-size: 7px;
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
#datos {
  color: rgb(0, 0, 0);
  background-color: white;
  padding: 5px;
  border-radius: 15px;
  border: none;
}</style>