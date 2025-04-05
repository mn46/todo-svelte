<script>
  import SingleTodo from "./SingleTodo.svelte";

  let { todos } = $props();
</script>

<div class="flex flex-col justify-between p-6 rounded-lg bg-white/40">
  {#each todos as todo}
    <SingleTodo {todo} />
  {/each}
</div>
