<template>
  <div id="app">
    <Dropdown></Dropdown>
    <router-view/>
  </div>
</template>

<script>
import Dropdown from '@/components/Dropdown'

export default {
  name: 'App',
  components: {
    Dropdown
  }
}
</script>

<style>
</style>
