<script>
import axios from "axios";
export default {
  data() {
    return {
      cep: "",
      resultado: {},
    };
  },
  methods: {
    async buscar() {
      const url = `https://viacep.com.br/ws/${this.cep}/json/`;
      const { data } = await axios.get(url);
      this.endereço = data;
    },
  },
};
</script>

<template>
  <h1>Buscar Cep</h1>
  <form @submit.prevent="buscar">
    <input type="text" v-model="cep" placeholder="Digite o CEP" />
    <button type="submit">Buscar</button>
  </form>
  <div 
    <label for="rua">Rua</label>
    <input name="rua" type="text" v-model="endereco.logradouro"/>
    <p> Complemento: {{ endereco.complemento}}</p>
    <p> Cidade: {{ endereco.localidade}}</p>
    <p> Estado: {{ endereco.uf}}</p>
  </div>
</template>
