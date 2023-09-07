<template>
  <div>
    <b-modal id="my-modal" hide-footer title="Using Component Methods">
      <div class="d-block text-center">
        <h3 v-if="!preview">o cara vai inserir os dados</h3>
        <h3 v-else>o cara vai preview da tarefa</h3>
        <button @click="criar">Criar tarefa</button>
      </div>
    </b-modal>
  </div>
</template>

<script>
export default {
 data(){
    return {
        preview: false
    }
 },
 methods:{
    criar(){
        this.preview = true
    }
 }
}
</script>

<style>

</style>