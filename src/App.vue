<template>
  <div class="container">
    <section>
      <input type="text" class="input-group" v-model="inputTodo">
      <button class="btn-success btn" @click="addTodo">Add</button>
    </section>
    <ul class="list-group">
      <li class="list-group-item" v-for="(todo, index) in todoList" :key="index">
        <span>{{ todo }}</span>
        <button class="btn btn-danger btn-sm float-right" @click="deleteTodo(index)">Delete</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      inputTodo: "",
      todoList: ['Buy groceries', 'Finish homework']
    }
  },
  methods: {
    addTodo() {
      if (this.inputTodo.trim() !== '') {
        this.todoList.push(this.inputTodo);
        this.inputTodo = '';
      }
    },
    deleteTodo(index) {
      this.todoList.splice(index, 1);
    }
  }
}
</script>

<style>
section{
  text-align: -webkit-center;
}
.container {
  max-width: 400px;
  margin: auto;
  padding: 150px;
  
}

.input-group {
  margin-bottom: 10px;
  border-radius: 1px;
}

.list-group-item {
  margin-bottom: 5px;
  position: relative;
  list-style: none;
}

.btn-danger {
  position: absolute;
  top: 50%;
  right: 10px;
  transform: translateY(-50%);
  background-color: red;
    color: white;
    border-radius: 5px;
    border: none;
    padding: 2px;
    width: 80px;
    height: 20px;
    font-weight: 700;
}
.btn-success {
  background-color: blue;
    color: white;
    margin-left: 10px;
    border-radius: 5px;
    border: none;
    padding: 2px;
    width: 80px;
    height: 25px;
    font-weight: 700;
}
</style>
