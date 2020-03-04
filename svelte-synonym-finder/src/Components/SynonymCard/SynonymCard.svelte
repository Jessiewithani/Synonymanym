<script>
    //we need to create another custom event
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();
    export let word

    const handleOnClick = (event) => {
        event.preventDefault();
        dispatch('showMoreSynonyms', word)
    }

    //when you click on the word, it needs to show more words. so it doesn't need  button
</script>

<div on:click={handleOnClick}>
    <h3>{word}</h3>
</div>

<style>
    div {
        background-color: white;
        margin-right: 30px;
        height: 50px; 
        width: 200px;
        border-radius: 6px;
        border: 3px solid olive;
        /* border-color: olive; */
        /* letter-spacing: 2px; */
        overflow: scroll;
    }
    h3 {
        font-size: 1.8em;
        text-align: center;
        margin-top: 8px;
        letter-spacing: 2px;
        /* overflow: scroll; */
    }
</style>