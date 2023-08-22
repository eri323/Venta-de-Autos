<template>
  <div class="barras">
    <div class="barra1">
      <div class="Pbarra">
        <h1 class="titulo">Ka-Chow</h1>
      </div>
      <div class="textoencacontainer">
        <div class="textoenca">
          <p class="intro">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Architecto,
            quas, laborum sequi iure quod officia doloribus earum consectetur
            praesentium quam eius reiciendis magnam sapiente beatae quia
            provident. Asperiores, nostrum laudantium.
          </p>
        </div>
      </div>
    </div>
    <div class="barra2">
      <div class="barraopc">
        <div class="opcinicio" id="opcs">
          <h4>Inicio</h4>
        </div>
        <div class="opcbuscar" id="opcs">
          <h4>Buscar</h4>
        </div>
        <div class="opcvender" id="opcs">
          <h4>Vender</h4>
        </div>
        <div class="opcayuda" id="opcs">
          <h4>Ayuda</h4>
        </div>
      </div>
      <div class="barraimg">
        <button
          data-bs-toggle="modal"
          data-bs-target="#exampleModal"
          class="botoncarrito"
        >
          <img src="./img/carrito.png" alt="" class="img" />
        </button>
      </div>
      <div
        class="modal"
        id="exampleModal"
        tabindex="-1"
        aria-labelledby="exampleModalLabel"
        aria-hidden="true"
      >
        <div class="modal-dialog">
          <div class="modal-content">
            <div class="modal-header">
              <h1 class="modal-title fs-5" id="exampleModalLabel">
                Nuevo registro
              </h1>
              <button
                type="button"
                class="btn-close"
                data-bs-dismiss="modal"
                aria-label="Close"
              ></button>
            </div>
            <div class="modal-body" ref="modalbody">
              <table class="table">
                <thead class="thead">
                  <tr>
                    <th style="border-top-left-radius: 25px">Vehiculo</th>
                    <th>Precio</th>
                    <th>Modelo</th>
                    <th style="border-top-right-radius: 25px">Opciones</th>
                  </tr>
                </thead>
                <tbody class="tbody">
                  <tr v-for="(tarjec, i) in TarjetasCompradas" :key="i">
                    <td>
                      <img :src="tarjec.img" alt="" style="width: 100px" />
                    </td>
                    <td>{{ tarjec.Precio }}</td>
                    <td>{{ tarjec.Modelo }}</td>
                    <td>
                      <button @click="Eliminar(i)" class="botonelimminar">
                        ❌
                      </button>
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>

            <div class="modal-footer"></div>
          </div>
        </div>
      </div>
    </div>
    <div class="barra3">
      <h1>Catalogo de autos</h1>
    </div>
  </div>

  <div class="B">
    <div class="carros">
      <div v-for="(tarje, i) in tarjetas" :key="i" class="tarjeta">
        <div class="divimg">
          <img :src="tarje.img" alt="img" id="carrostarjetas" />
        </div>
        <h5 class="modelo">{{ tarje.Modelo }}</h5>
        <h5 class="precio">{{ tarje.Precio }}</h5>
        <div class="textos">
          <h5 class="km" id="datos">{{ tarje.Kilometraje }}</h5>
          <h5 class="año" id="datos">{{ tarje.Año }}</h5>
          <h5 class="placa" id="datos">{{ tarje.Placa }}</h5>
        </div>
        <div class="botones">
          <button class="boto1" id="boto" @click="añadirP(i)">Comprar</button>
          <button
            class="boto2"
            id="boto"
            type="button"
            data-bs-toggle="modal"
            data-bs-target="#staticBackdrop"
            @click="añadirinfo(i)"
          >
            Mas info
          </button>
        </div>

        <div
          class="modal fade"
          id="staticBackdrop"
          data-bs-backdrop="static"
          data-bs-keyboard="false"
          tabindex="-1"
          aria-labelledby="staticBackdropLabel"
          aria-hidden="true"
        >
          <div class="modal-dialog">
            <div class="modal-content">
              <div class="modal-header">
                <h1 class="modal-title fs-5" id="staticBackdropLabel">
                  Informacion completa
                </h1>
                <button
                  type="button"
                  class="btn-close"
                  data-bs-dismiss="modal"
                  aria-label="Close"
                ></button>
              </div>
              <div class="modal-body">
                <div id="carouselExampleDark" class="carousel carousel-dark slide">
                  <div class="carousel-indicators">
                    <button type="button" data-bs-target="#carouselExampleDark" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
                    <button type="button" data-bs-target="#carouselExampleDark" data-bs-slide-to="1" aria-label="Slide 2"></button>
                    <button type="button" data-bs-target="#carouselExampleDark" data-bs-slide-to="2" aria-label="Slide 3"></button>
                  </div>
                  <div class="carousel-inner">
                    <div class="carousel-item active" >
                      <img src="./img/image-removebg-preview (29).png" class="d-block w-100" alt="...">
                      
                    </div>
                    <div class="carousel-item" >
                      <img src="./img/car-mercedes-benz-mercedes-amg-mercedes-amg-gt-wallpaper-preview.jpg" class="d-block w-100" alt="...">
                     
                    </div>
                    <div class="carousel-item">
                      <img src="./img/fondo.png" class="d-block w-100" alt="...">
                  
                    </div>
                  </div>
                  <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleDark" data-bs-slide="prev">
                    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                    <span class="visually-hidden">Previous</span>
                  </button>
                  <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleDark" data-bs-slide="next">
                    <span class="carousel-control-next-icon" aria-hidden="true"></span>
                    <span class="visually-hidden">Next</span>
                  </button>
                </div>
                <div class="containerinfomodal">
                  <div class="containerinfotabla">
                    <h2>Caracteristicas</h2>
                    <table v-for=" ( tarjeta, i ) in TarjetasInfo" :key="i" class="tableinfo">
                      <tr>
                        <td style="border-top-left-radius: 15px; border-top-right-radius: 15px;">Modelo: {{tarjeta.Modelo}}</td>
                      </tr>
                      <tr>
                        <td>Kilometraje: {{tarjeta.Kilometraje}}</td>
                      </tr>
                      <tr>
                        <td>Año: {{tarjeta.Año}}</td>
                      </tr>
                      <tr>
                        <td>Placa: {{tarjeta.Placa}}</td>
                      </tr>
                      <tr>
                        <td>Combustible: {{tarjeta.Combustible}}</td>
                      </tr>
                      <tr>
                        <td>Motor: {{tarjeta.Motor}}</td>
                      </tr>
                     <tr >
                      <td style="border-bottom-left-radius: 15px; border-bottom-right-radius: 15px;">Transmision: {{tarjeta.Transmision}}</td>
                     </tr>
                    </table>
                  </div>
                  <div class="containerinfodescripcion">
                    <h2>Descripción</h2>
                    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Obcaecati aliquid, incidunt dolore animi itaque fugit quas id tempora soluta veritatis qui dolorem commodi eius quam, voluptas, illo corporis beatae et?</p>
                  </div>
                </div>
                
              </div>
              <div class="modal-footer">
                <button
                  type="button"
                  class="btn btn-secondary"
                  data-bs-dismiss="modal"
                  @click="limpiarModal(i)"
                >
                  Close
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
const tarjetas = ref([
  {
    Precio: "280.000.000",
    Kilometraje: "10.000 Km",
    Modelo: "Audi R8",
    Año: 2020,
    Placa: "ABC-201",
    Combustible: "Gasolina",
    Motor: "V6 3.5 CC",
    Transmision :"Automatica",
    img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQKM7E2zDI8453KjKfJWaT3ZKjZNYz_9uv85yEwWnrP35cXiQiXKgEArcalLDAY6xSx0Vg&usqp=CAU",
  },

  {
    Precio: "280.000.000",
    Kilometraje: "22.000 Km",
    Modelo: "BMW",
    Año: 2020,
    Placa: "ABC-201",
    img: "https://www.bmw.com.co/content/dam/bmw/common/all-models/m-series/x6m/2019/inspire/bmw-x6-m-inspire-mg-competition-desktop-02.jpg",
  },
  {
    Precio: "280.000.000",
    Kilometraje: "10.000 Km",
    Modelo: "Chevrolet Spark",
    Año: 2020,
    Placa: "ABC-201",
    img: "https://img.autosblogmexico.com/2019/12/12/jy4ZkaKS/chevrolet-spark-resea-01-7402.png",
  },
  {
    Precio: "280.000.000",
    Kilometraje: "10.000 Km",
    Modelo: "Toyota Fourtuner",
    Año: 2017,
    Placa: "ABC-201",
    img: "https://www.valorenlinea.com/sn_fotos/auto_53301_img_344984.jpg",
  },
  {
    Precio: "280.000.000",
    Kilometraje: "22.000 Km",
    Modelo: "Nissan Patrol",
    Año: 2020,
    Placa: "ABC-201",
    img: "https://http2.mlstatic.com/D_NQ_NP_773796-MCO50452263450_062022-W.webp",
  },
  {
    Precio: "280.000.000",
    Kilometraje: "10.000 Km",
    Modelo: "Mazda 3",
    Año: 2019,
    Placa: "ABC-201",
    img: "https://th.bing.com/th/id/OIP.1MBvI3Kx7WtwNYtf-XC4mAHaE8?w=249&h=180&c=7&r=0&o=5&dpr=1.3&pid=1.7",
  },
  {
    Precio: "280.000.000",
    Kilometraje: "10.000 Km",
    Modelo: "Skopa",
    Año: 2000,
    Placa: "ABC-201",
    img: "https://img.autoabc.lv/Skoda-Octavia/Skoda-Octavia_2000_Hecbeks_234550528.jpg",
  },
  {
    Precio: "280.000.000",
    Kilometraje: "22.000 Km",
    Modelo: "Ford Escape",
    Año: 2016,
    Placa: "ABC-201",
    img: "https://th.bing.com/th/id/OIP.MA4Ne4km-1kf7BwChNTEDQHaFP?pid=ImgDet&rs=1",
  },
  {
    Precio: "280.000.000",
    Kilometraje: "10.000 Km",
    Modelo: "Ford Raptor",
    Año: 2020,
    Placa: "ABC-201",
    img: "https://th.bing.com/th/id/R.98e2bac7c17fe163259e44a0f40edd42?rik=8pRDghF967DFxg&riu=http%3a%2f%2fpictures.topspeed.com%2fIMG%2fcrop%2f201601%2f2017-ford-f-150-raptor-6_1600x0w.jpg&ehk=bQBVHrsEXP02D550iEERzTYXNmnh1GB4e%2bXRThS6esI%3d&risl=&pid=ImgRaw&r=0",
  },
  {
    Precio: "280.000.000",
    Kilometraje: "10.000 Km",
    Modelo: "Renault 12",
    Año: 2020,
    Placa: "ABC-201",
    img: "https://th.bing.com/th/id/OIP.Wk1MGjaA4vqR7FX8xI1HswHaDq?pid=ImgDet&rs=1",
  },
  {
    Precio: "280.000.000",
    Kilometraje: "22.000 Km",
    Modelo: "Renault Duster",
    Año: 2020,
    Placa: "ABC-201",
    img: "https://th.bing.com/th/id/OIP.rLINBQsFnz656Jvp7lhobgHaEK?w=297&h=180&c=7&r=0&o=5&dpr=1.3&pid=1.7",
  },
  {
    Precio: "280.000.000",
    Kilometraje: "10.000 Km",
    Modelo: "Volkswagen Golf",
    Año: 2020,
    Placa: "ABC-201",
    img: "https://th.bing.com/th/id/R.adecd608f2b2534a41d4ffc7776a4734?rik=rsogiHGjUIvIXg&pid=ImgRaw&r=0",
  },
]);

