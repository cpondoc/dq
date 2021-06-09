<!-- Script -->
<script>

	// Components for UI
	import { Button, Container, Card } from 'sveltestrap';

	// Binding values
	export let quote;
	export let author;

	// Array of names and quotes
		let cats = [
		{ id: 'cpondoc', name: 'I am getting railed in bedwars' }
	];

	// Function to add quotes
	function addNumber() {
		cats.push({id: author, name: quote});
		cats = cats;
		console.log("Yay!");
	}
</script>

<!-- To Import Bootstrap, Google Fonts, and Blocks by Linus library -->
<head>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.1/dist/css/bootstrap.min.css">
  <link rel="preconnect" href="https://fonts.gstatic.com">
  <link href="https://fonts.googleapis.com/css2?family=Fira+Sans:wght@400;600&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://unpkg.com/blocks.css/dist/blocks.min.css" />
</head>

<!-- Main Content -->
<main>

	<!-- Header -->
	<Container>
		<br />
		<h1 class="intro"><span role="img" aria-label="huh">🤔</span> For Dumb Quotes </h1>
		<h4 class="intro">A to-do list, but for dumb quotes.</h4>
		<br />
		<hr />
	</Container>

	<!-- Create Event -->
	<Container>
		<h2> Add a quote! </h2>
		<h4 class="intro">Recollect on past dummy things.</h4>
		<br />
		<h4><span role="img" aria-label="thought">💭</span> Quote: <input class="block" bind:value={quote}></h4>
		<br />
		<h4><span role="img" aria-label="clown">🤡</span> Author: <input class="block" bind:value={author}></h4>
		<br />
		<Button class="block" on:click={addNumber}> Add Quote </Button>
		<br />
		<hr />
	</Container>

	<!-- For each -->
	<Container>
		<br />
		<h2> All Quotes! </h2>
		<h3> Never forget. </h3>
		<br />
		{#each cats as { id, name }, i}
			<Card body class="block">
				<h4 class="quotation">"<i> {name} </i>"</h4>
				<p class="authorship"><span role="img" aria-label="laugh">😂</span>  Author: {id} </p>
			</Card>
			<br />
		{/each}
	</Container>

	<!-- Footer -->
	<Container>
		<p>Built by Chris Pondoc with <span role="img" aria-label="heart">❤️</span></p>
	</Container>
</main>

<!-- CSS Style -->
<style>
	:global(body) {
		font-family: 'Fira Sans', sans-serif !important;
		background: linear-gradient(90deg, #d53369 0%, #daae51 100%) !important;
	}
	.intro {
		color: white;
	}
	h1 {
		font-size: 60px;
		font-weight: bold;
	}
	h2 {
		font-size: 45px;
		font-weight: bold;
		color: white;
	}
	h3 {
		font-size: 30px;
		color: white;
	}
	h4 {
		font-size: 25px;
		color: white;
	}
	.quotation {
		color: black;
		font-size: 35px;
	}
	.authorship {
		font-size: 25px;
	}
</style>