<template>
  <div id="app">
    <nav class="navbar navbar-light bg-light">
      <div class="container-fluid t-c">
        <a class="navbar-brand" href="/">Generator QR Code</a>
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
  .t-c{
    display: inline-block !important;
    text-align: center;
  }
  /*Small devices (landscape phones, 576px and up)*/
    @media (min-width: 576px) {
        .t-c{
          display: flex !important;
        }
    }
</style>
