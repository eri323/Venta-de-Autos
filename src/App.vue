<template>
  <div class="barraimg">
    <button
      data-bs-toggle="modal"
      data-bs-target="#exampleModal"
      class="opcsboton"
    >
      <img
        src="https://th.bing.com/th/id/R.d01f6a524827d080143ba7b6a4fd2961?rik=csLHhRB6q%2f4LMg&pid=ImgRaw&r=0"
        alt=""
        class="img"
      />
    </button>
  </div>
  <div class="barras">
    <div class="barra1">
      <div class="Pbarra">
        <h1 class="titulo">Fast and safe</h1>
      </div>
      <div class="textoencacontainer">
        
      </div>
    </div>
    <div class="barra2">
      <div class="barraopc">
        <!-- <div class="container">
          <input
            type="text"
            name="text"
            class="input"
            required=""
            placeholder="Type to search..."
          />
          <div class="icon">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="ionicon"
              viewBox="0 0 512 512"
            >
              <title>Search</title>
              <path
                d="M221.09 64a157.09 157.09 0 10157.09 157.09A157.1 157.1 0 00221.09 64z"
                fill="none"
                stroke="currentColor"
                stroke-miterlimit="10"
                stroke-width="32"
              ></path>
              <path
                fill="none"
                stroke="currentColor"
                stroke-linecap="round"
                stroke-miterlimit="10"
                stroke-width="32"
                d="M338.29 338.29L448 448"
              ></path>
            </svg>
          </div>
        </div> -->
      </div>

      <div
        class="modal"
        id="exampleModal"
        tabindex="-1"
        aria-labelledby="exampleModalLabel"
        aria-hidden="true"
      >
        <div class="modal-dialog" id="modal-dialog1">
          <div class="modal-content" id="modal-contentre">
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
            <div class="modal-body" id="modal-body1" ref="modalbody">
              <table class="table">
                <thead class="thead">
                  <tr>
                    <th style="border-top-left-radius: 25px">Vehiculo</th>
                    <th>Cant</th>
                    <th>Subtotal</th>
                    <th>Precio</th>
                    <th style="border-top-right-radius: 25px">Opciones</th>
                  </tr>
                </thead>
                <tbody class="tbody">
                  <tr v-for="(tarjec, i) in TarjetasCompradas" :key="i">
                    <td>
                      <img :src="tarjec.img" alt="" style="width: 100px" />
                    </td>
                    <td>{{ tarjec.cantidadEnCarrito }}</td>
                    <td>
                      ${{
                        tarjec.Precio.toLocaleString("es-ES", {
                          style: "currency",
                          currency: "COP",
                          minimumFractionDigits: 0,
                          maximumFractionDigits: 2,
                        })
                      }}
                    </td>
                    <td>
                      ${{
                        (
                          tarjec.Precio * tarjec.cantidadEnCarrito
                        ).toLocaleString("es-ES", {
                          style: "currency",
                          currency: "COP",
                          minimumFractionDigits: 0,
                          maximumFractionDigits: 2,
                        })
                      }}
                    </td>
                    <td>
                      <button @click="Eliminar(i)" class="botonelimminar">
                        ❌
                      </button>
                    </td>
                  </tr>
                </tbody>
                <tfoot>
                  <tr>
                    <td style="font-weight: bolder; font-size: 20px">
                      Total a pagar:
                    </td>
                    <td>
                      ${{
                        total.toLocaleString("es-ES", {
                          style: "currency",
                          currency: "COP",
                          minimumFractionDigits: 0,
                          maximumFractionDigits: 2,
                        })
                      }}
                    </td>
                  </tr>
                  <tr>
                    <td>
                      <button @click="vaciarCarrito()" class="vaciarCarrito">
                        Vaciar
                      </button>
                    </td>
                  </tr>
                </tfoot>
              </table>
            </div>

            <div class="modal-footer"></div>
          </div>
        </div>
      </div>
    </div>
    <div class="barra3">
      <h4 class="textBarra3">
        Tu próximo viaje comienza aquí, explora en nuestra variedad de autos y
        encuentra la combinación perfecta de estilo y rendimiento
      </h4>
    </div>
  </div>

  <div class="B">
    <div class="carros">
      <div v-for="(tarje, i) in tarjetas" :key="i" class="tarjeta">
        <button
          data-bs-toggle="modal"
          data-bs-target="#staticBackdrop"
          @click="añadirinfo(i)"
          class="botonContainer"
          style="border: 0"
        >
          <div class="divimg">
            <img :src="tarje.img" alt="img" id="carrostarjetas" />
            <h5 class="modelo">{{ tarje.Modelo }}</h5>
          </div>
          <div class="card-social">
            <h5 class="precio card-social__item">
              ${{
                tarje.Precio.toLocaleString("es-ES", {
                  style: "currency",
                  currency: "COP",
                  minimumFractionDigits: 0,
                  maximumFractionDigits: 2,
                })
              }}
            </h5>
            <div class="textos">
              <h5 class="km" id="datos">{{ tarje.Kilometraje }}</h5>
              <h5 class="año" id="datos">{{ tarje.Año }}</h5>
            </div>
          </div>
        </button>
        <div class="botones">
          <div data-tooltip="Price:-$20" class="button">
            <button class="button-wrapper" @click="añadirP(i)">
              <div class="text">Añadir</div>
              <span class="icon">
                <svg
                  viewBox="0 0 16 16"
                  class="bi bi-cart2"
                  fill="currentColor"
                  height="16"
                  width="16"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M0 2.5A.5.5 0 0 1 .5 2H2a.5.5 0 0 1 .485.379L2.89 4H14.5a.5.5 0 0 1 .485.621l-1.5 6A.5.5 0 0 1 13 11H4a.5.5 0 0 1-.485-.379L1.61 3H.5a.5.5 0 0 1-.5-.5zM3.14 5l1.25 5h8.22l1.25-5H3.14zM5 13a1 1 0 1 0 0 2 1 1 0 0 0 0-2zm-2 1a2 2 0 1 1 4 0 2 2 0 0 1-4 0zm9-1a1 1 0 1 0 0 2 1 1 0 0 0 0-2zm-2 1a2 2 0 1 1 4 0 2 2 0 0 1-4 0z"
                  ></path>
                </svg>
              </span>
            </button>
          </div>
        </div>
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
                @click="limpiarModal(i)"
              ></button>
            </div>
            <div class="modal-body" id="modal-body2">
              <div
                id="carouselExampleDark"
                class="carousel carousel-dark slide"
              >
                <div class="carousel-indicators">
                  <button
                    type="button"
                    data-bs-target="#carouselExampleDark"
                    data-bs-slide-to="0"
                    class="active"
                    aria-current="true"
                    aria-label="Slide 1"
                  ></button>
                  <button
                    type="button"
                    data-bs-target="#carouselExampleDark"
                    data-bs-slide-to="1"
                    aria-label="Slide 2"
                  ></button>
                  <button
                    type="button"
                    data-bs-target="#carouselExampleDark"
                    data-bs-slide-to="2"
                    aria-label="Slide 3"
                  ></button>
                </div>
                <div class="carousel-inner"></div>
                <button
                  class="carousel-control-prev"
                  type="button"
                  data-bs-target="#carouselExampleDark"
                  data-bs-slide="prev"
                >
                  <span
                    class="carousel-control-prev-icon"
                    aria-hidden="true"
                  ></span>
                  <span class="visually-hidden">Previous</span>
                </button>
                <button
                  class="carousel-control-next"
                  type="button"
                  data-bs-target="#carouselExampleDark"
                  data-bs-slide="next"
                >
                  <span
                    class="carousel-control-next-icon"
                    aria-hidden="true"
                  ></span>
                  <span class="visually-hidden">Next</span>
                </button>
              </div>
              <div class="containerinfomodal">
                <div class="containerinfotabla">
                  <h2>Caracteristicas</h2>
                  <table
                    v-for="(tarjeta, i) in TarjetasInfo"
                    :key="i"
                    class="tableinfo"
                  >
                    <tr>
                      <td
                        style="
                          border-top-left-radius: 15px;
                          border-top-right-radius: 15px;
                        "
                      >
                        Modelo: {{ tarjeta.Modelo }}
                      </td>
                    </tr>
                    <tr>
                      <td>
                        <span>
                          Precio: ${{
                            tarjeta.Precio.toLocaleString("es-ES", {
                              style: "currency",
                              currency: "COP",
                              minimumFractionDigits: 0,
                              maximumFractionDigits: 2,
                            })
                          }}
                        </span>
                      </td>
                    </tr>
                    <tr>
                      <td>
                        <span>Kilometraje: {{ tarjeta.Kilometraje }}</span>
                      </td>
                    </tr>
                    <tr>
                      <td>
                        <span>Año: {{ tarjeta.Año }}</span>
                      </td>
                    </tr>
                    <tr>
                      <td>
                        <span>Placa: {{ tarjeta.Placa }}</span>
                      </td>
                    </tr>
                    <tr>
                      <td>
                        <span>Combustible: {{ tarjeta.Combustible }}</span>
                      </td>
                    </tr>
                    <tr>
                      <td>
                        <span>Motor: {{ tarjeta.Motor }}</span>
                      </td>
                    </tr>
                    <tr>
                      <td>
                        <span> Color: {{ tarjeta.Color }}</span>
                      </td>
                    </tr>
                    <tr>
                      <td 
                        style="
                          border-bottom-left-radius: 15px;
                          border-bottom-right-radius: 15px;
                        "
                      ><span>
                        Transmision: {{ tarjeta.Transmision }}
                      </span>
                       
                      </td>
                    </tr>
                  </table>
                </div>
                <div class="containerinfodescripcion">
                  <h2>Descripción</h2>
                  <p>
                    Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                    Obcaecati aliquid, incidunt dolore animi itaque fugit quas
                    id tempora soluta veritatis qui dolorem commodi eius quam,
                    voluptas, illo corporis beatae et?
                  </p>
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
  <div class="footer">
    <div class="card">
      <a class="socialContainer containerOne" href="#">
        <svg viewBox="0 0 16 16" class="socialSvg instagramSvg">
          <path
            d="M8 0C5.829 0 5.556.01 4.703.048 3.85.088 3.269.222 2.76.42a3.917 3.917 0 0 0-1.417.923A3.927 3.927 0 0 0 .42 2.76C.222 3.268.087 3.85.048 4.7.01 5.555 0 5.827 0 8.001c0 2.172.01 2.444.048 3.297.04.852.174 1.433.372 1.942.205.526.478.972.923 1.417.444.445.89.719 1.416.923.51.198 1.09.333 1.942.372C5.555 15.99 5.827 16 8 16s2.444-.01 3.298-.048c.851-.04 1.434-.174 1.943-.372a3.916 3.916 0 0 0 1.416-.923c.445-.445.718-.891.923-1.417.197-.509.332-1.09.372-1.942C15.99 10.445 16 10.173 16 8s-.01-2.445-.048-3.299c-.04-.851-.175-1.433-.372-1.941a3.926 3.926 0 0 0-.923-1.417A3.911 3.911 0 0 0 13.24.42c-.51-.198-1.092-.333-1.943-.372C10.443.01 10.172 0 7.998 0h.003zm-.717 1.442h.718c2.136 0 2.389.007 3.232.046.78.035 1.204.166 1.486.275.373.145.64.319.92.599.28.28.453.546.598.92.11.281.24.705.275 1.485.039.843.047 1.096.047 3.231s-.008 2.389-.047 3.232c-.035.78-.166 1.203-.275 1.485a2.47 2.47 0 0 1-.599.919c-.28.28-.546.453-.92.598-.28.11-.704.24-1.485.276-.843.038-1.096.047-3.232.047s-2.39-.009-3.233-.047c-.78-.036-1.203-.166-1.485-.276a2.478 2.478 0 0 1-.92-.598 2.48 2.48 0 0 1-.6-.92c-.109-.281-.24-.705-.275-1.485-.038-.843-.046-1.096-.046-3.233 0-2.136.008-2.388.046-3.231.036-.78.166-1.204.276-1.486.145-.373.319-.64.599-.92.28-.28.546-.453.92-.598.282-.11.705-.24 1.485-.276.738-.034 1.024-.044 2.515-.045v.002zm4.988 1.328a.96.96 0 1 0 0 1.92.96.96 0 0 0 0-1.92zm-4.27 1.122a4.109 4.109 0 1 0 0 8.217 4.109 4.109 0 0 0 0-8.217zm0 1.441a2.667 2.667 0 1 1 0 5.334 2.667 2.667 0 0 1 0-5.334z"
          ></path>
        </svg>
      </a>

      <a class="socialContainer containerTwo" href="#">
        <svg viewBox="0 0 16 16" class="socialSvg twitterSvg">
          <path
            d="M5.026 15c6.038 0 9.341-5.003 9.341-9.334 0-.14 0-.282-.006-.422A6.685 6.685 0 0 0 16 3.542a6.658 6.658 0 0 1-1.889.518 3.301 3.301 0 0 0 1.447-1.817 6.533 6.533 0 0 1-2.087.793A3.286 3.286 0 0 0 7.875 6.03a9.325 9.325 0 0 1-6.767-3.429 3.289 3.289 0 0 0 1.018 4.382A3.323 3.323 0 0 1 .64 6.575v.045a3.288 3.288 0 0 0 2.632 3.218 3.203 3.203 0 0 1-.865.115 3.23 3.23 0 0 1-.614-.057 3.283 3.283 0 0 0 3.067 2.277A6.588 6.588 0 0 1 .78 13.58a6.32 6.32 0 0 1-.78-.045A9.344 9.344 0 0 0 5.026 15z"
          ></path>
        </svg>
      </a>

      <a class="socialContainer containerThree" href="#">
        <svg viewBox="0 0 448 512" class="socialSvg linkdinSvg">
          <path
            d="M100.28 448H7.4V148.9h92.88zM53.79 108.1C24.09 108.1 0 83.5 0 53.8a53.79 53.79 0 0 1 107.58 0c0 29.7-24.1 54.3-53.79 54.3zM447.9 448h-92.68V302.4c0-34.7-.7-79.2-48.29-79.2-48.29 0-55.69 37.7-55.69 76.7V448h-92.78V148.9h89.08v40.8h1.3c12.4-23.5 42.69-48.3 87.88-48.3 94 0 111.28 61.9 111.28 142.3V448z"
          ></path>
        </svg>
      </a>

      <a class="socialContainer containerFour" href="#">
        <svg viewBox="0 0 16 16" class="socialSvg whatsappSvg">
          <path
            d="M13.601 2.326A7.854 7.854 0 0 0 7.994 0C3.627 0 .068 3.558.064 7.926c0 1.399.366 2.76 1.057 3.965L0 16l4.204-1.102a7.933 7.933 0 0 0 3.79.965h.004c4.368 0 7.926-3.558 7.93-7.93A7.898 7.898 0 0 0 13.6 2.326zM7.994 14.521a6.573 6.573 0 0 1-3.356-.92l-.24-.144-2.494.654.666-2.433-.156-.251a6.56 6.56 0 0 1-1.007-3.505c0-3.626 2.957-6.584 6.591-6.584a6.56 6.56 0 0 1 4.66 1.931 6.557 6.557 0 0 1 1.928 4.66c-.004 3.639-2.961 6.592-6.592 6.592zm3.615-4.934c-.197-.099-1.17-.578-1.353-.646-.182-.065-.315-.099-.445.099-.133.197-.513.646-.627.775-.114.133-.232.148-.43.05-.197-.1-.836-.308-1.592-.985-.59-.525-.985-1.175-1.103-1.372-.114-.198-.011-.304.088-.403.087-.088.197-.232.296-.346.1-.114.133-.198.198-.33.065-.134.034-.248-.015-.347-.05-.099-.445-1.076-.612-1.47-.16-.389-.323-.335-.445-.34-.114-.007-.247-.007-.38-.007a.729.729 0 0 0-.529.247c-.182.198-.691.677-.691 1.654 0 .977.71 1.916.81 2.049.098.133 1.394 2.132 3.383 2.992.47.205.84.326 1.129.418.475.152.904.129 1.246.08.38-.058 1.171-.48 1.338-.943.164-.464.164-.86.114-.943-.049-.084-.182-.133-.38-.232z"
          ></path>
        </svg>
      </a>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";
