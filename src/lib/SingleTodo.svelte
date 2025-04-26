<script>
  import editIcon from "../assets/edit-svelte.svg";
  import deleteIcon from "../assets/delete-svelte.svg";

  let { todo } = $props();
  let isEditing = $state(false);
  let editValue = $state(todo.task);

  const handleToggleIsEditing = () => {
    isEditing = !isEditing;
  };

  const handleSaveTodo = () => {
    todo.task = editValue;
    handleToggleIsEditing();
  };
</script>

<div class="flex justify-between bg-white/80 rounded-lg py-2 px-4 w-full">
  {#if isEditing}
    <div class="w-full flex gap-2">
      <input
        class="w-full bg-white rounded-full border-2 border-text"
        bind:value={editValue}
      />
      <button
        class="min-w-max bg-primary rounded-full py-1 px-2 border-2 border-text"
        onclick={() => handleSaveTodo()}>Save todo</button
      >
    </div>
  {:else}
    <div class="flex gap-2">
      <input id={`todo-${todo.id}`} type="checkbox" />
      <label for={`todo-${todo.id}`} class="break-all">
        {todo.task}
      </label>
    </div>
    <div class="space-x-2">
      <button aria-label="edit" onclick={() => handleToggleIsEditing()}>
        <img src={editIcon} alt="edit icon" />
      </button>
      <button aria-label="delete">
        <img src={deleteIcon} alt="delete icon" />
      </button>
    </div>
  {/if}
</div>
