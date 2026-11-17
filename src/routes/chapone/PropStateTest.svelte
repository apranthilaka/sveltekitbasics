<script>
	let value = $state(10);
	let { name, age } = $props();
</script>

<div>
	<div>My name is {name} and my ahe is {age}</div>
	{#if value >= 10}
		my value is {value}
	{:else}
		my value is smaller than 10
	{/if}
</div>
