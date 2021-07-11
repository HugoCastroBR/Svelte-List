<script>

	import {setContext} from 'svelte';
	import {writable} from 'svelte/store';
	
	import List from './components/List/index.svelte'
	import Input from './components/Input/index.svelte'

	let itemList = writable([
		{
			name: "Carne",
			price: 10,
			alreadyBought: false 
		},
		{
			name: "Teste",
			price: 32,
			alreadyBought: false 
		},
	])

	setContext('cart',itemList)

</script>


<main>
	<h1>Cart</h1>
	<Input/>
	<List/>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		margin: 0 auto;
	}

	h1 {
		margin-left: 28px;
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