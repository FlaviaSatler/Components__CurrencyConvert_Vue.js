<template>
  <div class="convert">
    <h3 class="subtitle">{{ moedaA }} Para {{ moedaB }}</h3>
    <input type="text" v-model="moedaA_value" v-bind:placeholder="moedaA" />
    <input type="button" value="Convert" v-on:click="convert" />
    <h3 class="result">{{ moedaB_value }}</h3>
  </div>
</template>

<script>
export default {
  name: "Convert",
  props: ["moedaA", "moedaB"],
  data() {
    return {
      moedaA_value: "",
      moedaB_value: 0
    };
  },
  methods: {
    convert() {
      let de_para = this.moedaA + "_" + this.moedaB;

      let url =
        "https://free.currencyconverterapi.com/api/v6/convert?q=" +
        de_para +
        "&compact=y";
      fetch(url)
        .then(res => {
          return res.json();
        })
        .then(json => {
          let cotacao = json[de_para].val;
          this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(
            2
          );
        });
    }
  }
};
</script>

<style scoped>
.convert {
  max-width: 300px;
  padding: 20px;
  margin-bottom: 25px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  background-color: #d7cec7;
  border: none;
}

.subtitle {
  color: #565656;
}

.result {
  color: #565656;
}
</style>
