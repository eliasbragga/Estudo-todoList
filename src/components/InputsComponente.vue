<template>
  <div>
    <h2>Lista de:{{ nomeList }}</h2>
    <v-col cols="8" sm="4" md="3">
      <v-text-field v-model="itemList" label="Item" placeholder="Digite um item"></v-text-field>
    </v-col>
    <v-btn depressed color="primary" @click="addItemInList"> Adicionar </v-btn>
    <v-btn depressed color="error"  @click="deleteList">Limpar Lista</v-btn>
    
    <div>
      <ul>
        <li v-for="(item, index) in itensList" :key="index"> {{ item }} <v-btn depressed color="error" x-small @click="deleteItem(index)"> Excluir</v-btn></li>
        
      </ul>
    </div>
  <DialogComponente/>
  </div>
</template>

<script>
import DialogComponente from "./DIalogComponente.vue"
export default {
  name: "InputsComponente",
  emits: [],
  props: {
    nomeList:String
  },
  data() {
    return {
     itemList:"",
     itensList:[]
    };
  },
  methods: {
    addItemInList(){
      if(this.itemList){
        this.itensList.push(this.itemList)
        this.itemList = ""
      }
      
    },
    deleteItem(index) {
      this.itensList.splice(index,1)
    } ,
    deleteList(){
      this.itensList = []
    }
    
  },
  components: {
    DialogComponente
  }
  
};
</script>

<style>
</style>