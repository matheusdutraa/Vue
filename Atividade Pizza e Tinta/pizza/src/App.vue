<!--1. Pizzômetro: Faça uma aplicação em Vue que calcule aquantidade de de pizzas necessárias para uma confraternização.Você deve perguntar a quantidade de adultos e quantidadedecrianças.
Considere que uma pizza gigante possui 12 pedaços, umapizzafamília 10 e uma pizza convencional 8. Considere tambémqueum adulto come em média 3 pedaços e uma criança 2 pedaços-->

<template>
  <div id="app">
    <h1>Pizzômetro</h1>
  <p>Quantidade de adultos:</p>
  <input type="number" v-model="adulto" />
  <p>Quantidade de crianças:</p>
  <input type="number" v-model="crianca" />
  <button @click="calcular()">Calcular</button>
  <h3 id="resposta">...</h3>
  </div>


</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      adulto: 0,
      crianca: 0,
      pizzaGigante: 0,
      pizzaFamilia: 0,
      pizzaConvencional: 0,
      total: 0
    }
  },
  methods: {
    calcular() {
      this.total = this.adulto * 3 + this.crianca * 2
      
      while(this.total > 12) {
        this.pizzaGigante ++
        this.total -= 12
      }
      while (this.total > 10) {
        this.pizzaFamilia ++
        this.total -= 10
      }
      while (this.total > 8) {
        this.pizzaConvencional ++
        this.total -= 8
      }
      while (this.total > 0) {
        this.pizzaConvencional ++
        this.total = 0
      }
      document.getElementById("resposta").innerHTML = "Você precisa de " + this.pizzaGigante + " pizza gigante, " + this.pizzaFamilia + " pizza família e " + this.pizzaConvencional + " pizza convencional."

      this.total = 0
      this.pizzaGigante = 0
      this.pizzaFamilia = 0
      this.pizzaConvencional = 0
      this.adulto = 0
      this.crianca = 0

    }
  },

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
