<template>
  <q-page padding>
    <div class="row q-mb-lg">
      <q-input v-model="newTask" placeholder="Ajouter un nom" class="col" @keyup.enter="addTask"/>
        <q-btn color="light-green" size="sm" label="Ajouter" @click.native="addTask" style="background-color: #026b33; color:white;"/> 
    </div>


    <div class="row q-mb-lg">
    <q-list highlight class="col">
      <q-list-header> Dossier en attente</q-list-header>
      <q-item clickable v-ripple v-for="(task ,index) in tasks" >
        <q-item-section>{{task}}</q-item-section>
        <q-item-section avatar>
          <q-icon color="green" name="check" @click.native="moveToDone(index)"/>
        </q-item-section>
      </q-item>

    </q-list>  
    </div>


    <div class="row q-mb-lg">
    <q-list highlight class="col">
      <q-list-header>Fait</q-list-header>
      <q-item clickable v-ripple v-for="(task ,index) in done">
        <q-item-section>{{task}}</q-item-section>
        <q-item-section avatar>
          <q-icon color="red" name="close" @click.native="deleteTask(index)" />
        </q-item-section>
      </q-item>

    </q-list>  
    </div>
  </q-page>
</template>

<style>
</style>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'IndexPage',
  data(){
    return{
      tasks:[],
      done:[],
      newTask:''
    }
  },
  methods:{
    addTask(){
      this.tasks.push(this.newTask)
      this.newTask =''
    },
    moveToDone(index){
      this.done.push(this.tasks[index])
      this.tasks.splice(index,1)
    },
    deleteTask(index){
      this.$q.dialog({
        title:"Confirmation",
        message:"Voulez-vous vraiment effacer ce nom?",
        ok:'Oui',
        cancel:'Non'
      }).onOk(() =>{
        this.done.splice(index,1)
        console.log('allo')
        this.$q.notify('Effacé avec succès')
      }).catch(()=>{
      })
    }
  }
})
</script>
