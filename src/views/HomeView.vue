<template>
  <div>
    <ListaProdutos/>
  </div>
</template>

<script>
// @ is an alias to /src
import ListaProdutos from "@/components/produtos/ListaProdutos.vue";

export default {
  name: 'HomeView',
  components:{
    ListaProdutos
  }
}
</script>
