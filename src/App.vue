<template lang="">
  <div id="app">
  <div class="container-left">
      <!-- Hero -->
      <PThero v-bind:person="person"></PThero>
      <!-- Cierre Hero -->
      <!-- informacion -->
      <PTinformacion v-bind:person="person"></PTinformacion>
      <!-- Cierre Informacion -->
      <!-- Social link -->
      <section class="social-link">
        <a href="https://twitter.com/silvermiguel96" target="_black" class="social-link twitter"></a>
        <a href="https://www.facebook.com/miguelangel.rc13" target="_black" class="social-link facebook"></a>
        <a href="https://github.com/silvermiguel96" target="_black" class="social-link github"></a>
        <a href="https://www.instagram.com/silvermiguel13/" target="_black" class="social-link instagram"></a>
      </section>
  </div>
    <div class="container-right">
      <!-- About -->
     <PTsobremi v-bind:person="person"></PTsobremi>
      <!-- Trabajo -->
      <section class="trabajos">
        <h2 class="trabajo-titulo">Trabajos</h2>
        <div class="trabajo" v-for=" p in person.data[0].jobs">
          <h3><strong> Tiempo: </strong>{{ p.tiempo }}</h3>
          <h3><strong> Cargo: </strong>{{ p.cargo }}</h3>
          <h3><strong> Empresa: </strong>{{ p.empresa }}</h3>
        </div>
      </section>
      <PTfooter></PTfooter>
    </div>
  </div>
</template>

<script>
import PThero from '../src/components/layout/hero.vue'
import PTinformacion from '../src/components/informacion.vue'
import PTsobremi from '../src/components/sobremi.vue'
import PTfooter from '../src/components/layout/footer.vue'

import axios from 'axios'
import URL from './services/url.js'

export default {
  name: 'app',
  components: { PTfooter, PThero ,PTinformacion , PTsobremi },
  data () {
    return {
      person: [],
    }
  },
  mounted() {
    axios
      .get(URL)
      .then(response => (this.person = response))
      console.log(this.person)
  },
  filters () {
  }
}
</script>
<style>
*/
* {
  margin: 0;
  padding: 0;
}
h1,
  h2,
    h3,
     p,
     li,h4{
      font-family: 'ABeeZee', sans-serif; 
    }
p {
  font-size: 20px;
}
#app {
  display: flex;
  width: 100%;
  height: 100vh;
}
.container-left {
  background-color: #252F63;
  color: #ffffff;
  width: 50% ;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.social-link {
  display: flex;
  width: 200px;
  height: 50px;
  background-size: 50px 50px;
  margin: 0 auto;

}
.social-link.twitter {
  background-image: url('../src/public/img/twitter.svg');
}
.social-link.facebook {
  background-image: url('../src/public/img/facebook.svg');
}
.social-link.github {
  background-image: url('../src/public/img/github.svg');
}
.social-link.instagram {
  background-image: url('../src/public/img/instagram.svg');
}
/* Block container :right */
.container-right {
  display: flex;
  width: 50% ;
  flex-direction: column;
  justify-content: center;
}
.trabajos {
  width:600px;
  margin: 0 auto;
  display:block;
}
.trabajo-titulo,.sobre-titulo {
  color: #6DB344;
  font-size: 60px;
  border-bottom: 1px solid #6DB344;
  padding-bottom: 3px;
}
.trabajos p {
  font-size: 20px;
  margin-top: 5px;
  height: 200px;
}
.trabajo {
  margin: 10px 0 10px 0;
  padding: 10px
}
.trabajo h3 {
  font-size: 1.5em;
}
@media screen and (max-width: 767) {
  #app {
    flex-direction: column;
  }
}
</style>
