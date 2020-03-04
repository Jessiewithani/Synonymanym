<script>

import Header from '../../Components/Header/Header.svelte';
import SynonymForm  from '../../Components/SynonymForm/SynonymForm.svelte';

</script>



<main>
    <Header />
    <SynonymForm/>
	<!-- <h1>Hello {word}!</h1> -->
	<!-- <p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p> -->
</main>

<style>

	main {
        background-color: blanchedalmond;
        height: 100vh;
		/* text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto; */
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>