<template>
  <div>
    <Todo></Todo>
    <NuxtChild />
  </div>
</template>

<script>
import Todo from '~/components/Todo'

export default {
  components: {
    Todo
  }
}
</script>

<style>
</style>
