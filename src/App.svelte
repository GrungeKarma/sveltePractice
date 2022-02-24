<script>
	import ContactCard from "./ContactCard.svelte";
	let name = "";
	let age = null;
	let jobTitle = "";
	let image = '';
	let shortDescription = "";
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
<button on:click={incrementAge}>Increase Age</button><br>

<!-- <button on:click={changeName}>Change Name</button> -->
<!--<input type="text" value={name} on:input={nameInput} /> -->
<span>name:  </span><input type="text" bind:value={name} /><br>
<span>job title:  </span><input type='text' bind:value={jobTitle}/><br>
<span>image:  </span><input type='text' bind:value={image}/><br>

<span>job description:  </span><textarea rows=3 bind:value={shortDescription}/>
<ContactCard
	userName={name}
	userJobTitle={jobTitle}
	userShortDescription={shortDescription}
	userImage={image}
/>


<style>
	h1 {
		color: slateblue;
	}
</style>
