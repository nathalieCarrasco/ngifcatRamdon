<template>
  <div class="app">
    <h1 class="titulo">GIF CAT RANDOM</h1>
    <div class="form">
      <form class="lista">
            <label for="">Titulo: </label>
            <input type="text" v-model="titulo" placeholder="cuchito">
            <div class="filtro">
            <label for="" >Filtro: </label>
            <select id="" class="pr-4 pl-1 py-1" v-model="filtro">
              <option value="blur">Blur</option>
              <option value="mono">Mono</option>
              <option value="sepia">Sepia</option>
              <option value="negative">Negative</option>
              <option value="paint">Paint</option>
            </select>
            </div>
            <div class="color">
            <label for="">Color:  </label>
            <select id="" class="py-1" v-model="color">
              <option value="red">Rojo</option>
              <option value="green">Verde</option>
              <option value="yellow">Amarillo</option>
              <option value="blue">Azul</option>
              <option value="white">Blanco</option>
              <option value="black">Negro</option>
            </select>
            <div class="circuloColor mx-3 py-2" :style="{backgroundColor : this.color}"></div>
            </div>
            <div>
            <label>Tamaño: </label>
            <input type="number" v-model="tamaño" placeholder="300,400,500,etc">
            </div>   
            
      </form>
</div>
 <button  @click="obtenerGatito">Obtener mi gatito</button>  
    <div>
    <img :src="gatito" alt="">
    </div>
</div>
</template>

<script>
export default {
  name: "Formcat",

  data: () => ({
    titulo : "",
    filtro : "",
    color : "",
    tamaño : "",
    gatito: ""
  }),
  methods:{
    obtenerGatito(){
      fetch(`https://cataas.com/cat/gif/says/${this.titulo}?filter=${this.filtro}&color=${this.color}&size=${this.tamaño}`)
        .then(resp => this.gatito = resp.url)
    }  
  }
}
</script>

<style scoped>


.circuloColor{
  border-radius: 50%;
  height: 30px;
  width: 30px;
  display: inline-block;
  vertical-align: middle;
}
.titulo{
  height:  100px;
  padding-top: 80px;
  margin: 0 auto;
  font-weight: bold;
}
.form{
    background-color: crimson;
    margin: 0;
    padding: 100px;
}

</style>