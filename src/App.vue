<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
   
   <!--  <router-link to="/kelas">Data Kelas  </router-link>
    <router-link to="/siswa">Data Siswa</router-link>
    <router-view/><br><br> -->

    <h1>{{ name }}</h1>
    <input v-model="name" placeholder="Masukan Nama"><br><br>
    <p>Nilai Anda : {{ total }}</p> 
    <button v-on:click="submit">Click Me!</button>

    <p><b>1. Berasal darimanakah makanan khas ayam betutu?</b></p>
    <input type="radio" value="Jakarta" v-model="satu">
    Jakarta &nbsp &nbsp
    <input type="radio" value="Malaysia" v-model="satu">
    Malaysia &nbsp &nbsp
    <input type="radio" value="Papua" v-model="satu">
    Papua &nbsp &nbsp
    <input type="radio" value="Bali" v-model="satu">
    Bali <br><br>

    <p><b>2. Soto banjar adalah makanan khas daerah..</b></p>
   <input type="radio" value="Kalimantan Barat" v-model="dua">
   Kalimantan Barat &nbsp &nbsp
   <input type="radio" value="Cirebon" v-model="dua">
   Cirebon &nbsp &nbsp
   <input type="radio" value="Banjar" v-model="dua">
   Banjar &nbsp &nbsp
   <input type="radio" value="Kalimantan Selatan" v-model="dua">
   Kalimantan Selatan <br><br>

   <p><b>3. Nama pizza tradisional yang berasal dari daerah Tolitoli adalah..</b></p>
   <input type="radio" value="Bunni" v-model="tiga">
   Bunni  &nbsp &nbsp
   <input type="radio" value="Ambal" v-model="tiga">
   Ambal  &nbsp &nbsp
   <input type="radio" value="Doran" v-model="tiga">
   Doran  &nbsp &nbsp
   <input type="radio" value="Cerakcak" v-model="tiga">
   Cerakcak

  </div>

</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  data() {
    return {
      name : '',
      satu: '',
      dua : '',
      tiga : '', 
      total : 0
    }
    },
  methods: {
    submit(){
      if (this.satu == 'Bali' && this.dua == 'Kalimantan Selatan' && this.tiga == 'Ambal') {
        this.total=+3
      }
      else if(this.satu == 'Bali' && this.dua == 'Kalimantan Selatan') {
        this.total=+2
      }
      else if(this.satu == 'Bali' && this.tiga == 'Ambal') {
        this.total=+2
      }
      else if(this.dua == 'Kalimantan Selatan' && this.tiga == 'Ambal') {
        this.total=+2
      }
      else if (this.satu == 'Bali') {
        this.total=+1
      }
      else if(this.dua == 'Kalimantan Selatan') {
        this.total=+1
      }
      else if (this.tiga == 'Ambal') {
        this.total=+1
      }
      else{this.total = 0}
    }
  },
  components: {
    HelloWorld
  }
}

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
