<template>

  <section class="src-components-text">
    <label for="color">Color</label>
          <input 
            type="text"
            id="color"
            class="form-control"
            v-model="color"
          >
    <label for="background">Fondo</label>
    <input 
      type="text"
      id="background"
      class="form-control"
      v-model="background"
    >
    <label for="size">Tamaño</label>
    <input 
      type="text"
      id="size"
      class="form-control"
      v-model="size"
    >
    <hr>
    <label for="text">Texto</label>
    <input 
      type="text"
      id="text"
      class="form-control"
      v-model="text"
      :style="{
          color: color,
          'background-color': background,
          'font-size': size
        }"
    >
    <p v-if="wordsInString >= 1">Cantidad de palabras: {{ wordsInString }} </p>

    <hr>
    <table>
      <tr>
        <th>Pregunta</th>
        <th>Respuesta</th>
      </tr>
      <tr>
        <td>1.</td>
        <td>b</td>
      </tr>
      <tr>
        <td>2.</td>
        <td>c</td>
      </tr>
      <tr>
        <td>3.</td>
        <td>b</td>
      </tr>
      <tr>
        <td>4.</td>
        <td>d</td>
      </tr>
      <tr>
        <td>5.</td>
        <td>a, d</td>
      </tr>
    </table>
  </section>

</template>

<script>

  export default  {
    name: 'src-components-text',
    props: [],
    mounted () {
        
    },
    data () {
      return {
        text: "",
        size: "",
        color: "",
        background: "",
      }
    },
    methods: {
      
    },
    computed: {
      wordsInString() {
        let totalWords = this.text.trim()
        if (totalWords != "") {
          totalWords = totalWords.replace(/[ ]+/g, " ")
          totalWords = totalWords.split(" ")
        }
        return totalWords.length
      }
    }
}


</script>

<style scoped lang="css">
  .src-components-text {

  }
  table {
    border-collapse: collapse;
  }
  th {
    border: 1px solid black
  }
  td {
    border: 1px solid black
  }
</style>
