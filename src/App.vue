<template>
  <div id="app">
      <Horloge/>
      <TodoList/>
      <DoneList/>
  </div>
</template>

<script>
import Horloge from './components/Horloge.vue'
import TodoList from './components/TodoList.vue'
import DoneList from './components/DoneList.vue'

export default {
  name: 'App',
  components: {
    TodoList,
    Horloge,
    DoneList
  }
}
</script>

<style>

</style>
