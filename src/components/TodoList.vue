<template>
  <div>
     <transition-group name="list" tag="ul">
      <li 
        v-for="( todoItem, index ) in propsdata" 
        v-bind:key="todoItem.item" 
        class="shadow"
      >
        <i 
          class="checkBtn fas fa-check" 
          v-bind:class="{checkBtnCompleted: todoItem.completed}"
          v-on:click="toggleComplete(todoItem, index)"
        >
        </i>
        <span
          v-bind:class="{textCompleted: todoItem.completed}" 
          >
          {{ todoItem.item }}
        </span>
        <span 
          class="removeBtn" 
          v-on:click="removeTodo(todoItem, index)"
        >
          <i class="fas fa-trash-alt"></i>
        </span>
      </li>
     </transition-group>
  </div>
</template>

<script>
  export default {
    props: ['propsdata'],
    methods: {
      removeTodo(todoItem, index) {
        this.$emit('removeItem', todoItem, index);
      }, 
      toggleComplete(todoItem, index) {
        this.$emit('toggleItem', todoItem, index);
      }
    },
   
  }
</script>

<style scoped>
  ul {
    list-style-type: none;
    padding-left: 0;
    margin-top: 0;
    text-align: left;
  }

  li {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 50px;
    height: 50px;
    line-height: 50px;
    margin: 0.5rem 0;
    padding: 0 1.5rem;
    background: white;
    border-radius: 5px;
    font-size: 1.3rem;
  }

  .checkBtn {
    line-height: 45px;
    color: #62acde;
    margin-right: 15px;
    cursor: pointer;
  }

  .checkBtnCompleted {
    color: #b3adad;
  }

  .textCompleted {
    text-decoration: line-through;
    color:#b3adad;
  }

  .removeBtn {
    margin-left: auto;
    color: #de4343;
    cursor: pointer;
    transition: all 300ms ease-in-out;
  }

  .removeBtn:hover {
    transform: scale(1.2);
  }

  .list-enter-active, .list-leave-active {
    transition: all 1s;
  }
  
  .list-enter, .list-leave-to {
    opacity: 0;
    transform: translateY(30px);
  }
</style>