<script>
export default {
  name: 'Layout'
}
</script>

<template lang="pug">
v-app
  td-navbar
  v-container(
    fluid
    fill-height
  )
    nuxt
  td-footer
</template>
