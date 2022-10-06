<script>
  const defaultExpense = {
    category: "Food",
    subcategory: "",
    amount: 0,
    date: "",
  };

  let expense = { ...defaultExpense };

  const submit = () => {
    console.log(expense);
  };

  $: {
    if (currentExpense) {
      expense = currentExpense;
    }
  }
  const getCategories = () => {
    return ["Food", "Transport", "Communication", "Activities", "Pocket money"];
  };

  export let goBack = () => {};
  export let currentExpense = { ...defaultExpense };
</script>

<main>
  <button on:click={goBack}>go back</button>
  <h1>Add expense</h1>
  <select placeholder="Category" bind:value={expense.category}>
    {#each getCategories() as category}
      <option value={category}>{category}</option>
    {/each}
  </select>
  <!-- <input bind:value={expense.subcategory} placeholder="Subcategory" /> -->
  <input bind:value={expense.amount} placeholder="Amount" />
  <input type="datetime-local" bind:value={expense.date} placeholder="Date" />
  <button on:click={submit}>submit</button>
</main>

<style>
  main {
    padding: 16px;
  }
  input,
  select {
    margin-bottom: 8px;
    padding: 18px;
    border: 1px solid #ddd;
    border-radius: 5px;
    max-width: 100%;
    /* height: 50px; */
    box-sizing: border-box;
    width: 100%;
  }
  select {
    appearance: none;
  }

  button {
    background: #ddd;
    border-radius: 5px;
    width: 100%;
    height: 50px;
    margin-top: 16px;
  }
</style>
