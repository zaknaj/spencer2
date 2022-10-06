<script>
  import Expense from "./Expense.svelte";

  const getExpenses = () => {
    return [
      {
        category: "Food",
        subcategory: "Groceries",
        date: "Thu 6 Oct",
        amount: 6,
        id: 1,
      },
      {
        category: "Food",
        subcategory: "Groceries",
        date: "Thu 6 Oct",
        amount: 7,
        id: 2,
      },
      {
        category: "Food",
        subcategory: "Groceries",
        date: "Thu 6 Oct",
        amount: 8,
        id: 3,
      },
      {
        category: "Food",
        subcategory: "Groceries",
        date: "Thu 6 Oct",
        amount: 123,
        id: 4,
      },
    ];
  };

  export let goToAdd = () => {};
  export let onExpenseClick = (expense) => {};
</script>

<main>
  {#each getExpenses() as expense}
    <Expense
      on:click={() => onExpenseClick(expense)}
      category={expense.category}
      subcategory={expense.subcategory}
      date={expense.date}
      amount={expense.amount}
    />
  {/each}

  <button on:click={goToAdd}>Add an expense</button>
</main>

<style>
  main {
    padding: 16px;
  }
  button {
    background: #ddd;
    border-radius: 5px;
    width: 100%;
    height: 50px;
    margin-top: 16px;
  }
</style>