const tarjetas = ref([
  {
    id: 1,
    Precio: 142900000,
    Kilometraje: "34.000 Km",
    Modelo: "Audi Q5 Atracction quattro",
    Año: 2020,
    Placa: "ABC-201",
    Combustible: "Gasolina",
    Motor: "2.0 CC",
    Transmision: "Automatica",
    Color: "Gris",
    img: "https://http2.mlstatic.com/D_NQ_NP_874721-MCO70220176890_062023-O.webp",
    cantidadEnCarrito: 1,
  },

  {
    id: 2,
    Precio: 193000000,
    Kilometraje: "50.000 Km",
    Modelo: "Bmw X4 Xdrive 30i",
    Año: 2020,
    Placa: "ABC-201",
    Combustible: "Gasolina",
    Motor: "2.0 CC",
    Transmision: "Automatica",
    Color: "Blanco",
    img: "https://http2.mlstatic.com/D_NQ_NP_966351-MCO71043873668_082023-O.webp",
    cantidadEnCarrito: 1,
  },
  {
    id: 3,
    Precio: 33000000,
    Kilometraje: "89.000 Km",
    Modelo: "Chevrolet Spark Gt ",
    Año: 2015,
    Placa: "MUT-455",
    Combustible: "Gasolina",
    Motor: "1.2 CC",
    Transmision: "Mecanica",
    Color: "Rojo",
    img: "https://http2.mlstatic.com/D_NQ_NP_686542-MCO71168707266_082023-O.webp",
    cantidadEnCarrito: 1,
  },
  {
    id: 4,
    Precio: 178500000,
    Kilometraje: "39.052 Km",
    Modelo: "Toyota Fortuner Srv",
    Año: 2018,
    Placa: "EMM-649",
    Combustible: "Gasolina",
    Motor: "2.7 CC",
    Transmision: "Automatica",
    Color: "Gris",
    img: "https://http2.mlstatic.com/D_NQ_NP_722288-MCO70200116805_062023-O.webp",
    cantidadEnCarrito: 1,
  },
  {
    id: 5,
    Precio: 280000000,
    Kilometraje: "621.440 Km",
    Modelo: "Nissan Patrol",
    Año: 2020,
    Placa: "IAH-061",
    Combustible: "Gasolina",
    Motor: "4.0 CC",
    Transmision: "Mecanica",
    Color: "Blanco",
    img: "https://http2.mlstatic.com/D_NQ_NP_773796-MCO50452263450_062022-W.webp",
    cantidadEnCarrito: 1,
  },
  {
    id: 6,
    Precio: 280000000,
    Kilometraje: "10.000 Km",
    Modelo: "Mazda 3",
    Año: 2019,
    Placa: "ABC-201",
    img: "https://th.bing.com/th/id/OIP.1MBvI3Kx7WtwNYtf-XC4mAHaE8?w=249&h=180&c=7&r=0&o=5&dpr=1.3&pid=1.7",
    cantidadEnCarrito: 1,
  },
  {
    id: 7,
    Precio: 280000000,
    Kilometraje: "10.000 Km",
    Modelo: "Skopa",
    Año: 2000,
    Placa: "ABC-201",
    img: "https://img.autoabc.lv/Skoda-Octavia/Skoda-Octavia_2000_Hecbeks_234550528.jpg",
    cantidadEnCarrito: 1,
  },
  {
    id: 8,
    Precio: 280000000,
    Kilometraje: "22.000 Km",
    Modelo: "Ford Escape",
    Año: 2016,
    Placa: "ABC-201",
    img: "https://th.bing.com/th/id/OIP.MA4Ne4km-1kf7BwChNTEDQHaFP?pid=ImgDet&rs=1",
    cantidadEnCarrito: 1,
  },
  {
    id: 9,
    Precio: 280000000,
    Kilometraje: "10.000 Km",
    Modelo: "Ford Raptor",
    Año: 2020,
    Placa: "ABC-201",

    img: "https://th.bing.com/th/id/R.98e2bac7c17fe163259e44a0f40edd42?rik=8pRDghF967DFxg&riu=http%3a%2f%2fpictures.topspeed.com%2fIMG%2fcrop%2f201601%2f2017-ford-f-150-raptor-6_1600x0w.jpg&ehk=bQBVHrsEXP02D550iEERzTYXNmnh1GB4e%2bXRThS6esI%3d&risl=&pid=ImgRaw&r=0",
    cantidadEnCarrito: 1,
  },
  {
    id: 10,
    Precio: 280000000,
    Kilometraje: "10.000 Km",
    Modelo: "Renault 12",
    Año: 2020,
    Placa: "ABC-201",
    img: "https://th.bing.com/th/id/OIP.Wk1MGjaA4vqR7FX8xI1HswHaDq?pid=ImgDet&rs=1",
    cantidadEnCarrito: 1,
  },
  {
    id: 11,
    Precio: 280000000,
    Kilometraje: "22.000 Km",
    Modelo: "Renault Duster",
    Año: 2020,
    Placa: "ABC-201",
    img: "https://th.bing.com/th/id/OIP.rLINBQsFnz656Jvp7lhobgHaEK?w=297&h=180&c=7&r=0&o=5&dpr=1.3&pid=1.7",
    cantidadEnCarrito: 1,
  },
  {
    id: 12,
    Precio: 280000000,
    Kilometraje: "10.000 Km",
    Modelo: "Volkswagen Golf",
    Año: 2020,
    Placa: "ABC-201",
    img: "https://th.bing.com/th/id/R.adecd608f2b2534a41d4ffc7776a4734?rik=rsogiHGjUIvIXg&pid=ImgRaw&r=0",
    cantidadEnCarrito: 1,
  },
]);

