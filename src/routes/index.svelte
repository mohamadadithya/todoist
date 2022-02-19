<script>
	import TodoForm from '../components/TodoForm.svelte';
	import Todo from '../components/Todo.svelte';
	import { todos } from '../stores/todoStore.js';
</script>

<main class="font-poppins container mx-auto max-w-md px-6">
	<h1 class="text-2xl font-bold pt-10 uppercase tracking-widest">Todoist</h1>
	<TodoForm />
	<ul>
		{#each $todos as todo}
			<Todo {todo} index={todo.id} />
		{/each}
	</ul>
</main>
