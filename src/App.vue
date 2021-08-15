<template>
  <div id="app">
    <h2> Agrega una tarea a la lista</h2>
    <input type="text" name="addTodo" id="addTodo" v-model="addToList" placeholder="ej. estudiar vue js">
    <button type="submit" @click="addItem">Agregar</button>
    <h1> Lista de tareas </h1>
    <ul id="todoList">
      <li v-for="(item, index) in list" :key="item">{{index+1}} : {{item}}</li>
    </ul>
  </div>
</template>

<script>


export default {
  name: "ToDo",
  el: '#todoList',
  data() {
        return {
          addToList: '',
          list: [
            'Regar las plantas',
            'Limpiar areneros',
          ]
        }
  }, 
  methods:{
    addItem(){
      this.list.push(this.addToList)
      this.addToList = ''
    }
  }
};
</script>

<style>
  ul{
    list-style: none;
    text-align: start;
  }
</style>
