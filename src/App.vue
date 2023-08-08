<template>
  <div id="app">
    <h1 class="title">Currency Converter</h1>
    <div class="line">
      <ConverterComponent currency-a="USD" currency-b="BRL" />
      <ConverterComponent currency-a="BRL" currency-b="USD" />
    </div>
    <div class="line">
      <ConverterComponent currency-a="EUR" currency-b="BRL" />
      <ConverterComponent currency-a="BRL" currency-b="EUR" />
    </div>
    <div class="line">
      <ConverterComponent currency-a="CAD" currency-b="BRL" />
      <ConverterComponent currency-a="BRL" currency-b="CAD" />
    </div>
    <div class="line">
      <ConverterComponent currency-a="EUR" currency-b="USD" />
      <ConverterComponent currency-a="USD" currency-b="EUR" />
    </div>
    <div class="line">
      <ConverterComponent currency-a="CAD" currency-b="USD" />
      <ConverterComponent currency-a="USD" currency-b="CAD" />
    </div>
  </div>
</template>

<script>
import ConverterComponent from './components/ConverterComponent.vue';
export default {
  name: 'App',
  components: {
    ConverterComponent,
  }
}
</script>

<style>
#app {
  margin: auto;
  max-width: 900px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

.title {
  text-align: center;
}

.line {
  display: flex;
  justify-content: space-around;
  margin-top: 40px;
}
</style>
