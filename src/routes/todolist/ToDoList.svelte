<script>
	let newTask = $state();

	let taskList = $state([]);

	let handleAddTask = () => {
		taskList.push(newTask);
		newTask = '';
	};
</script>

<div>
	<div>
		{newTask}
		{taskList}
		<h1>Add list Here</h1>
		<label for="addTask">Add Task</label>
		<input type="text" bind:value={newTask} />
		<button class="border p-2" onclick={handleAddTask}>Add Task</button>
	</div>
	<div>
		Task list

		{#each taskList as task (task)}
			<div class=" flex flex-col">
				<div>
					{task}
				</div>
			</div>
		{/each}
	</div>
</div>

<style>
</style>
