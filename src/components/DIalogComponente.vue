<template>
  <div>
     <v-col cols="auto">
      <v-dialog v-model="dialog"
        transition="dialog-top-transition"
        max-width="600"
      >        
        <template>
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >ALERTA</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12">Deseja excluir a lista?</div>
            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="$emit('fecharAlerta')"
              >Cancelar</v-btn>
              <v-btn
                text
                @click="$emit('clearList')"
                depressed color="error"
              >Excluir</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>
  </div>
</template>

<script>
export default {
    name:"DialogComponente",
    emits:["fecharAlerta","clearList"],
    data(){
        return {
            
        }
    },
    props:{
      dialog:Boolean
    },
    methods:{
      
    }
}
</script>

<style>

</style>