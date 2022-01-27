<script context="module" lang="ts">
  import type { Load } from "@sveltejs/kit"

  export const load: Load = async ({ fetch }) => {
    const res = await fetch('/api/todos.json')

    if (res.ok) {
      const todos = await res.json()
      return {
        props: { todos }
      }
    }

    const { message } = await res.json()
    return {
      error: new Error(message)
    }
  }
</script>

<script lang="ts">
  import TodoItem from "$lib/todo-item.svelte";

  export let todos: Todo[];

  const title = "Todo List";
</script>

<svelte:head>
  <title>{title}</title>
</svelte:head>

<div class="todos grid gap-4 mx-auto text-center">
  <h1 class="text-2xl text-center">{title}</h1>
  
  <form action="api/todos.json" method="post" class="new text-center">
    <input type="text" name="text" aria-label="Add a todo" placeholder="+ type to add a todo">
  </form>
  
  {#each todos as todo}
    <TodoItem {todo} />
  {/each}
</div>

<style>
  .todos :global(input) {
    font-size: 1.5rem;
    padding: 0.5rem;
    border: 1px solid transparent;
    border-radius: 4px;
  }

  .todos :global(input:focus-visible) {
    border: 1px solid red;
  }
  .new {
    
  }
</style>