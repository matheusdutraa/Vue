<!--2. 
1 litro pinta até 6 metros quadrados
lata de 18 litros custa 80
galao 3,6 litros custa 25
a. comprar apenas latas de 18 litros;
b. comprar apenas galões de 3,6 litros;
c. desafio (para agradar o professor): misturar latasegalões, de forma que o desperdício de tinta sejamenor.Acrescente 10% de folga e sempre arredonde osvalorespara cima, isto é, considere latas cheias.-->

<template>
    <div id="app">
        <h1>Calculadora de tinta de latas</h1>
        <p>Quantos metros quadrados você quer pintar?</p>
        <input type="number" v-model="metroquadrado" />
        <button @click="calcularLatas()">Calcular</button>
        <h3 id="resposta">...</h3>
        <h1>Calculadora de tinta de galoes</h1>
        <p>Quantos metros quadrados você quer pintar?</p>
        <input type="number" v-model="metroquadrado" />
        <button @click="calcularGaloes()">Calcular</button>
        <h3 id="resposta2">...</h3>
        <h1>Calculadora de tinta economica</h1>
        <p>Quantos metros quadrados você quer pintar?</p>
        <input type="number" v-model="metroquadrado" />
        <button @click="carcularAmbos()">Calcular</button>
        <h3 id="resposta3">...</h3>
    </div>
  
</template>

<script>
    export default{
        name: 'App',
        data(){
            return{
                metroquadrado: 0,
                valor: 0,
                litros: 0,
                latas: 0,
                galoes: 0,

            }
        },
        methods:{
            calcularLatas(){
                this.litros = this.metroquadrado / 6
                while (this.litros > 18){
                    this.latas ++
                    this.valor += 80
                    this.litros -= 18
                }
                while (this.litros > 0){
                    this.latas ++
                    this.valor += 80
                    this.litros = 0
                }
                document.getElementById("resposta").innerHTML = "Você precisa de " + this.latas + " latas de 18 litros." + " O valor total é de R$" + this.valor + ",00."
                this.valor = 0
                this.litros = 0
                this.latas = 0
                this.metroquadrado = 0
            },
            calcularGaloes(){
                this.litros = this.metroquadrado / 6
                while (this.litros > 3.6){
                    this.galoes ++
                    this.valor += 25
                    this.litros -= 3.6
                }
                while (this.litros > 0){
                    this.galoes ++
                    this.valor += 25
                    this.litros = 0
                }
                document.getElementById("resposta2").innerHTML = "Você precisa de " + this.galoes + " galoes de 3.6 litros." + " O valor total é de R$" + this.valor + ",00."
                this.valor = 0
                this.litros = 0
                this.galoes = 0
                this.metroquadrado = 0
            },
            carcularAmbos(){
                this.litros = this.metroquadrado / 6
                while (this.litros > 18){
                    this.latas ++
                    this.valor += 80
                    this.litros -= 18
                }
                while (this.litros > 3.6){
                    this.galoes ++
                    this.valor += 25
                    this.litros -= 3.6
                }
                while (this.litros > 0){
                    this.galoes ++
                    this.valor += 25
                    this.litros = 0
                }
                document.getElementById("resposta3").innerHTML = "Você precisa de " + this.latas + " latas de 18 litros e " + this.galoes + " galoes de 3.6 litros." + " O valor total é de R$" + this.valor + ",00."
                this.valor = 0
                this.litros = 0
                this.latas = 0
                this.galoes = 0
                this.metroquadrado = 0
            }
            }
        }
 
        
    
</script>

<style>
    div{
      border: 2px solid black;
      background-color: #afaead;
    }
    body{
      background-color: #788491;
    }
    #app {
      font-family: 'Avenir', Helvetica, Arial, sans-serif;
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      text-align: center;
      color: #2c3e50;
    }
    
    #resposta {
      color: #000000;
    }
    
    </style>
