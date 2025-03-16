<script>
  import { onMount } from "svelte";
  import { cart } from "../stores/cartStore";

  let products = [];

  onMount(async () => {
    const response = await fetch("/products/products.json");
    products = await response.json();
  });

  function addToCart(product) {
    cart.update((items) => {
      const existingItem = items.find((item) => item.id === product.id);
      if (existingItem) {
        existingItem.quantity += 1;
      } else {
        items.push({ ...product, quantity: 1 });
      }
      return [...items];
    });
  }
</script>

<div class="products">
  <h2>Products</h2>
  <div class="product-list">
    {#each products as product}
      <div class="product">
        <h3>{product.name}</h3>
        <p>{product.description}</p>
        <p><strong>${product.price.toFixed(2)}</strong></p>
        <button on:click={() => addToCart(product)}>Add to Cart</button>
      </div>
    {/each}
  </div>
</div>

<style>
  .product-list {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 1rem;
  }

  .product {
    border: 1px solid #ddd;
    padding: 1rem;
    border-radius: 5px;
    text-align: center;
  }

  .product button {
    background-color: #007bff;
    color: white;
    padding: 0.5rem;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }

  .product button:hover {
    background-color: #0056b3;
  }
</style>