const TarjetasCompradas = ref([]);

const TarjetasInfo = ref([]);

function añadirP(index) {
  const tarjetaSeleccionada = tarjetas.value[index]; // Llamar la tarjeta seleccionada

  // Verificar si el producto ya está en el carrito
  const productoExistente = TarjetasCompradas.value.find(
    (p) => p.id === tarjetaSeleccionada.id
  );

  if (productoExistente) {
    // Si el producto ya está en el carrito, aumentar su cantidad
    productoExistente.cantidadEnCarrito += 1;
  } else {
    // Si el producto no está en el carrito, añadirlo al carrito
    tarjetaSeleccionada.cantidadEnCarrito = 1;
    TarjetasCompradas.value.push(tarjetaSeleccionada);
  }
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

const total = computed(() => {
  return TarjetasCompradas.value.reduce(
    (total, tarjetas) => total + tarjetas.Precio * tarjetas.cantidadEnCarrito,
    0
  );
});
function vaciarCarrito() {
  TarjetasCompradas.value = [];
}
</script>

<style scoped>
.container {
  position: relative;
  --size-button: 40px;
  color: white;
}

.input {
  padding-left: var(--size-button);
  height: var(--size-button);
  font-size: 15px;
  border: none;
  color: #fff;
  outline: none;
  width: var(--size-button);
  transition: all ease 0.3s;
  background-color: #191a1e;
  box-shadow: 1.5px 1.5px 3px #0e0e0e, -1.5px -1.5px 3px rgb(95 94 94 / 25%),
    inset 0px 0px 0px #0e0e0e, inset 0px -0px 0px #5f5e5e;
  border-radius: 50px;
  cursor: pointer;
}

.input:focus,
.input:not(:invalid) {
  width: 500px;
  cursor: text;
  box-shadow: 0px 0px 0px #0e0e0e, 0px 0px 0px rgb(95 94 94 / 25%),
    inset 1.5px 1.5px 3px #0e0e0e, inset -1.5px -1.5px 3px #5f5e5e;
}

.input:focus + .icon,
.input:not(:invalid) + .icon {
  pointer-events: all;
  cursor: pointer;
}

.container .icon {
  position: absolute;
  width: var(--size-button);
  border-radius: 25px;
  top: 0;
  left: 13px;
  padding: 8px;
  pointer-events: none;
}

.container .icon svg {
  width: 100%;
  height: 100%;
}

.barraimg {
  position: fixed;
  padding: 20px;
}
.footer {
  width: 100%;
}
.card {
  background-color: #3d5af1;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  padding: 10px 25px;
  gap: 20px;
  box-shadow: 0px 0px 20px rgba(0, 0, 0, 0.055);
}

/* for all social containers*/
.socialContainer {
  width: 52px;
  height: 52px;
  border-radius: 50%;
  background-color: rgb(44, 44, 44);
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  transition-duration: 0.3s;
}
/* instagram*/
.containerOne:hover {
  background-color: #d62976;
  transition-duration: 0.3s;
}
/* twitter*/
.containerTwo:hover {
  background-color: #00acee;
  transition-duration: 0.3s;
}
/* linkdin*/
.containerThree:hover {
  background-color: #0072b1;
  transition-duration: 0.3s;
}
/* Whatsapp*/
.containerFour:hover {
  background-color: #128c7e;
  transition-duration: 0.3s;
}

.socialContainer:active {
  transform: scale(0.9);
  transition-duration: 0.3s;
}

.socialSvg {
  width: 17px;
}

.socialSvg path {
  fill: rgb(255, 255, 255);
}

.socialContainer:hover .socialSvg {
  animation: slide-in-top 0.3s both;
}

@keyframes slide-in-top {
  0% {
    transform: translateY(-50px);
    opacity: 0;
  }

  100% {
    transform: translateY(0);
    opacity: 1;
  }
}

.button {
  --width: 100px;
  --height: 35px;
  --button-color: #222;
  width: var(--width);
  height: var(--height);
  background: var(--button-color);
  position: relative;
  text-align: center;
  border-radius: 0.45em;
  font-family: "Arial";
  transition: background 0.3s;
}

.button::before {
  position: absolute;
  font-size: 0.9rem;
  color: #fff;
  border-radius: 0.25em;
}

.text {
  display: flex;
  align-items: center;
  justify-content: center;
}

.button-wrapper,
.text,
.icon {
  overflow: hidden;
  position: absolute;
  width: 100%;
  height: 100%;
  left: 0;
  color: #fff;
  background-color: #000000;
}

.text {
  top: 0;
}

.text,
.icon {
  transition: top 0.5s;
}

.icon {
  color: #fff;
  top: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.icon svg {
  width: 24px;
  height: 24px;
}

.button:hover {
  background: #222;
}

.button:hover .text {
  top: -100%;
}

.button:hover .icon {
  top: 0;
}

.button:hover:before,
.button:hover:after {
  opacity: 1;
  visibility: visible;
}

.button:hover:after {
  bottom: calc(var(--height) + var(--gap-between-tooltip-to-button) - 20px);
}

.button:hover:before {
  bottom: calc(var(--height) + var(--gap-between-tooltip-to-button));
}

@font-face {
  font-family: "Mia";
  src: url("./fonts/Sportesia.otf");
}
.titulo {
  color: white;
  display: flex;
  justify-content: center;
  font-family: "Mia";
}
.tableinfo tr:nth-child(odd) {
  background-color: #a0f1ff;

}

.containerinfomodal {
  display: flex;
  justify-content: space-around;
  align-items: baseline;
}
#modal-contentre {
  display: flex;
  flex-wrap: wrap;
}
.containerinfotabla {
  text-align: center;
  display: grid;
  gap: 10px;
}

.containerinfodescripcion {
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
  display: flex;
  flex-direction: column;
}

th {
  background-color: #3d5af1;
  color: white;
  border-bottom: 3px solid black;
  padding: 10px 20px;
}

.textoenca {
  color: white;
}

tr {
  padding: 10px;
  text-align: center;
  display: flex;
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
  background-image: url(https://images.caricos.com/m/mercedes-benz/2022_mercedes-benz_c-class/images/2560x1440/2022_mercedes-benz_c-class_45_2560x1440.jpg);
  height: 80vh;
  background-size: cover;
  object-fit: cover;
  background-repeat: no-repeat;
}

.barra2 {
  background-color: #3d5af1;
  color: white;
  display: flex;
  flex-wrap: wrap;
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
  border-bottom: 3px solid #3d5af1;
}
.textBarra3 {
  width: 700px;
  text-align: center;
}
.barraopc {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  gap: 35px;
  color: #b6b6b6;
}

#opcs,
h4 {
  font-size: 20px;
}

.divimg {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  transition: transform 0.2s ease, opacity 0.2s ease;
  gap: 15px;
}

.B {
  display: flex;
}

.opcsboton {
  position: relative;
  display: block;
  transition: 0.5s;
  cursor: pointer;
  background-color: #3d5af1;
  border: none;
  border-radius: 100%;
  padding: 10px;
}

.opcsboton::after {
  position: absolute;
  content: "";
  width: 60%;
  height: 5%;
  top: 90%;
  left: 20%;
  transition: transform 0.5s;
  transform: scaleX(0);
  transform-origin: right;
  background-color: #000000;
}

.opcsboton:hover {
  color: white;
}

.opcsboton:hover::after {
  transform: scaleX(1);
  transform-origin: left;
}

.img {
  width: 35px;
}

.botones {
  display: flex;
  justify-content: center;
  width: 100%;
}

#opcs {
  padding: 10px;
  cursor: pointer;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
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
  padding: 20px 100px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 55px;
  background-color: #000000;
}

.textos {
  display: flex;
  gap: 15px;
  justify-content: space-around;
}

#carrostarjetas {
  width: 300px;
  height: 200px;
  border-top-right-radius: 15px;
  border-top-left-radius: 15px;
  border-bottom-left-radius: 0px;
  border-bottom-right-radius: 0px;
}

