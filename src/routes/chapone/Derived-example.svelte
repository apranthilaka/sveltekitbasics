<script lang="ts">
	let firstName: string = $state('Aravinda');
	let lastName: string = $state('Ranthilaka');

	// state value depend on other state values
	let fullName = $derived(firstName + ' ' + lastName);
</script>

<div class="mt-5 border p-5">
	<div>Derived Example</div>
	<div>
		{fullName}
	</div>
</div>
