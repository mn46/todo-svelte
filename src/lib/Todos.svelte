<script>
  import SingleTodo from "./SingleTodo.svelte";

  let { todos } = $props();

  let newTodoTask = $state("");

  const handleAddTodo = () => {
    const newTodo = {
      id: todos.length + 1,
      task: newTodoTask,
      status: "doing",
    };

    todos.push(newTodo);
  };
</script>

<div class="flex flex-col justify-between p-6 rounded-lg bg-white/40">
  {#each todos as todo}
    <SingleTodo {todo} />
  {/each}

  <div>
    <input type="text" bind:value={newTodoTask} />
    <button onclick={() => handleAddTodo()}>Add todo</button>
  </div>
</div>
