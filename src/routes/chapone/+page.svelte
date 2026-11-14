<script>
	import DerivedExample from './Derived-example.svelte';
	import LogicExample from './Logic-example.svelte';
	import Propexample from './Propexample.svelte';
	import StateExample from './State-example.svelte';

	//this is a stateless variable
	let firstName = 'Aravinda';
	let lastName = 'Ranthilaka';
</script>

<div>
	<Propexample {firstName} {lastName} />
</div>

<div>
	<StateExample />
</div>

<div>
	<DerivedExample />
</div>

<div>
	<LogicExample />
</div>
