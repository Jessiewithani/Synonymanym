<script>

import Header from '../../Components/Header/Header.svelte';
import SynonymForm  from '../../Components/SynonymForm/SynonymForm.svelte';
import SynonymContainer from '../../Components/SynonymContainer/SynonymContainer.svelte';

//similar to react, this would be where we fetch from our api then we would need "state" here as well

let word = ''
let synonyms = []

const findSyns = (event) => {
    word = event.detail
    fetch(`https://www.dictionaryapi.com/api/v3/references/thesaurus/json/${word}?key=9b1f77c6-83ee-4110-91ca-eb219d07412c`)
    .then(response => response.json())
    .then(data => synonyms = data[0].meta.syns[0])
    .catch(error => console.log(error))
}

</script>



<main>
    <Header />
    <SynonymForm on:submitSynWord={findSyns}/>
	<SynonymContainer word={word} synonyms={synonyms}/>
	<!-- <p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p> -->
</main>

<style>

	main {
        /* background-color: blanchedalmond; */
        height: 100vh;
        /* background-image: url('') */
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