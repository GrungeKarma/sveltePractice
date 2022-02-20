<script>
	import ContactCard from "./ContactCard.svelte";
	let name = "Tony";
	let age = 31;
	let jobTitle = "Web Dev";
	let shortDescription =
		"I work as the Website Administrator and Developer for Full Moon Productions";
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
<!--<input type="text" value={name} on:input={nameInput} /> -->
<input type="text" bind:value={name} />
<ContactCard
	userName={name}
	userJobTitle={jobTitle}
	userShortDescription={shortDescription}
/>

<style>
	h1 {
		color: slateblue;
	}
</style>