.tarjeta {
  background-color: #e2f3f5;
  display: flex;
  flex-direction: column;
  font-size: 15px;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  padding-bottom: 15px;
  border-radius: 15px;
  height: 420px;

}
.botonContainer {
  background-color: #e2f3f5;
  display: flex;
  flex-direction: column;
  gap: 15px;
  font-size: 15px;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  padding: 0;
  height: 300px;
  border-radius: 15px;
}

#datos {
  color: rgb(255, 255, 255);
  background-color: rgb(0, 0, 0);
  padding: 7px;
  border-radius: 10px;
  border: none;
}

#modal-body2 {
  display: flex;
  flex-direction: column;
  align-items: center;
  flex-wrap: wrap;
}

#modal-body1 {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
}

.carousel-inner {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  width: 400px;
  height: 300px;
  border-radius: 25px;
  overflow: hidden;
}

.carousel-item,
img {
  width: 400px;
  height: 100%;
  object-fit: cover;
  border-radius: 25px;
  position: relative;
}

.opcstext {
  position: relative;
  display: block;
  transition: 0.5s;
  cursor: pointer;
}

.opcstext::after {
  position: absolute;
  content: "";
  width: 100%;
  height: 15%;
  top: 120%;
  left: 0;
  transition: transform 0.5s;
  transform: scaleX(0);
  transform-origin: right;
  background-color: #000000;
}

