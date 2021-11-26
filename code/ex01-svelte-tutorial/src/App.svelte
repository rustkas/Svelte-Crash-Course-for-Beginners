<script>
	let name = "Evan";
	let src = "favicon.png";
	let count = 0;

	let firstName = "";
	let lastName = "";

	const incrementCounter = () => {
		count++;
	}

	const handleInput = (event) => {
		name = event.target.value;
	}

	const resetName = () => {
		name = "Unknown";
	}

	$: fullName = `${firstName} ${lastName}`;
	$: {
		console.log(lastName);
		console.log(firstName);
	}
</script>

<main>
	<h1>Hello {name}</h1>
	<h2>Hello {fullName}</h2>
	<h3>Counter: {count}</h3>
	
	<label> First Name:
		<input type="text" bind:value={firstName} />
	</label>
	<label>Last Name:
		<input type="text" bind:value={lastName}/>
	</label>

	<input type="text" on:input={handleInput} value={name}/>
	<input type="text" bind:value={name}/>
	<button on:click="{resetName}">Set name to Unknown</button>
	<button on:click="{incrementCounter}">Add 1 to Counter</button>
	<img {src} alt="Svelte logo" />
</main>

<style>
	main {
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	h1 {
		font-size: 72px;
		text-align: center;
	}
	h3{
		font-size: 38px;
	}
</style>