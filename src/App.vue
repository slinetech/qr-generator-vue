<template>
  <div id="app">
    <nav class="navbar navbar-light bg-light">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">Generator QR Code</a>
      </div>
    </nav>
    <Generator />
  </div>
</template>

<script>
import Generator from './components/qr/Generator.vue'

export default {
  name: 'App',
  components: {
    Generator
  }
}
</script>

<style>

</style>
