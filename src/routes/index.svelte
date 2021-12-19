<script>
let age = ""
let name = ""

async function getName() {
    fetch('https://api.agify.io/?name=' + name)
    .then((response) => response.json())
    .then((data) => {
        age = data.age
    })
}
</script>

<h1>Weather App</h1>
<p>Age: {age}</p>
<form on:submit|preventDefault={getName}>
    <label for="name">Name:</label>
    <input id="name" bind:value={name} type="text" />
    <button type="submit">Check</button>
</form>
