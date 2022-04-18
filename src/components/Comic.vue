<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
   <div class="container" align="center">
      <div class="card" style="width: 18rem;">
        <h3>Comic: {{info.num}}</h3>
      <img v-bind:src="info.img" class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">{{info.title}}</h5>
        <p class="card-text">{{info.alt}}</p>
        <p>
          <div class="clasificacion">
            <input id="radio1" type="radio" name="estrellas" value="5"><!--
          --><label for="radio1">&#9733;</label><!--
          --><input id="radio2" type="radio" name="estrellas" value="4"><!--
          --><label for="radio2">&#9733;</label><!--
          --><input id="radio3" type="radio" name="estrellas" value="3"><!--
          --><label for="radio3">&#9733;</label><!--
          --><input id="radio4" type="radio" name="estrellas" value="2"><!--
          --><label for="radio4">&#9733;</label><!--
          --><input id="radio5" type="radio" name="estrellas" value="1" ><!--
          --><label for="radio5">&#9733;</label>
          </div>
        </p>
        <button class="btn btn-success" v-on:click="datosRetornados()">Cambiar</button>
      </div>
      </div>
   </div>

  </div>
</template>

<script>
import axios from 'axios'
export default {
      name: 'Comic',
      data(){
        return {
          info: null
        }
      },
      props: {
        msg: String
      },
      mounted(){
        this.datosRetornados();
      },
      methods: {
        datosRetornados(){
          debugger;
          var rand = Math.floor(Math.random() * (2500 - 1 + 1)) + 1 
          axios
          .get(`http://localhost:8080/${rand}/info.0.json`)
          .then((response) => (this.info = response.data))    
          console.log(info)

      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

input[type="radio"] {
  display: none;
}

label {
  color: grey;
  font-size:50px;
}

.clasificacion {
  direction: rtl;
  unicode-bidi: normal;
}

label:hover,
label:hover ~ label {
  color: orange;
}

input[type="radio"]:checked ~ label {
  color: orange;
}

</style>
