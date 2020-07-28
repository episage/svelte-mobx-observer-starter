<script>
	import { observable, autorun, reaction } from 'mobx';
	export let name;

	let moo = observable({
		deep: ({
			nested:{
				counter: 7,
			}
		})
	})

	// autorun(()=>{
	// 	console.log(`autorun moo ${moo.deep.nested.counter}`);
	// });

	// reaction(()=>{
	// 	console.log(`reaction moo ${moo.deep.nested.counter}`);
	// 	return {};
	// },()=>{
	// 	console.log(`rerereaction MOO`);
	// })

	window.moo = moo;
</script>

<main on:click={()=>moo.deep.nested.counter=4}>
	<h1>{moo.deep.nested.counter}</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>