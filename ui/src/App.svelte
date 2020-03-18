<script>
	import Die from './Die.svelte';
</script>
<style>
	:global(body) {
		background-color: black;
  	color: white;
		margin: 0;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
      'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
      sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;

	}
	div {
		text-align: center;
	}
	.container { 
  	display: grid;
  	grid-gap: 10px;
	}

</style>
<div class="App container">
	<Die sides=20 />
	<Die sides=10 />
	<Die sides=8 />
	<Die sides=6 />
	<Die sides=4 />
</div>
