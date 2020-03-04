<script>
    import { createEventDispatcher } from 'svelte'; //creates a customEvent. DO NOT bubgle and d.preventDefault() doesn't work with this
    //takes in two arguments, (name, detail);

    //create a function that invokes the createEventDispatcher
    //include what "state" we'll have for the form

    const dispatch = createEventDispatcher();
        //state
        let searchWord = ''
        //do we need one for error handling as well?
    const submitSyn = (event) => {
        event.preventDefault();
        //create the custom event here
        dispatch('submitSynWord', searchWord)
        console.log('searchWord', searchWord)
        //clear out the field here
        searchWord = ''
    }
</script>
<form>
<h2> Insert A Word To Find A Synonym!</h2>
    <input type="text" placeholder="enter a word" bind:value={searchWord} >
    <button type="submit" on:click={submitSyn}>Find!</button>
</form>

<style>
    form {
        background-color: teal;
    }

</style>