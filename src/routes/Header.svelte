<script lang="ts">
	type PropTypes = {
		name: string;
	};

	let { name }: PropTypes = $props();
</script>

<div class="border">
	<h1>Header component</h1>
	<h1>Hellow {name}</h1>
</div>
