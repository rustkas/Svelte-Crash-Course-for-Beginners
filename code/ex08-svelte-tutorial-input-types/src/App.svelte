<script>
	let name;
	let num;
	let isChecked = !false;
	let value = 2;
	let selected;

	let questions=[
		{id: 1, text: "What is your favorite color?"},
		{id: 2, text: "What is your favorite fruit?"},
		{id: 3, text: "What is your favorite day time?"},
	];
</script>

<main>
	<input type="text" bind:value={name} />
	<input type="number" bind:value={num} />
	<input type="checkbox" bind:checked={isChecked} />

	<label>
		<input type="radio" value={1} bind:group={value}/>
		1
	</label>
	<label>
		<input type="radio" value={2} bind:group={value}/>
		2
	</label>
	<label>
		<input type="radio" value={3} bind:group={value}/>
		3
	</label>	
	
	<select bind:value={selected}>
		{#each questions as question}
			<option value={question}>
				{question.text}
			</option>
		{/each}
	</select>
</main>

<style>
	main {
		display: flex;
		flex-direction: column;
		align-items: center;
	}
</style>
