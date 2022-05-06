<template>
    <div id="app">
        <h2>TODO List</h2>
 
        <form v-on:submit.prevent>
            <input type="text" v-model="newItem">
            <button v-on:click="addItem">Add</button>
        </form>
        <pre>{{$data}}</pre>
 
    </div>
</template>
 
<script>
export default {
  data () {
    return {
      newItem: '',
      todos: []
    }
  },
  methods: {
    addItem: function (event) {
      if (this.newItem === '') {
        return
      }
      var todo = {
        item: this.newItem
      }
      this.todos.push(todo)
      this.newItem = ''
    }
  }
}
</script>
