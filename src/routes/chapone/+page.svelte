<script>
	import ChildrenExample from './Children-example.svelte';
	import DerivedExample from './Derived-example.svelte';
	import LogicExample from './Logic-example.svelte';
	import Propexample from './Propexample.svelte';
	import PropStateTest from './PropStateTest.svelte';
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

<div>
	<ChildrenExample userName="Aravinda">
		<!-- <div>This is children example inside</div> -->

		<div>Children data from inside</div>

		{#snippet secondChild(name)}
			Name is SecondChild {name}
		{/snippet}
	</ChildrenExample>
</div>

<div>
	<PropStateTest name="aravinda" age="15" />
</div>
