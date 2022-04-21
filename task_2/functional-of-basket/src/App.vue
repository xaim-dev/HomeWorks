<template>
  <div class="wrapper">
    <PriceEditor
      v-model:prodNumberOne.number="prodNumberOne"
      v-model:prodNumberTwo.number="prodNumberTwo"
      v-model:taxOne.number="taxOne"
      v-model:taxTwo.number="taxTwo"
      v-model:countOne.number="productOneCount"
      v-model:countTwo.number="productTwoCount"
    />
    <div class="total">Total: {{ calculate }} ₴</div>
  </div>
</template>

<script>
import PriceEditor from "./components/PriceEditor";

export default {
  name: "App",
  components: {
    PriceEditor,
  },
  data() {
    return {
      prodNumberOne: null,
      prodNumberTwo: null,
      taxOne: null,
      taxTwo: null,
      countOne: null,
      countTwo: null,
    };
  },
  computed: {
    productOneCount() {
      return (this.prodNumberOne / 100) * this.taxOne + this.prodNumberOne;
    },
    productTwoCount() {
      return (this.prodNumberTwo / 100) * this.taxTwo + this.prodNumberTwo;
    },
    calculate() {
      return this.productOneCount + this.productTwoCount;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.wrapper {
  border: 3px solid #000;
  max-width: 507px;
}
.total {
  text-align: left;
  padding-left: 20px;
}
</style>
