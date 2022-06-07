<script>
    export let todos;
  </script>
  
  <ul>
    {#each todos as todo (todo.id)}
    <li class:completed="{todo.completed}">
      <label>
        <input type="checkbox" bind:checked="{todo.completed}" />
        {todo.text}
      </label>
    </li>
    {/each}
  </ul>
  
  <style>
    .completed {
      text-decoration: line-through;
    }
  </style>