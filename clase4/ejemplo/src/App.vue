<script>
  import Menu from './components/Menu.vue'
  import Info from './components/Info.vue'
  export default {
    components: {Menu, Info},
    data() {
      return {
        unUsuario: 'PNT2-Adrian'
      }
    }
  }
</script>

<template>
  <div>
    <Menu/>
    <Info :usuario="unUsuario"/>
  </div>
</template>

<style scoped>
</style>
