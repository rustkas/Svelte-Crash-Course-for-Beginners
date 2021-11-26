<script>
	import Button from './Button.svelte';
</script>

<main>
	<Button btnText={"Hello world"} />
	<Button>Title</Button>
</main>

<style>
	main{
		display: flex;
		flex-direction: column;
		align-items: center;
	}
</style>