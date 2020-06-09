<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <ul>
      <li v-for="todo in todos" :key="todo.id">
        {{todo.title}}
      </li>
    </ul>
  </div>
</template>

<script>
// @ is an alias to /src
import axios from 'axios'
export default {
  name: 'Home',
  data () {
    return {
      todos: []
    }
  },
  mounted () {
    axios.get('https://jsonplaceholder.typicode.com/todos')
      .then((res) => {
        this.todos = res.data
      })
  }
}
</script>
