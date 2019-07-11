<template>
  <div>
    <h3>Todos</h3>
    <div v-bind:key="todo.id" v-for="todo in todos" >
      <TodoItem v-bind:todo="todo"/>
    </div>
  </div>
</template>

<script>
import TodoItem from './TodoItem'

export default {
  name: 'Todos',
  components: {TodoItem},
  props: ['todos'],
  comments: {
    TodoItem
  }
}
</script>

<style scoped>
  </style>
