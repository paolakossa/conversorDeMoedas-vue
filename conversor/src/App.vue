<template>
  <div id="app">
    <h1>Conversor de Moedas💵</h1>
    <div class="linha">
    <Conversor moeda-a="USD" moeda-b="BRL"/>
    <Conversor moeda-a="BRL" moeda-b="USD"/>
  </div>
  <div class="linha">
    <Conversor moeda-a="CAD" moeda-b="BRL"/>
    <Conversor moeda-a="BRL" moeda-b="CAD"/>
  </div>
  <div class="linha">
    <Conversor moeda-a="EUR" moeda-b="BRL"/>
    <Conversor moeda-a="BRL" moeda-b="EUR"/>
  </div>
  </div>
</template>

<script>
import Conversor from './components/Conversor.vue';
export default {
  name: 'App',
  components: {
    Conversor
  }
}
</script>

<style>
#app {
  margin: auto;
  max-width: 900px;
  font-family: 'Poppins', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2A3990;
  margin-top: 60px;
 
}

.linha{
  display: flex;
  justify-content: space-around;
  margin-top: 40px;
}
</style>
