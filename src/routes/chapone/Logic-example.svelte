<script>
	let formState = $state({
		name: '',
		birthday: '',
		step: 0,
		error: ''
	});
</script>

<main>
	<div>
		Step: {formState.step + 1}
		{#if formState.error}
			{formState.error}
		{/if}
	</div>
	{#if formState.step === 0}
		<div>
			<label for="">Enter Name</label>
			<input type="text" id="" bind:value={formState.name} /> <br />
			<button
				class=" border p-2"
				onclick={() => {
					if (formState.name != '') {
						formState.step += 1;
						formState.error = '';
					} else {
						formState.error = 'Enter your name, you canr keep it blank';
					}
				}}>Next</button
			>
		</div>
	{:else if formState.step === 1}
		<div>
			<label for="">Enter Birthday</label>
			<input type="date" id="" bind:value={formState.birthday} /> <br />
			<button
				class=" border p-2"
				onclick={() => {
					if (formState.birthday != '') {
						formState.step += 1;
						formState.error = '';
					} else {
						formState.error = 'Enter your birthday, you canr keep it blank';
					}
				}}>Next</button
			>
		</div>
	{:else}
		<div>Form ended</div>
	{/if}
</main>
