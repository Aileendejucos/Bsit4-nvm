<template>
  <div id="app">
    <header>
      <h1>Product Price Calculator</h1>
    </header>
    <main>
      <section>
        <h2>Product Information</h2>
        <label for="productName">Product Name:</label>
        <input v-model="productName" type="text" id="productName" />

        <label for="basePrice">Base Price:</label>
        <input v-model.number="basePrice" type="number" id="basePrice" />

        <label for="quantity">Quantity:</label>
        <input v-model.number="quantity" type="number" id="quantity" />

        <label for="discount">Discount (%):</label>
        <input v-model.number="discount" type="number" id="discount" />

        <button @click="calculatePrice">Calculate Price</button>
      </section>

      <section v-if="calculatedPrice !== null">
        <h2>Calculated Price</h2>
        <p>
          The total price for {{ quantity }} {{ productName }}(s) is:
          ${{ calculatedPrice.toFixed(2) }}
        </p>
      </section>
    </main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      productName: "",
      basePrice: 0,
      quantity: 0,
      discount: 0,
      calculatedPrice: null,
    };
  },
  methods: {
    calculatePrice() {
      const discountedPrice = this.basePrice * ((100 - this.discount) / 100);
      this.calculatedPrice = discountedPrice * this.quantity;
    },
  },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

header {
  background-color: #41b883;
  padding: 20px;
  color: white;
}

main {
  display: flex;
  justify-content: center;
  align-items: center;
}

section {
  margin: 20px;
}

button {
  background-color: #41b883;
  color: white;
  padding: 10px;
  cursor: pointer;
  border: none;
  border-radius: 5px;
}
</style>