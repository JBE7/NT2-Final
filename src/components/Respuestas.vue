<template>
     
      <div class="table-responsive">
          <table class="table">
            <tr class="bg-success text-white">
              <th>Número de pregunta</th>
              <th>Respuesta</th>
            </tr>
            <tr
              class="bg-info text-white"
              v-for="(preg, index) in preguntas"
              :key="index"
            >
              <td>{{ preg.pregunta }}</td>
              <td><a v-for="(res, index) in preg.respuestas"
              :key="index"> {{ res }}</a></td>
            </tr>
          </table>
      </div>

</template>

<script>

  export default  {
    name: 'src-components-respuestas',
    props: [],
    mounted () {

    },
    data () {
      return {
        preguntas : [
          { pregunta: 1, respuestas: ["b"] },
          { pregunta: 2, respuestas: ["c"] },
          { pregunta: 3, respuestas: ["b"] },
          { pregunta: 4, respuestas: ["d"] },
          { pregunta: 5, respuestas: ["d"] },
        ]
      }
    },
    methods: {

    },
    computed: {
      
    }
}


</script>

<style scoped lang="css">
  .src-components-respuestas {

  }
</style>
