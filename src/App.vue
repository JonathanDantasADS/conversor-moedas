<template>
  <div id="app">
    <h1 class="center">Conversor de moedas</h1>
    <div class="card">
      <Conversor class="item" moeda-a="USD" moeda-b="BRL"/>
      <Conversor class="item" moeda-a="BRL" moeda-b="USD"/>
    </div>

    <div class="card">
      <Conversor class="item" moeda-a="CAD" moeda-b="BRL"/>
      <Conversor class="item" moeda-a="BRL" moeda-b="CAD"/>
    </div>

    <div class="card">
      <Conversor class="item" moeda-a="EUR" moeda-b="BRL"/>
      <Conversor class="item" moeda-a="BRL" moeda-b="EUR"/>
    </div>

  </div>
</template>

<script>

import Conversor from "./components/Conversor.vue";
export default {
  name: 'app',
  components: {
    Conversor
  }
}
</script>

<style>


#app {
  margin: auto;
  max-width: 900px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.center {
  align-content: center;
}

.card {
  display: flex;
  justify-content: space-around;
  margin-top: 50px;
  }

.item {
  border-radius: 20%;
}
 
</style>


