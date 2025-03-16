<script>
  import Checkout from "./lib/CheckoutPage.svelte";
  import ProductList from "./lib/ProductList.svelte";
</script>

<main>
  <h1>Welcome to Our Store</h1>
  <ProductList />
  <Checkout />
</main>

<style>
  main {
    padding: 1rem;
  }
</style>
