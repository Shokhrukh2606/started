<template>
  <div id="todo-list-example">
    <form v-on:submit.prevent="addNewToDo">
      <label for="new-todo">Add a todo</label>
      <input v-model="newTodoText" id="new-todo" placeholder="Feed the cat" />
      <button>Add</button>
    </form>
    <ul>
      <li
        is="todo"
        v-for="(todo, index) in todos"
        v-bind:key="todo.id"
        v-bind:title="todo.title"
        v-on:remove="todos.splice(index, 1)"
      ></li>
    </ul>
  </div>
</template>

<script>
import todo from "./Todo.vue";
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  methods: {
    addNewTodo: function() {
      this.todos.push({
        id: this.nextTodoId++,
        title: this.newTodoText
      });
      this.newTodoText = "";
    }
  },
  data: function() {
    var todos = new Object();
    return
    newTodoText: '',
      todos[
        ({
          id: 1,
          title: "Do the dishes"
        },
        {
          id: 2,
          title: " the dishes"
        },
        {
          id: 3,
          title: "dishes"
        },
        {
          id: 4,
          title: "es"
        })
      ];
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