const TarjetasCompradas = ref([]);

const TarjetasInfo = ref([]);

let tarjetaSeleccionada = ref(null);

function añadirP(index) {
  let tarjetaSeleccionada = tarjetas.value[index]; // Llamar la tarjeta seleccionada
  TarjetasCompradas.value.push(tarjetaSeleccionada); // Agrega la tarjeta al carrito  
}
function añadirinfo(index) {
  let tarjetaSeleccionada = tarjetas.value[index]; // Llamar la tarjeta seleccionada
  TarjetasInfo.value.push(tarjetaSeleccionada);
}
function Eliminar(i) {
  TarjetasCompradas.value.splice(i, 1);
}

function limpiarModal(i) {
  TarjetasInfo.value.splice(i, 1);
}
</script>

<style scoped>
.titulo {
  color: white;
  display: flex;
  justify-content: center;
}
tr:nth-child(odd) {
  background-color: #a0f1ff;
}
.containerinfomodal{
  display: flex;
  justify-content: space-around;
  align-items: baseline;
}
.containerinfotabla{
  text-align: center;
  display: grid;
  gap: 10px;
}
.containerinfodescripcion{
  text-align: center;
  padding: 25px;
  display: flex;
  flex-direction: column;
  gap: 10px;
}
.intro {
  font-size: 25px;
  width: 300px;
}
.Pbarra {
  font-size: 25px;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}
