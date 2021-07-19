<template>
  <div class="clearAllContainer">
    <span class="clearAllBtn" v-on:click="clearTodo">Clear All</span>
  </div>
</template>

<script>
import { mapMutations } from 'vuex';

  export default {
    methods: {
      ...mapMutations({
        clearTodo : 'clearAllItems'
      })
    }
  }
</script>

<style scoped>
  .clearAllContainer {
    width: 8.5rem;
    height: 50px;
    font-size: 1.5rem;
    line-height:50px;
    background-color: white;
    border-radius: 5px;
    margin: 0 auto;
  }
  .clearAllContainer:hover {
    background: linear-gradient(90deg, rgba(131,58,180,1) 0%, rgba(253,29,29,1) 50%, rgba(252,176,69,1) 100%);
    cursor: pointer;
  }
  .clearAllBtn {
    display: block;
    color: #e20303;
  }
  .clearAllBtn:hover {
    color: white;
  }
</style>