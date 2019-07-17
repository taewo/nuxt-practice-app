<template>
  <div class="container">
    <input @keyup="handleKeyup" v-model="inputText" type="text">
    <input @click="addTodo" type="button" value="+">
    <ul>
      <li v-for="(todo, index) in todoList" :key="index">
        <input @change="handleCheckbox(index)" :id="index" type="checkbox" :checked="todo.finish">
        <label v-if="todo.finish" :for="index"><del>{{ todo.content }}</del></label>
        <label v-else :for="index">{{ todo.content }}</label>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Todo',
  data() {
    return {
      inputText: '',
      todoList: [
        {
          finish: false,
          content: 'hello'
        }
      ]
    }
  },
  methods: {
    handleCheckbox(index) {
      this.todoList[index].finish = !this.todoList[index].finish
    },
    handleKeyup(e) {
      if(e.keyCode == 13) {
        this.addTodo()
      }
    },
    addTodo() {
      if(this.inputText == '') return
      this.todoList.push({
        finish: false,
        content: this.inputText
      })
      this.inputText = ''

    }
  }
}
</script>

<style scoped>

.container {padding:10px;}

</style>
