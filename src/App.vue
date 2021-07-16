<template>
  <div id="app">
    <TodoHeader></TodoHeader>
    <TodoInput></TodoInput>
    <TodoList></TodoList>
    <TodoFooter></TodoFooter>
  </div>
</template>

<script>
import TodoHeader from './components/TodoHeader.vue'
import TodoInput from './components/TodoInput.vue'
import TodoList from './components/TodoList.vue'
import TodoFooter from './components/TodoFooter.vue'


export default {
    components: {
      "TodoHeader" : TodoHeader,
      "TodoInput" : TodoInput,
      "TodoList" : TodoList,
      "TodoFooter": TodoFooter
    }   
}
</script>

<style>
  body {
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    background-color: #f6f6f6;
    margin: auto;
  }

  input {
    border-style: groove;
    width: 50rem;
    height: 50px;
    text-align: center;
    border-radius: 5px;
  }

  button {
    border-style: groove;
  }

  .shadow {
    box-shadow: 5px 10px 10px rgba(0, 0, 0, 0.03);
  }
</style>