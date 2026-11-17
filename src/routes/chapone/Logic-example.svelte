<script lang="ts">
	let formState = $state({
		answers: {},
		step: 0,
		error: ''
	});

	let questions = [
		{
			id: 'name',
			type: 'text',
			question: 'what is your name?'
		},
		{
			id: 'birthday',
			type: 'date',
			question: 'what is your birthday?'
		},
		{
			id: 'color',
			type: 'color',
			question: 'what is your color?'
		}
	];

	let handleNext = (val: string) => {
		if (formState.answers[val]) {
			formState.step += 1;
			formState.error = '';
		} else {
			formState.error = `Fill in the ${val} information`;
		}
	};
</script>

<main class="mt-5 border p-5">
	<div>
		{#if formState.step >= questions.length}
			<p>Thank You!</p>
		{:else}
			Step: {formState.step + 1}
		{/if}
		{#if formState.error}
			<div class="error">
				{formState.error}
			</div>
		{/if}
	</div>
	{#each questions as question, index (question.id)}
		{#if formState.step === index}
			{@render formStep({ name: question.id, type: question.type, question: question.question })}
		{/if}
	{/each}
	{JSON.stringify(formState)}
</main>

<!-- main snippet  -->
{#snippet formStep({ name, type, question }: { name: string; type: string; question: string })}
	<div>
		<label for={name}>{question}</label>
		<input {type} bind:value={formState.answers[name]} />
		<button class="border p-2" onclick={() => handleNext(name)}>Next</button>
	</div>
{/snippet}

<style>
	.error {
		color: red;
	}
</style>
