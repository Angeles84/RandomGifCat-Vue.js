<template>
  <div class="hello">
    <h1>{{ encabezado }}</h1>
    <div class="div-form">
      <form>
        <label for="titulo">Título: </label>
        <input type="text" class="ml-2 pl-1" placeholder="Miau" v-model="titulo">
        <br><br>
        <label for="filtro">Filtro: </label>
        <select class="pr-4 pl-1 py-1 ml-2" v-model="filtro">
          <option disabled selected value="">Elige un filtro</option>
          <option value="sepia">sepia</option>
          <option value="blur">blur</option>
          <option value="mono">mono</option>
          <option value="negative">negative</option>
          <option value="paint">paint</option>  
        </select>
        <br><br>
        <label for="color">Color: </label>
        <select class="pr-4 pl-1 py-1 ml-2" v-model="color" >
          <option disabled selected value="">Elige un color</option>
          <option value="red">rojo</option>
          <option value="yellow">amarillo</option>
          <option value="green">verde</option>
          <option value="blue">azul</option>
          <option value="blueviolet">violeta</option>
        </select>
        <span class="bola" :style="{backgroundColor: this.color}"></span>
        <br><br>
        <label for="tamano">Tamaño: </label>
        <input type="number" class="ml-2 pl-1" placeholder="400" v-model.number="tamano">
      </form>
    </div>
    <button class="btn btn-secondary mt-3" @click="buscarGifCat">Obtener gatito</button>
    <div class="random-git-cat" >
      <img :src="imagen" alt="">
    </div>
  </div>
</template>

<script>
export default {
  name: 'RandomGifCat',
  props: {
    encabezado: String
  },
  data: () => ({
    titulo: "",
    filtro: "",
    color: "",
    tamano: "",
    imagen: ""
  }),
  methods: {
    async buscarGifCat() {
      this.imagen = `https://cataas.com/cat/gif/says/${this.titulo}?filter=${this.filtro}&color=${this.color}&size=${this.tamano}`;
    }
  //buscarGifCat() {
  //  fetch(`https://cataas.com/cat/gif/says/${this.titulo}?filter=${this.filtro}&color=${this.color}&size=${this.tamano}`)
  //  .then(response => this.imagen = response.url)  
  //}
  }
}

//https://cataas.com/cat/gif/says
</script>

<style scoped>
h1 {
  font-weight: 700;
  margin-bottom: 0.5em;
}
.div-form {
  background-color: #e67070;
}
form {
  text-align: left;
  width: 81%;
  margin: 0 auto;
  padding-top: 1.4em;
  padding-bottom: 1em;
}

@media (min-width: 415px) and (max-width: 768px) {
  form {
    width: 50%;
  }
}

@media (min-width: 769px) and (max-width: 992px) {
  form {
    width: 40%;
  }
}

@media (min-width: 993px) and (max-width: 1200px) {
  form {
    width: 35%;
  }
}

@media (min-width: 1201px) {
  form {
    width: 28%;
  }
}

label {
  font-weight: 600;
}
.bola {
  height: 2em;
  width: 2em;
  border-radius: 50%;
  display: inline-block;
  margin-left: 0.4em;
  vertical-align: middle;
}
.random-git-cat {
  padding-top: 1.5em;
  padding-bottom: 1em;
}
</style>
