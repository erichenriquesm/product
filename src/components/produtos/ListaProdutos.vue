<template>
  <div class="container">
    <h1>Lista de produtos</h1>
    <b-row class="table-header bg-dark text-white">
      <b-col>#</b-col>
      <b-col>Nome</b-col>
      <b-col>Valor</b-col>
      <b-col>Descrição</b-col>
      <b-col>Ações</b-col>
    </b-row>
    {{ produtos }}
  </div>
</template>

<script>
export default {
  data() {
    return {
      teste: "ok",
      produtos: [],
    };
  },
  methods: {
    buscaProdutos() {
      fetch("http://192.168.0.120:8001/api/product")
        .then((data) => {
          return data.json();
        })
        .then((produtos) => {
          this.produtos = produtos.data;
        });
    },
  },
  created() {
    // executa coias antes do html ser rendizerado
    this.buscaProdutos();
  },
};
</script>

<style>
</style>