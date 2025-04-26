<script>
  import editIcon from "../assets/edit-svelte.svg";
  import deleteIcon from "../assets/delete-svelte.svg";

  let { todo } = $props();
</script>

<div class="flex justify-between bg-white/80 rounded-lg py-2 px-4 w-full">
  <div class="flex gap-2">
    <input id={`todo-${todo.id}`} type="checkbox" />
    <label for={`todo-${todo.id}`} class="break-all">
      {todo.task}
    </label>
  </div>
  <div class="space-x-2">
    <button>
      <img src={editIcon} />
    </button>
    <button>
      <img src={deleteIcon} />
    </button>
  </div>
</div>
