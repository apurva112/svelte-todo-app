<script>
	import AddTodoForm from './AddTodoForm.svelte';
	import TodoListItems from './TodoListItems.svelte';
  
	export let name;
	let todos = [
	  { id: 1, text: 'Walk the dog', completed: false },
	  { id: 2, text: 'Mop the floors', completed: true },
	];
  
	function addTodo(text) {
	  // Create an ID that's 1 more than the current largest
	  const id = Math.max(...todos.map(({ id }) => id)) + 1;
	  todos = [...todos, { id, text, completed: false }];
	}
  </script>
  
  <main>
	<h1>{name}'s Todo List!</h1>
	<TodoListItems {todos} />
	<AddTodoForm {addTodo} />
  </main>
  
  <style>
	main {
	  padding: 1em;
	  max-width: 40em;
	  margin: 0 auto;
	}
  
	h1 {
	  color: #ff3e00;
	  text-transform: uppercase;
	  font-size: 4em;
	  font-weight: 100;
	}
  </style>