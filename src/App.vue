<template>
  <div id="app">
    <nav class="navbar navbar-light navbar-bg">
      <div class="container-fluid t-c">
        <h1>
          <a class="navbar-brand app-tittle-color" href="/">Generator QR Code</a>
        </h1>
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
  .app-tittle-color{
    color: white !important;
  }
  .navbar-bg{
    background-color: #4caf50 !important;
  }
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
