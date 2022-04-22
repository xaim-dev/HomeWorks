<template>
  <div class="container">
    <div class="product__one"> Продукт 1:
      <label> Price:
        <input type="number" 
             :value="prodNumberOne"
             @input="$emit('update:prodNumberOne', $event.target.value)">
      </label>
      <label> Tax:
        <input type="number" 
             :value="taxOne"
             @input="$emit('update:taxOne', $event.target.value)">
      </label>
      <label class="count__one"> Count:
        <input type="number" 
             :value="countOne"
             @input="$emit('update:countOne', $event.target.value)"
             disabled>
      </label>
    </div>
    <div class="product__two"> Продукт 2:
      <label> Price:
        <input type="number" 
             :value="prodNumberTwo" 
             @input="$emit('update:prodNumberTwo', $event.target.value)">
      </label>
      <label> Tax:
        <input type="number" 
             :value="taxTwo"
             @input="$emit('update:taxTwo', $event.target.value)">
      </label>
      <label class="count__two"> Count:
        <input type="number" 
             :value="countTwo"
             @input="$emit('update:countTwo', $event.target.value)"
             disabled>
      </label>
    </div>
    
  </div>
</template>

<script>
export default {
  name: "PriceEditor",
  props: {
    prodNumberOne: {
      type: Number,
    },
    prodNumberTwo: {
      type: Number,
    },
    taxOne: {
      type: Number,
    },
    taxTwo: {
      type: Number,
    },
  },
  computed: {
    countOne() {
      return ((this.prodNumberOne / 100) * this.taxOne) + this.prodNumberOne
    },
    countTwo() {
        return ((this.prodNumberTwo / 100) * this.taxTwo) + this.prodNumberTwo
    },
  }
};
</script>

<style lang="css" scoped>
.container {
  display: flex;
}
.product__one,
.product__two {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  border-bottom: 2px solid #000;
  padding: 15px;
}
.product__one {
  border-right: 2px solid #000;
}
.count__one,
.count__two {
  border-top: 1px solid #000;
  margin-top: 10px;
  padding-top: 5px;
}
</style>