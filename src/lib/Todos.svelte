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

  <div class="w-full flex flex-col md:flex-row gap-2">
    <input
      type="text"
      bind:value={newTodoTask}
      class="w-full bg-white rounded-full border-2 border-text"
    />
    <button
      onclick={() => handleAddTodo()}
      class="min-w-max bg-primary rounded-lg py-1 px-2 border-2 border-text"
      >Add todo</button
    >
  </div>
</div>
