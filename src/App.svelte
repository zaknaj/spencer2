<script>
  import AddExpense from "./lib/AddExpense.svelte";
  import Categories from "./lib/Categories.svelte";
  import ExpensesList from "./lib/ExpensesList.svelte";

  let page = "expenses";

  let currentExpense = null;
  const setExpense = (expense) => {
    currentExpense = expense;
    page = "add";
  };
</script>

<div id="main">
  {#if page === "expenses"}
    <ExpensesList onExpenseClick={setExpense} goToAdd={() => (page = "add")} />
  {/if}
  {#if page === "add"}
    <AddExpense
      {currentExpense}
      goBack={() => {
        page = "expenses";
        currentExpense = null;
      }}
    />
  {/if}

  {#if page === "categories"}
    <Categories goBack={() => (page = "expenses")} />
  {/if}
</div>

<style>
  #main {
    max-width: 400px;
    margin: 0 auto;
  }
</style>
