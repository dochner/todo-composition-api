<script>
import { ref, computed } from '@nuxtjs/composition-api'
export default {
  name: 'TdTodoList',

  setup() {
    const cardWidth = computed(function() {
      switch(this.$vuetify.breakpoint.name){
        case 'xs': return 300
        case 'sm': return 350
        case 'md': return 500
      }
      return 500
    })

    const todoText = ref('')
    const todos = ref([])

    function addTodo(text) {
      if(text) {
        todos.value.push({'text': text, 'done': false})
      } else {
        return ''
      }
    }

  return { cardWidth, todos, addTodo }
  }
}
</script>

<template lang="pug">
  v-card(
    dark
    elevation-4
    :width="cardWidth"
  )
    v-card-title(
      class="white--text font-weight-bold"
    )
      | Todo app
    
    v-list
      v-list-item(v-for="(todo, i) in todos" :key="`${todo}${i}`")
        v-checkbox(
          :label="todo.text"
          :v-model="todo.done"
          :class="todo.done ? 'text-decoration-line-through': ''"
        )
    
    v-form
    v-text-field(
      v-model="todoText"
      dark
      outlined
      dense
      class="px-4"
    )
    v-card-actions
      v-btn(
        block
        @click="addTodo(todoText)"
      )
        | Add Todo

</template>

