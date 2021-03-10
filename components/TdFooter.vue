<script>
export default {
  name: 'TdFooter'
}
</script>

<template lang="pug">
  v-footer(
    dark
    app
  )
    div(
      class="text-center mx-auto"
    )
      | {{ new Date().getFullYear() }} — <strong>Todo app - by Douglas Ochner</strong>
</template>

