<template>
  <div>
      <input type="text" class="todo-input" placeholder="What needs to be done today"
      v-model="newTodo" @keyup.enter="addTodo">
    <div v-for="todo in todos" :key="todo.id" class="todo-item"></div>
    {{ todo.title }}
  </div>
</template>

<script>
export default {
  name: 'todo',
  data () {
    return {
      newTodo: '',
      idForTodo: 3,
       todos: [
           {
               'id': 1,
               'title': 'Finish Vue Assignment',
               'completed': false
           },
            {
               'id': 2,
               'title': 'Create javascript project',
               'completed': false
           },
       ]
    }
  },
  methods: {
      addTodo() {
          this.todos.push({
              id: this.isForTodo,
              title: this.newTodo,
              completed: false,
          })

          this.newTodo = ''
          this.idForTodo++
      }
  }
    
}
</script>


<style>
.todo-input {
    width:100%;
    padding: 10px 18px;
    font-size: 18px;
    margin-bottom: 16px;

}

</style>
