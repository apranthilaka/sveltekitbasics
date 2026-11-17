<script lang="ts">
	import type { Snippet } from 'svelte';

	let {
		children,
		userName,
		secondChild
	}: {
		userName: string;
		children: Snippet;
		secondChild: Snippet;
	} = $props();
</script>

<div class="mt-5 border p-5">
	<h1>Children Example</h1>
	<div>User name is {userName}</div>
	<div>{@render children()}</div>
	<div>{@render secondChild('Ara')}</div>
</div>