.table {
  border-collapse: collapse;
}
.thead,
th {
  background-color: #3d5af1;
  color: white;
  border-bottom: 3px solid black;
}
.textoenca {
  color: white;
}
.tbody,
tr,
td {
  padding: 10px;
  text-align: center;
}
.textoencacontainer {
  display: flex;
  justify-content: end;
  text-align: right;
  padding: 55px 25px 0px 0px;
}
.barras {
  display: flex;
  flex-direction: column;
}
.modal {
  color: black;
}
.barra1 {
  background-color: #1d1d4f;
  padding: 20px;
  display: flex;
  flex-direction: column;
  background-image: url(./img/balco1.jpg);
  height: 80vh;
  background-size: cover;
  object-fit: cover;
  background-repeat: no-repeat;
}

.barra2 {
  background-color: #3d5af1;
  color: white;
  display: flex;
  padding: 10px;
  justify-content: space-around;
  align-items: center;
}

.barra3 {
  background-color: #e2f3f5;
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
  color: #e2f3f5;
}

#opcs,
h4 {
  font-size: 20px;
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
.botoncarrito {
  background-color: #3d5af1;
  border: none;
}
.botoncarrito:hover {
  border-bottom: rgb(0, 0, 0) 3px solid;
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
  font-family: Verdana, Geneva, Tahoma, sans-serif;
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
  border: 2px solid #3d5af1;
  transform: scale(1, 1);
}
.botonelimminar:hover {
  background-color: rgb(255, 179, 179);
  transform: scale(1.1);
}

.botonelimminar {
  border: none;
  background-color: rgb(255, 215, 215);
  border-radius: 10px;
  padding: 5px;
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
  background-color: #e2f3f5;

  border: 3px solid #000000;
  display: flex;
  flex-direction: column;
  gap: 15px;
  padding: 25px;
  font-size: 15px;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}

#datos {
  color: rgb(0, 0, 0);
  background-color: white;
  padding: 5px;
  border-radius: 15px;
  border: none;
}
.modal-body{
  display: flex;
  flex-direction: column;
  align-items: center;
}
.carousel-inner{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  width: 400px;
  height: 300px;
  border-radius: 25px;
  overflow: hidden;

  
}
.carousel-item, img{
  width: 400px;
  height: 100%;
  object-fit: cover;
  border-radius: 25px;
  position: relative;
}
.slider{
  width: 300%;
  height: 100%;
  display: flex;
 
}
.slider-section{
  width: calc(100%/3);
  height: 100%;
}

.btn-left{
  display: flex;
  position: absolute;
  top: 21%;
  font-size: 1.5rem;
  background-color: transparent;
  border-radius: 50%;
  padding: 5px;
  font-weight: 600;
  cursor: pointer;
  color: #ffffff81;
  transform: translate(0,-30%);
  transition: .5s ease;
  user-select: none;
  left: 10px;
}
.btn-right{
  
  display: flex;
  position: absolute;
  right: 10px;
  top: 21%;
  font-size: 1.5rem;
  background-color: transparent;
  border-radius: 50%;
  padding: 5px;
  font-weight: 600;
  cursor: pointer;
  color: #ffffff81;
  transform: translate(0,-30%);
  transition: .5s ease;
  user-select: none;
}
.btn-left:hover{
  background-color: #333333d4;
  color: #fff;
}
.btn-right:hover{
  background-color: #333333d4;
  color: #fff;
}
</style>
