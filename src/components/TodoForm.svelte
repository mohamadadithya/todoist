<script>
	import { addTodo } from '../stores/todoStore.js';
	let todo = '';
	let hasError = false;

	const handleSubmit = () => {
		if (todo === '') {
			hasError = true;
		} else {
			hasError = false;
			addTodo(todo);
			todo = '';
		}
	};
</script>

<form on:submit|preventDefault={handleSubmit} class="bg-gray-200 my-6 p-8 rounded-lg shadow-lg">
	<div class="mb-3">
		<label for="todo" class="block mb-3">Enter your todo</label>
		<input
			type="text"
			class={`p-3 w-full rounded-md mb-1 outline-none focus:border-blue-500 border-2 ${
				hasError === true ? 'border-red-500' : 'border-transparent'
			}`}
			name="todo"
			id="todo"
			placeholder="What you gonna do?"
			bind:value={todo}
			autocomplete="off"
		/>
		<small class={`${hasError === true ? 'block' : 'hidden'} mb-2 text-red-500`}
			>Please enter your todo.</small
		>
	</div>
	<button type="submit" class="bg-blue-500 hover:bg-blue-700 text-white px-4 py-2 w-full rounded-md"
		>Add</button
	>
</form>
