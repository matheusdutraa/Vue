<template>
  <div class="container my-5">
    <CadastrarRecado @recadoCadastradoMsg="cadastrar"></CadastrarRecado>
    <listar-recados :recadosProp="recados"></listar-recados>
  </div>
</template>

<script>
import { createDOMCompilerError } from "@vue/compiler-dom";
import axios from "axios";
import CadastrarRecado from "./components/CadastrarRecado.vue";
import ListarRecados from "./components/ListarRecados.vue";

export default {
  name: "App",
  components: {
    CadastrarRecado,
    ListarRecados,
  },

  data() {
    return {
      url : "http://192.100.60.125:8080/RestAPI/rest/recados",
      recados: [],
    };
  },

  methods: {
    cadastrar(recadoTexto) {
      //this.recados.push(recado);

      let recado = {
        texto : recadoTexto
      }
      
      axios.post(this.url, recado).then(()=>{
        console.log(resposta)
      }).catch(()=>{
        console.log(erro)
      });
    },
    buscarMensagem() {
    axios
      .get(this.url)
      .then((resultado) => {
        console.log(resultado["data"]);

        this.recados = resultado["data"];
      })
      .catch((erro) => {
        console.log(erro);
      });
  }
  },
  created() {
    this.buscarMensagem();
  },
  mounted() {
    setInterval(this.buscarMensagem, 3000)
  }
};
</script>

<style>
@import url("https://cdn.jsdelivr.net/npm/bootstrap@5.2.1/dist/css/bootstrap.min.css");
body {
  background-color: black;
  color: bisque;
}
</style>
