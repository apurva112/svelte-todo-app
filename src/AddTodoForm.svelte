<script>
    export let addTodo;
    let text = "";
  </script>
  
  <div>
    <form
      on:submit={(e) => {
        e.preventDefault();
        if (text.trim() !== 0) {
          addTodo(text);
          text = "";
        }
      }}
    >
      <label for="new-todo">New Todo Item:</label><br />
      <input id="new-todo" bind:value={text} /><br />
      <button>Add Todo</button>
    </form>
  </div>