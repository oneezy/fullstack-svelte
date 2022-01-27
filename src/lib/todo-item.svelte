<script lang="ts">
  import Button from "$lib/button.svelte";

  export let todo: Todo;
</script>

<div class="grid grid-flow-col items-center bg-white">

  <!-- Done/ Not Done -->
  <form action="" class="">
    <input type="hidden" name="done" value=""/>
    <Button label="Mark done/not done">Done/Not Done</Button>
  </form>

  <!-- Save -->
  <form action="" method="" class="grid grid-flow-col">
    <input type="text" value="{todo.text}" class="flex-1 w-full" placeholder="hello" />
    <Button label="Save todo">Save</Button>
  </form>

  <!-- Delete -->
  <form action="" method="" class="grid grid-flow-col">
    <Button label="Delete todo">Delete</Button>
  </form>
</div>

<style>
  
</style>