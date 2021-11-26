<script>
	import Alert from "./Announcement.svelte";

	let fruits = [
		{name: "Apple", color: "red", amount: 5, id: 1},
		{name: "Banana", color: "red", amount: 7, id: 2},
		{name: "Grape", color: "red", amount: 3, id: 3},
	];
	//fruits = [];
	const deleteFruit = (id)=>{
		console.log(id);
		
		// True: Keep it in our array
		// False: Remove it from our array
		fruits = fruits.filter((fruit) => fruit.id != id) 
		console.log(fruits);
	};

	let num = 7;
	 num = 10;
</script>

<main>
	<Alert />
	{#each fruits as fruit (fruit.id)}
		{#if fruit.amount < 4}
			<div class="card">
				<h5>{fruit.name}</h5>
				<p>{fruit.color}</p>
				<button on:click={()=>deleteFruit(fruit.id)}>Delete</button>
			</div>
		{:else}
			<p>The amount for {fruit.name} is greater than or equal to 4</p>
		{/if}	
	{:else}
		<p>There is no fruit in our fruit array</p>
	{/each}
	
	{#if fruits.length >0}
	{#if fruits[0]}
	<div class="card">
		<h3>{fruits[0].name}</h3>
		<p>{fruits[0].color}</p>
	</div>
	{/if}
	{#if fruits[1]}
	<div class="card">
		<h3>{fruits[1].name}</h3>
		<p>{fruits[1].color}</p>
	</div>
	{/if}
	{#if fruits[2]}
	<div class="card">
		<h3>{fruits[2].name}</h3>
		<p>{fruits[2].color}</p>
	</div>
	{/if}
	{/if}

	{#if num > 10}
		<p>Greate than 10</p>
	{:else if num < 10}	
		<p>Less than 10</p>
	{:else}	
		<p>Equal to 10</p>
	{/if}
</main>

<style>
	h5, p {
		margin: 4px 0px;
	}
	.card {
		min-width: 400px;
		padding: 8px;
		border-radius: 20px;
		border: 2px solid gray;
		margin-top: 8px;
	}
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