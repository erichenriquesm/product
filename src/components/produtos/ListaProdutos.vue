<template>
  <div class="container">
    <h1 class="mb-4">Listagem de produtos</h1>
    <b-row class="p-2 bg-dark text-light">
      <b-col>#</b-col>
      <b-col>Nome</b-col>
      <b-col>Valor</b-col>
      <b-col>Decrição</b-col>
      <b-col>Ações</b-col>
    </b-row>

    <b-row v-for="(produto, index) in produtos" :key="index" class="p-2">
      <b-col>{{ produto.id }}</b-col>
      <b-col>{{ produto.name }}</b-col>
      <b-col>{{ produto.value }}</b-col>
      <b-col>{{ produto.description }}</b-col>
      <b-col>
        
      </b-col>
    </b-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      exemplo: "exemplo de variavel vue",
      produtos: [],
    };
  },
  methods: {
    buscaProdutos() {
      fetch("http://192.168.0.120:8001/api/product")
        .then((data) => {
          return data.json();
        })
        .then((data) => {
          this.produtos = data.data;
        });
    },
  },
  created() {
    this.buscaProdutos();
  },
};
</script>

<style>
</style>