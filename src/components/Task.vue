<template>
    <div>
        <li>{{ tarea }} <button @click="clickedBorrar(indice)">Borrar</button></li>
    </div>
</template>

<script>
export default {
  name: 'Task',
  props: {
    tarea: String,
    indice: Number,
  },
  methods: {
    clickedBorrar(indice) {
      this.$emit("borrar", indice);
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    li {
    display: inline-block;
    margin: 0.5rem;
    }
</style>
