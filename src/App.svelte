<script>
  import Todos from "./lib/Todos.svelte";

  let todos = $state([]);
</script>

<main>
  <Todos {todos} />
</main>
