<template>
  <div id="app">
    <h1 class="ui dividing centered header">Vue.js Todo App</h1>
    <div class='ui three column centered grid'>
      <div class='column'>
        <todo-list v-bind:todos="todos"></todo-list>
      </div>
    </div>
  </div>
</template>



<script>
// import sweetalert from 'sweetalert'
import TodoList from './components/TodoList'

export default {
  name: 'app',
  components: {
    TodoList
  },

  data () {
    return {
      todos: [{
        title: 'Todo A',
        project: 'Project A',
        done: true
      }, {
        title: 'Todo B',
        project: 'Project B',
        done: false
      }, {
        title: 'Todo C',
        project: 'Project C',
        done: true
      }]
    }
  }
}
</script>
