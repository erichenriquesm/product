<template>
  <div class="container">
    <div class="d-flex justify-content-betweeen">
        <h1 class="my-2">Listagem de Produtos</h1>
        <b-button @click="$bvModal.show('my-modal')" variant="outline-success">Criar</b-button>

    </div>
    <b-row class="table-header bg-dark text-white">
      <b-col>#</b-col>
      <b-col>Nome</b-col>
      <b-col>Valor</b-col>
      <b-col>Descrição</b-col>
      <b-col>Ações</b-col>
    </b-row>

    <b-row v-for="(produto, index) in produtos" :key="index" class="table-row">
      <b-col>{{ produto.id }}</b-col>
      <b-col>{{ produto.name }}</b-col>
      <b-col>{{ produto.value }}</b-col>
      <b-col>{{ produto.description }}</b-col>
      <b-col>
        <div class="d-flex gap-2">
          <b-button variant="outline-danger">Excluir</b-button>
          <b-button variant="outline-primary">Editar</b-button>
        </div>
      </b-col>
    </b-row>

    <ProdutoModalVue/>
  </div>
</template>

<script>
import ProdutoModalVue from "./ProdutoModal.vue";
export default {
  components: {
    ProdutoModalVue,
  },
  data() {
    return {
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

<style scoped>
</style>