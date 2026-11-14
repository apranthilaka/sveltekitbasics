<script lang="ts">
	//state values
	let name: string = $state('');
	let myValue: true | false = $state(false);
	let doorState: 'open' | 'close' = $state('open');

	// methods
	let handleState = () => {
		myValue = !myValue;
	};

	let handleDoorState = () => {
		doorState = doorState === 'open' ? 'close' : 'open';
	};
</script>

<div class="mt-5 border p-5">
	<h1>Stahe binded name</h1>
	<div>My stste name is {name}</div>
	<input type="text" bind:value={name} />

	<h1>State Example 1</h1>
	<div>State is {myValue ? 'State is True' : 'State is False'}</div>
	<button class="border bg-neutral-200 p-2" onclick={handleState}>Change State</button>

	<!-- door state -->
	<h1>State Example 2</h1>
	<div>
		The door is {doorState === 'open' ? ' Open' : 'Close'}
	</div>
	<button onclick={handleDoorState}>Handle Door State</button>
</div>
