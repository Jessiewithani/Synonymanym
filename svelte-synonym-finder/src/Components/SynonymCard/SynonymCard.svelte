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
        background-color: pink;
        margin-right: 10px;
        height: 80px;
        width: 200px;
    }
</style>