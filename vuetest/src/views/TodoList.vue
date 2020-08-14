<template>
  <div class="todoList">
    <div class="title"> TODO LIST</div>
    <div>
      <ul>
        <li v-for="(item, index) in todoList" >{{ item }} <span class="remove" @click="removeTodo(index)">删除</span></li>
      </ul>
    </div>
    <input type="text" class="input" v-model="inputVal" placeholder="请输入todo"/>
    <div class="btn" @click="addTodo">增加</div>
  </div>
</template>

<script>

export default {
  name: "TodoList",
  data() {
    return {
      todoList: ['你好呀'],
      inputVal: ''
    }
  },
  methods: {
    addTodo() {
      this.todoList.push(this.inputVal || '默认值')
    },
    removeTodo(index) {
      this.todoList.splice(index, 1);
    }
  }
}
</script>

<style scoped>
    .btn {
      border: 1px solid #42b983;
      color: #2c3e50;
    }
    .input {

    }
    .remove {
      color: red;
    }
</style>