<template>
  <div class="inputBox shadow">
    <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo">
    <span class="addContainer" v-on:click="addTodo">
      <i class="fas fa-plus addBtn"></i>
    </span>

    <Modal v-if="showModal" @close="showModal = false">
      <h3 slot="header" class="modalHeader">
        경 고!
        <i class="closeModalBtn fas fa-times" @click="showModal= false" title="닫기"></i>
      </h3>

      <span slot="body">
        아무것도 입력하지 않으셨습니다.
      </span>

    </Modal>

  </div>
</template>

<script>
import Modal from './common/Modal.vue';

  export default {
    data() {
      return {
        newTodoItem: '',
        showModal: false
      }
    },
    methods: {
      addTodo() {
        if (this.newTodoItem !== '') {
          this.$emit("addTodoItem",this.newTodoItem);
          this.clearInput();
        } else {
          this.showModal = !this.showModal;
        }
      },
      clearInput() {
        this.newTodoItem = '';
      }
    },
    components: {
      Modal
    }
  }
</script>

<style scoped>
input:focus {
  outline: none;
}

.inputBox {
  display: flex;
  justify-content: center;
  align-items: center;
  background: white;
  width: 50rem;
  height: 50px;
  line-height: 50px;
  border-radius: 5px;
}

.inputBox input {
  border-style: none;
}

.addContainer {
  float: right;
  background: linear-gradient(to right, #6478FB, #8763fb);
  display: block;
  width: 3rem;
  border-radius: 0 5px 5px 0;
}

.addContainer:hover {
  cursor: pointer;
}

.addBtn {
  color: white;
  vertical-align: middle;
  transition: all 300ms ease-in-out;
}

.addBtn:hover {
  transform: rotate(45deg) scale(1.5);
}

.modalHeader {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: auto;
}

.closeModalBtn {
  color: #42b983;
  margin-left: 20px;
}
.closeModalBtn:hover {
  cursor: pointer;
}
</style>