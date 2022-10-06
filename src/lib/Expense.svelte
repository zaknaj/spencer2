<script>
  export let category = "";
  export let subcategory = "";
  export let amount = 0;
  export let date = "";
</script>

<div class="component" on:click>
  <div class="left">
    <div class="category">{category}</div>
    <div class="subcategory">{subcategory}</div>
  </div>
  <div class="right">
    <div class="date">{date}</div>
    <div class="amount">{amount}</div>
  </div>
</div>

<style>
  .component {
    display: flex;
    border: 1px solid #ddd;
    margin-bottom: 8px;
    padding: 10px;
    justify-content: space-between;
    align-items: center;
    border-radius: 5px;
  }
  .category,
  .date {
    opacity: 0.5;
  }
  .subcategory,
  .amount {
    font-size: 1.2em;
    font-weight: 600;
  }
</style>
