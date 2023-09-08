<template>
  <div class="container">
    <h1 class="mb-3">Listagem de produtos</h1>
    <b-row>
      <b-col>#</b-col>
      <b-col>Nome</b-col>
      <b-col>Valor</b-col>
      <b-col>Descrição</b-col>
      <b-col>Ações</b-col>
    </b-row>

    <b-row v-for="(produto, index) in produtos" :key="index">
      <b-col>{{ produto.id }}</b-col>
      <b-col>{{ produto.name }}</b-col>
      <b-col>{{ prdouto.value }}</b-col>
      <b-col>{{produto.description}}</b-col>
      <b-col>
        
      </b-col>
    </b-row>

    
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