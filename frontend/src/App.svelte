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


<script>	
	async function fetchMessage(){
		const message = await fetch("http://localhost:8000/test")
		const jsn = await message.json()

		if (message.ok){
			console.log
			return jsn.Message
		}
		throw new Error(text)
	};

	let name = fetchMessage()


</script>

<main>

{#await name}
	<h1>Hello World!</h1>
{:then message}
	<h1>Hello {message}!</h1>
{:catch error}
	<p style="color: red">{error.message}</p>
{/await}

<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
</main>
