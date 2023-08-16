<template>
  <div class="barras">
    <div class="barra1">
      <div class="Pbarra">
        <h1 class="titulo">Ka-Chow</h1>
        <div class="barraopc">
          <div class="opcinicio" id="opcs">
            <h1>Inicio</h1>
          </div>
          <div class="opcbuscar" id="opcs">
            <h1>Buscar</h1>
          </div>
          <div class="opcvender" id="opcs">
            <h1>Vender</h1>
          </div>
          <div class="opcayuda" id="opcs">
            <h1>Ayuda</h1>
          </div>
        </div>
        <div class="barraimg">
          <img src="./img/carrito.png" alt="" class="img">
        </div>
      </div>
      
     <!--  <div class="barra11">
        <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Doloremque repellat rerum odio corrupti quidem
          laudantium suscipit aspernatur ab fugit, unde vitae eum veritatis, officia distinctio dolorem nesciunt quos
          aliquam! Cupiditate?</p>
      </div> -->
    </div>

    <div class="barra3">
      <h1>Catalogo de autos</h1>
    </div>
  </div>

  <div class="B">

    <div class="carros">
      <div v-for=" (tarje, i ) in tarjetas" :key="i" class="tarjeta">
        <div class="divimg">
          <img :src="tarje.img" alt="img" id="carrostarjetas">
        </div>
        <h1 class="modelo">{{ tarje.Modelo }}</h1>
        <div class="textos">
          <h1 class="km" id="datos">{{ tarje.Kilometraje }}</h1>
          <h1 class="año" id="datos">{{ tarje.Año }}</h1>
          <h1 class="placa" id="datos">{{ tarje.Placa }}</h1>
        </div>
        <div class="botones">
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
  { Kilometraje: "22.000 Km", Modelo: "BMW", Año: 2020, Placa: "ABC-201", img: "https://www.bmw.com.co/content/dam/bmw/common/all-models/m-series/x6m/2019/inspire/bmw-x6-m-inspire-mg-competition-desktop-02.jpg" },
  { Kilometraje: "10.000 Km", Modelo: "Chevrolet Spark", Año: 2020, Placa: "ABC-201", img: "https://img.autosblogmexico.com/2019/12/12/jy4ZkaKS/chevrolet-spark-resea-01-7402.png" },
  { Kilometraje: "10.000 Km", Modelo: "Toyota Fourtuner", Año: 2017, Placa: "ABC-201", img: "https://www.valorenlinea.com/sn_fotos/auto_53301_img_344984.jpg" },
  { Kilometraje: "22.000 Km", Modelo: "Nissan Patrol", Año: 2020, Placa: "ABC-201", img: "https://http2.mlstatic.com/D_NQ_NP_773796-MCO50452263450_062022-W.webp" },
  { Kilometraje: "10.000 Km", Modelo: "Mazda 3", Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/3464cdf9-18e2-4546-b451-a9044c5cb17e/AUDI-A3-LOS-COCHES-removebg-preview.png" },
  { Kilometraje: "10.000 Km", Modelo: "Skopa", Año: 2000, Placa: "ABC-201", img: "https://img.autoabc.lv/Skoda-Octavia/Skoda-Octavia_2000_Hecbeks_234550528.jpg" },
  { Kilometraje: "22.000 Km", Modelo: "Ford Scape", Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/3464cdf9-18e2-4546-b451-a9044c5cb17e/AUDI-A3-LOS-COCHES-removebg-preview.png" },
  { Kilometraje: "10.000 Km", Modelo: "Ford Raptor", Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/3464cdf9-18e2-4546-b451-a9044c5cb17e/AUDI-A3-LOS-COCHES-removebg-preview.png" },
  { Kilometraje: "10.000 Km", Modelo: "Renault 12", Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/3464cdf9-18e2-4546-b451-a9044c5cb17e/AUDI-A3-LOS-COCHES-removebg-preview.png" },
  { Kilometraje: "22.000 Km", Modelo: "Renault Duster", Año: 2020, Placa: "ABC-201", img: "https://o.remove.bg/downloads/3464cdf9-18e2-4546-b451-a9044c5cb17e/AUDI-A3-LOS-COCHES-removebg-preview.png" },
  { Kilometraje: "10.000 Km", Modelo: "Volkswagen Golf", Año: 2020, Placa: "ABC-201", img: "https://th.bing.com/th/id/R.adecd608f2b2534a41d4ffc7776a4734?rik=rsogiHGjUIvIXg&pid=ImgRaw&r=0" },
])



</script>

<style scoped>
.titulo {
  color: white;

}
.Pbarra{
  
}
.barras {
  display: flex;
  flex-direction: column;
}

.barra1 {
  background-color: #1d1d4f;
  padding: 20px;
  text-align: center;
  background-image: url(./img/fondo.png);
  height: 50vh;
  background-size: cover;
  object-fit: cover;
  background-repeat: no-repeat;
}

.barra11 {
  color: white;
  width: 200px;
  margin-left: 5%;
}

.barra3 {
  margin-top: 3%;
  background-color: #E2F3F5;
  padding: 25px;
  display: flex;
  justify-content: center;
  border-top: 3px solid black;
  border-bottom: 3px solid black;
}

.barraopc {
  display: flex;
  justify-content: space-around;
  gap: 35px;
  color: #E2F3F5;
  font-size: 7px;
}

.divimg {
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
  width: 35px;

}

.botones {
  display: flex;
  justify-content: space-around;
}

#opcs {
  padding: 10px;
  cursor: pointer;
}

#opcs:hover {
  border-bottom: rgb(0, 0, 0) 3px solid;
}

#boto {
  padding: 10px;
  border-radius: 15px;
  background-color: #ffffff;
  border: none;
  cursor: pointer;
}

#boto:hover {

  border: 2px solid #3D5AF1;
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
  height: 130px;
}

.tarjeta {

  background-color: #E2F3F5;

  border: 3px solid #000000;
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
}
</style>