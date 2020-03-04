<script>
    //to use "props" from different components, you have to export it
    import SynonymCard from '../../Components/SynonymCard/SynonymCard.svelte';
    export let word
    export let synonyms

const findSyns = (event) => {
    word = event.detail
    fetch(`https://www.dictionaryapi.com/api/v3/references/thesaurus/json/${word}?key=9b1f77c6-83ee-4110-91ca-eb219d07412c`)
    .then(response => response.json())
    .then(data => synonyms = data[0].meta.syns[0])
    .catch(error => console.log(error))
}
    //use each block to map through the synonyms to make a card
</script>
<h3>Here are your synonyms for {word}</h3>
<div>
    {#each synonyms as word}
    <SynonymCard word={word} on:showMoreSynonyms={findSyns}/>
    {/each}
</div>
<style>
    div {
        background-color: rgb(191, 191, 122);
        height: 400px;
        display: flex;
    }
</style>