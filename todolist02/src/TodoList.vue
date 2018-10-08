<template>
  <div>
    <div>
      <input v-model="inputValue"  @keyup.enter="handleSubmit"/>
      <button @click="handleSubmit">提交</button>
    </div>
    <ul>
      <todo-item v-for="(item, index) of list" :index="index" :key="index" :content="item" @delete_one="handleDelete">
      </todo-item>
    </ul>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem'
export default {
  components: {
    'todo-item': TodoItem
  },
  data () {
    return {
      list: [],
      inputValue: ''
    }
  },
  methods: {
    handleSubmit () {
      this.list.push(this.inputValue)
      this.inputValue = ''
    },
    handleDelete (index) {
      this.list.splice(index, 1)
    }
  }
}
</script>

<style>
</style>
