<template>

  <div class="jumbotron">
    <div>
      Color: <input type="text" v-model="color" />
      Fondo: <input type="text" v-model="bkColor" />
      Size: <input type="text" v-model="size" />
    </div>

    <hr>

    <div>
      Texto: <input type="text" v-model="texto" :style="{ 'color': color, 'fontSize': getSizeFormated(), 'backgroundColor': bkColor }" />
     
      <p v-if="contarPalabras.mostrar">
        Cantidad de palabras: {{contarPalabras.cantidad}}
      </p>
    </div>

  <br/>
  <br/>
  <hr>

    <div>
      <Respuestas> </Respuestas>
    </div>

  </div>

</template>

<script>
  import Respuestas from "./Respuestas"

  export default  {
    name: 'src-components-texto',
    props: [],
    mounted () {

    },
    components: {
      Respuestas
    },
    data () {
      return {
        color: 'black',
        bkColor: 'white',
        size: '20',
        texto: ''
      }
    },
    methods: {
      getSizeFormated(){
        return this.size + 'px'
      }
    },
    computed: {
      contarPalabras(){
        let cant = this.texto.split(' ').filter((a) => a != '').length 
        return {
          mostrar: cant > 0,
          cantidad: cant 
        }
      }
    }
}
</script>

<style>
  
</style>
