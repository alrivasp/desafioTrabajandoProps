<template>
  <div>
    <div>
      <label for="tarea">Tarea:</label>
      <input id="tarea" type="text" v-model="inputMensaje" placeholder="Agregar nueva tarea"/>
      <button v-on:click="agregar">Agregar</button>
    </div>
    <hr>
    <h3>Lista</h3>
    <ul>
      <Task 
        v-for="(tarea, index) in lista" 
        :key="index"
        :tarea="tarea"
        :indice="index"  
        v-on:borrar="borrar"
      />
    </ul>
  </div>
</template>

<script>
import Task from './Task.vue'
export default {
  name: 'TaskList',
  components: {
    Task    
  },
  data(){
    return {
      lista: [],
      inputMensaje: ''
    }
  },
  methods: {
    agregar(){
      if(this.inputMensaje){
        this.lista.push(this.inputMensaje);
        this.inputMensaje = "";
      }
    },
    borrar(id) {
      this.lista = this.lista.filter((k, v) => v !== id);
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
</style>
