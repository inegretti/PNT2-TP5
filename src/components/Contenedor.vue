<template>

  <section class="src-components-contenedor">
    <br>
    <div id="container" >
    <div >
    <button v-for="(boton,index) in this.cbotones" :key="index" :style={backgroundColor:boton} value=boton @click="$emit('envio-respuesta',boton)"> OPTION </button>
    </div>
    <br>
	</div>
  </section>


</template>

<script>

  export default  {
    name: 'src-components-contenedor',
    props: ["cbotones"
    ],
      beforeMount () {
    
      
      
    },
    mounted () {
      
      
      
      
    },
     beforeUpdate () {
       
    },
    updated () {
      
    },
    data () {
      return {
          //cantidad:this.cbotones,
          botones:this.cbotones,
      }
    },
    methods: {
    },
    computed: {
      
    }
}


</script>

<style scoped lang="css">
  .src-components-contenedor {
  background: #232323;
	margin: 0;
	font-family: "Montserrat", "Avenir";
  }
</style>
