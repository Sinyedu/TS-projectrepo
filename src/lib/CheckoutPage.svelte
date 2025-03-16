<script>
  let name = "";
  let address = "";
  let cardNumber = "";
  let expiryDate = "";
  let cvv = "";

  function handleSubmit() {
    console.log("Form submitted", {
      name,
      address,
      cardNumber,
      expiryDate,
      cvv,
    });
  }
</script>

<div class="checkout-form">
  <h2>Checkout</h2>
  <form on:submit|preventDefault={handleSubmit}>
    <div>
      <label for="name">Name</label>
      <input type="text" id="name" bind:value={name} required />
    </div>
    <div>
      <label for="address">Address</label>
      <input type="text" id="address" bind:value={address} required />
    </div>
    <div>
      <label for="cardNumber">Card Number</label>
      <input type="text" id="cardNumber" bind:value={cardNumber} required />
    </div>
    <div>
      <label for="expiryDate">Expiry Date</label>
      <input type="text" id="expiryDate" bind:value={expiryDate} required />
    </div>
    <div>
      <label for="cvv">CVV</label>
      <input type="text" id="cvv" bind:value={cvv} required />
    </div>
    <button type="submit">Submit</button>
  </form>
</div>

<style>
  .checkout-form {
    max-width: 400px;
    margin: auto;
    padding: 1rem;
    border: 1px solid #ccc;
    display: flex;
    flex-direction: column;
    justify-content: center;
    border-radius: 5px;
  }

  .checkout-form div {
    margin-bottom: 1rem;
  }

  .checkout-form label {
    display: block;
    margin-bottom: 0.5rem;
  }

  .checkout-form input {
    width: auto;
    padding: 0.5rem;
    border: 1px solid #ccc;
    border-radius: 5px;
  }

  .checkout-form button {
    width: 100%;
    padding: 0.75rem;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }

  .checkout-form button:hover {
    background-color: #0056b3;
  }
</style>
