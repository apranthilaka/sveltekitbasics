<script lang="ts">
	let {
		firstName,
		lastName,
		fakeName
	}: {
		firstName: string;
		lastName: string;
		fakeName?: string | null;
	} = $props();
</script>

<div class="mt-5 border p-5">
	<h1>Prop Example</h1>
	<div>Name is {firstName} {lastName}</div>
	<div>
		<div>replace a with X</div>
		{firstName.replaceAll('a', 'X')}
	</div>
	<div>
		{fakeName}
	</div>
</div>
