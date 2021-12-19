<h1>Guess Gender</h1>
<form on:submit|preventDefault={getName}>
    <label for="name">Name:</label>
    <input id="name" bind:value={name} type="text" />
    <button type="submit">Check</button>
</form>

<script>
    let name=''
    let gender=''
    async function getName() {
  fetch('https://api.genderize.io/?name=Mickey' + name)
	.then((response) => response.json())
	.then((data) => {
  	gender = data.gender; // Path for gender
	});
}
</script>
<p>Gender:{gender}</p>