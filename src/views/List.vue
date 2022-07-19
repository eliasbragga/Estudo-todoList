<template>
  <div class="about">
    <div>
      <h1>Criar listas</h1>
      <v-col cols="8" sm="4" md="3">
        <v-text-field
          v-model="nomeList"
          label="Lista"
          placeholder="Digite o nome da Lista"
        ></v-text-field>
      </v-col>
      <v-btn depressed color="primary" @click="createList"> Criar Lista </v-btn>
    </div>
    <div v-for="(item, index) in lists" :key="index">
      <InputsComponente :nomeList="item" />
    </div>
  </div>
</template>

<script>
import InputsComponente from "../components/InputsComponente.vue";
export default {
  name: "List",
  data() {
    return {
      nome: "",
      nomeList:"",
      lists:[],

    };
  },
  methods: {    
    createList() {
      if(this.nomeList){
        this.lists.push(this.nomeList)
        this.nomeList = ""
      }
      
    }
  },
  components: {
    InputsComponente,
  },
};
</script>
