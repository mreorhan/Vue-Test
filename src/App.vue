<template>
  <div id="app">
    <img src="./assets/logo.png">
    <HelloWorld/>
    <input type="text" v-model="newItem" @keyup.enter="addNewItem"/>
    <button @click="addNewItem">Add New Item</button>
    <div :class="[isError ? 'isError':'hide']">Error!</div>
  <Todos v-bind:todos="todos"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import Todos from './components/Todos'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Todos
  },
  data () {
    return {
      newItem: '',
      isError: false,
      todos: [
        {id: 1, title: 'Todo one', completed: false},
        {id: 2, title: 'Todo two', completed: true},
        {id: 3, title: 'Todo three', completed: false}
      ]
    }
  },
  methods: {
    addNewItem () {
      if (this.newItem.trim() !== '') {
        this.todos.push({id: this.todos.length + 1, title: this.newItem, completed: false})
        this.isError = false
      } else {
        this.isError = true
      }
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.isError {
    visibility: visible;
  }
.hide{
  visibility: hidden;
}
</style>
