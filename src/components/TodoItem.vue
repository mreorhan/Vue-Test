<template>
<div v-bind:class="{'is-complete':todo.completed}">
  <input type="checkbox" v-on:change="markComplete"/>
{{todo.title}}
</div>
</template>

<script>
export default{
  name: 'TodoItem',
  props: ['todo'],
  methods: {
    markComplete () {
      this.todo.completed = !this.todo.completed
    }
  }
}
</script>

<style scoped>
.is-complete{
  color:darkred;
}
</style>
