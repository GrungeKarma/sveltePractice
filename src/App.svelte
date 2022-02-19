<script>
	let name = "Anthony";
	let age = 31;
	const incrementAge = () => {
		age += 1;
	};
</script>

<h1>Hello I am {name}, my age is {age}!</h1>
<button on:click={incrementAge}>Increase Age</button>

<style>
	h1 {
		color: purple;
	}
</style>
