
<template>
  <div>
    <p class='tasks'>Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
    <p class='tasks'>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
   <!-- // we are now passing the data to the todo component to render the todo list -->
    <todo  v-on:delete-todo="deleteTodo" v-for="todo in todos" v-bind:todo="todo"></todo>
  </div>
</template>

<script type = "text/javascript" >
import sweetalert from 'sweetalert'
import Todo from './Todo'

export default {
  props: ['todos'],
  components: {
    Todo
  },
  methods: {
    completeTodo (todo) {
      const todoIndex = this.todos.indexOf(todo)
      this.todos[todoIndex].done = true
      sweetalert('Success!', 'To-Do completed!', 'success')
    },
    deleteTodo (todo) {
      this.todos.splice(this.todos.indexOf(todo), 1)
    }
  }
}
</script>
