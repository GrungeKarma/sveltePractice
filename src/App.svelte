<script>
	let name = "Tony";
	let age = 31;
	//let upperCaseName; not required!
	$: upperCaseName = name.toUpperCase();
	$: console.log(name);
	$: if (name === "Anthony") {
		age = 55;
	}
	const incrementAge = () => {
		age += 1;
	};
	const changeName = () => {
		name = "Anthony";
	};
	let nameInput = (event) => {
		const enteredValue = event.target.value;
		name = enteredValue;
	};
</script>

<h1>Hello I am {upperCaseName}, my age is {age}!</h1>
<button on:click={incrementAge}>Increase Age</button>

<!-- <button on:click={changeName}>Change Name</button> -->
<input type="text" value={name} on:input={nameInput} />

<style>
	h1 {
		color: slateblue;
	}
</style>
