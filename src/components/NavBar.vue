<template >

  <section class="src-components-nav-bar">
    <Header :res='valor'/>
    <button @click="resetear()"> New colors</button>
		<span>{{mensaje}} </span>
		<button @click="cambiarAEasy()">easy</button>
		<button class="selected" @click="cambiarAHard()">hard</button>
    <Contenedor  @contador-out="valor=$event"   @envio-respuesta="evaluar($event)" :cbotones='botones'/>

  </section>

</template>

<script >
import Contenedor from "./Contenedor.vue";
import Header from "./Header.vue"
  export default  {
    name: 'src-components-nav-bar',
    props: [],
    components:{
      Contenedor, //lo registramos
      Header,
      
    },
     beforeMount () {
      this.cambiarAHard()
    },
    mounted () {
       console.log("numero:"+this.valor)
      
      
    },
    update(){
       
    },
    data () {
      return {
        correcto:  "-You Picked Right!-",
        incorrecto:"-------Try Again!------",
        mensaje:   "----------------------------",
        valor:"",
        botones:[],
      } 
    },
    methods: {
     
      evaluar(valor){
        if(valor==this.valor){
          this.mensaje=this.correcto
        }else{
          this.mensaje=this.incorrecto
        }
      },
      resetear(){
        
        location.reload()
      },
      cambiarAHard(){
         this.botones=this.entregarBotones(6)
         this.valor=this.botones[this.getRndInteger(0,6)]
         
         
      },
      cambiarAEasy(){
         this.botones=this.entregarBotones(3)
         this.valor=this.botones[this.getRndInteger(0,3)]
        
      },

      randomInt(){
      return Math.floor(Math.random() * 256);
      },

      createRandomStringColor(){
          let newColor = "rgb(" + this.randomInt() + ", " + this.randomInt() + ", " + this.randomInt() + ")" ;
          return newColor;},
    
        entregarBotones(valor){
        let botones=[]
        for(let i=0;i<valor;i++){
            botones[i]= this.createRandomStringColor()
        }
        return botones
        },
   
    getRndInteger(min, max) {
      return Math.floor(Math.random() * (max - min)) + min;
    },


    },
    
    computed: {

    }
}


</script>

<style scoped lang="css">
  .src-components-nav-bar {
  background: #ffffff;
	height: 30px;
	text-align: center;
	margin: 0;
	margin-top: -30px;

  }
  
  button {
	border: none;
	background-color: white;
	font-family: "Montserrat", "Avenir";
	text-transform: uppercase;
	height: 100%;
	font-weight: 700;
	letter-spacing: 1px;
	color: steelblue;
	transition: all 0.3s;
	outline: none;
  }
  button:hover {
    color: white;
    background-color: steelblue;
  }
  span{
    color:black
  }
</style>
