<script>
	import { deleteTodo, toggleTodoCompleted } from '../stores/todoStore';
	export let todo;
</script>

<li class="bg-gray-200 p-5 rounded-md border-2 flex items-center mb-3">
	<input
		type="checkbox"
		name="completed"
		id="completed"
		checked={todo.completed}
		on:change={() => toggleTodoCompleted(todo.id)}
		class="mr-3 form-check h-5 w-5"
	/>

	<p class={`flex-1 text-gray-800 ${todo.completed ? 'line-through' : ''}`}>{todo.text}</p>

	<button
		type="button"
		class="text-sm bg-red-500 text-white rounded-md py-1 px-4 hover:bg-red-700"
		on:click={() => deleteTodo(todo.id)}>Delete</button
	>
</li>
