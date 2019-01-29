<template>
  <div id="app">
    <h1 class="title">Currency Convert</h1>
    <div class="linha">
      <Convert moeda-a="USD" moeda-b="BRL" />
      <Convert moeda-a="BRL" moeda-b="USD" />
    </div>
    <div class="linha">
      <Convert moeda-a="CAD" moeda-b="BRL" />
      <Convert moeda-a="BRL" moeda-b="CAD" />
    </div>
    <div class="linha">
      <Convert moeda-a="EUR" moeda-b="BRL" />
      <Convert moeda-a="BRL" moeda-b="EUR" />
    </div>
  </div>
</template>

<script>
import Convert from "./components/Convert";
export default {
  name: "App",
  components: {
    Convert
  }
};
</script>

<style>
body {
  background-color: #d9d9d9;
}
#app {
  margin: 0 auto;
  max-width: 900px;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}

.title {
  color: #565656;
}

.linha {
  margin: 10px 0;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}
</style>
