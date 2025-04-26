<script>
  import Todos from "./lib/Todos.svelte";

  let todos = $state([]);
</script>

<main
  class="h-screen bg-gradient-to-bl from-white to-primary p-6 lg:p-28 grid lg:grid-cols-2 gap-8"
>
  <Todos {todos} />
</main>
