<script>
	let agenda = [];
	let newAgenda = '';

	function addAgenda() {
		if (newAgenda.trim() !== '') {
			agenda = [...agenda, newAgenda];
			newAgenda = '';
		}
	}

	function removeAgenda(index) {
		agenda = agenda.filter((_, i) => i !== index);
	}
</script>

<main>
	<h1>Traktandenliste</h1>

	<div class="input-container">
		<input
			type="text"
			bind:value={newAgenda}
			placeholder="Neues Traktandum eingeben"
		/>
		<button on:click={addAgenda}>Add</button>
	</div>

	<ul>
		{#each agenda as item, index}
			<li>
				{item}
				<button on:click={() => removeAgenda(index)}>Remove</button>
			</li>
		{/each}
	</ul>
</main>

<style>
	main {
		max-width: 500px;
		margin: 0 auto;
		font-family: Arial, sans-serif;
	}

	h1 {
		text-align: center;
	}

	.input-container {
		display: flex;
		gap: 10px;
		margin-bottom: 20px;
	}

	input {
		flex: 1;
		padding: 5px;
	}

	button {
		padding: 5px 10px;
		cursor: pointer;
	}

	ul {
		list-style: none;
		padding: 0;
	}

	li {
		display: flex;
		justify-content: space-between;
		margin-bottom: 10px;
	}
</style>