@media screen and (max-width: 1000px) {
}
@media screen and (max-width: 838px) {
  .intro {
    width: 100%;
    text-align: center;
  }
}
@media screen and (max-width: 756px) {
  .carros {
    padding: 20px 70px;
  }
}
@media screen and (max-width: 568px) {
  .carros {
    padding: 20px 0px;
  }
  #modal-body1 {
    padding: 0;
  }
  .tbody td {
    padding: 4px;
    border: 2px solid rgba(0, 0, 0, 0.105);
    display: flex;
    align-items: center;
  }
  .thead th {
    padding: 10px 17px;
  }
}
@media screen and (max-width: 359px) {
  .tarjeta {
    width: 300px;
  }
}

#textos {
  display: flex;
  gap: 10px;
  justify-content: space-around;
  background-color: #ffffff;
}

/*Card footer*/
.card-social {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  width: 100%;
  opacity: 0;
  transition: transform 0.2s ease, opacity 0.2s ease;
  gap: 10px;
}
/*Hover*/
/*.tarjeta:hover {
  box-shadow: 0 8px 50px #23232333;
  height: 440px;
  background-color: #e2f3f5;
  display: flex;
  flex-direction: column;
  gap: 15px;
  font-size: 15px;
  transition: 0.5s ease-in-out;
  transform: scale(1.1);
  margin: 20px 10px 20px 10px;
}*/

.tarjeta:hover .divimg {
  transform: translateY(0%);
  transition: 0.5s ease-in-out;
}

 .card-social {
  transform: translateY(10%) translateX(0%);
  opacity: 1;
  transition: 0.5s ease-in-out;
}

.button {
  transform: translateY(215%);
}

.vaciarCarrito {
  background-color: #3d5af1;
  color: white;
  border: none;
  padding: 10px;
  font-weight: bold;
  border-radius: 15px;
}
</style>
