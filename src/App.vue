<template>
  <div id="app">
    <TodoHeader></TodoHeader>
    <TodoInput></TodoInput>
    <TodoList>
    </TodoList>
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
    TodoHeader,
    TodoInput,
    TodoList,
    TodoFooter
  }   
}
</script>

<style>
  * {
    font-family: 'Jua', sans-serif;
  }

  body {
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    /* background-color: #f6f6f6; */
    background: radial-gradient(circle, rgba(238,174,202,1) 0%, rgba(148,187,233,1) 100%);
    margin: auto;
  }

  input {
    border-style: groove;
    width: 50rem;
    height: 50px;
    font-size: 1.5rem;
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