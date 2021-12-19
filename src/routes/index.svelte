<script>
    let name = ''
    let gender = ''

    async function getGender() {
        fetch('https://api.genderize.io/?name=' + name)
        .then((response) => response.json())
        .then((data) => {
  	gender = data.gender; // Path for gender
	});
}
</script>

<h1>Guess Gender</h1>

<form on:submit|preventDefault={getGender}>
    <label for="name">Name:</label>
    <input id="name" bind:value={name} type="text" />
    <button type="submit">Check</button>
</form>

<p>Gender: {gender}</p>