
<script>
  export default {
   // props:['title'], una forma de declarar props
  // otra forma es con un objeto

    props:{ // este permite establecer el tipo, lo cual ofrece cierta validación
      // ya que por consola le dirá al desarrollador cierto feedback del fallo
      // OJO: Solo da feedback al dev, la app no se rompe ni le da feedback al usuario!

      title: String,
      initialNumber: {
        type: Number,
        // required: true,
        default: 20
      }
    },


    data(){
      return{
        counter:this.initialNumber, // paso un props a la variable reactiva
        subtitle: "learning vue"
      }
    },

    methods: {
      getSquare(){
        return this.counter * this.counter
      },

      increase(){
        this.counter++
      },

      decrease(){
        this.counter--
      }

    },

    computed: {
      getSquareComputed(){
        return this.getSquare()
      }
    }

  }
</script>


<template>

  <section class="ejemplo">
    <h1>Counter</h1>
    <h6>{{subtitle}}</h6>
    <p>{{counter}}<sup>2</sup> =  {{getSquareComputed}}</p>
    <button v-on:click="increase">Incrementar</button>
    <button v-on:click="decrease">disminuir</button>
  </section>

</template>

<style scoped>

.ejemplo{
  font-size: xxx-large;

}

button{
  height: 20%;
  width: 60%;
  background-color: aquamarine;
  cursor: pointer;
}

</style>
