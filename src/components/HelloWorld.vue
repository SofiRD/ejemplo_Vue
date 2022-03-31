<script setup>
import { ref } from 'vue';
defineProps({
  msg: String
});

const count = ref(0);
var existentialQuestion= ref('Que es tan lindo')
var number = 0;
var image_name = ref("../assets/michi1.jpg");
var imagenes = [true, false, false, false];
var mostrar = ref(true);
var items= [
      { message: 'Obediente' },
      { message: 'Cariñoso' },
      { message: 'Limpio' }
    ]
function changeImage() {  
  for(var i = 0; i<imagenes.length; i++){
     if (imagenes[i]){
       if (i+1 < imagenes.length){
         imagenes[i+1]=true
       } else {
         imagenes[0] = true
       }
       imagenes[i] = false;
       break;
     }
    
  }
  items = imagenes
}
</script>

<template>
  <h1>{{ msg }}</h1>
  <img class="image" v-show="mostrar" src="../assets/michi1.jpg" width="200" />
  <img class="image" v-show="!mostrar" src="../assets/michi2.jpg" width="200" />
  <h2>Lo que a tu te gusta de mi michi es: {{existentialQuestion}}</h2>
   <input v-model="existentialQuestion"/>

  <h2>¿Porque es el mejor? </h2>
  <ul id="example-1">
  <li v-for="item in items" :key="item.message">
    {{ item.message }}
  </li>
</ul>

  <button type="button" @click="mostrar = !mostrar">Cambiar Imagen</button>
  
  
</template>

<style scoped>
a {
  color: #42b983;
}
</style>
