<template>
  <li @click="handleDelete">{{content}}</li>
</template>
>

<script>
export default {
  props: ['content', 'index'],
  methods: {
    handleDelete () {
      this.$emit('delete_one', this.index)
    }
  }
}
</script>

<style scoped>
</style>
