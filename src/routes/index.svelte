<script>
  import TodoItem from "$lib/todo-item.svelte";

  const title = "Todo List";
</script>

<svelte:head>
  <title>{title}</title>
</svelte:head>

<h1 class="text-2xl text-center">{title}</h1>

<form action="" method="" class="text-center">
  <input type="text" name="text" aria-label="Add a todo" placeholder="+ type to add a todo">
</form>

<TodoItem />
<TodoItem />
<TodoItem />