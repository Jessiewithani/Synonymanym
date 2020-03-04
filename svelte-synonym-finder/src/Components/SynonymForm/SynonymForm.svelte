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
<div>

<!-- <h2> Insert A Word To Find A Synonym!</h2> -->

    <input type="text" placeholder="enter a word to find a synonym" bind:value={searchWord} >
    <button type="submit" on:click={submitSyn}>Find!</button>

</div>

<style>
    div {
        /* background-color:pink; */
        height: 100px;
        text-align: center;
    }
    input {
        font-size: 2em;
        width: 500px;
        text-align: center;
        border:none;
        border-bottom: 4px solid black;
        /* border-radius: 6px; */
        margin-top: 25px;
        letter-spacing: 1px;
        background-color: transparent;
    }
    button {
        font-size: 2em;
        /* margin-left:-4px; */
        /* border: none; */
        border-radius: 6px;
        margin-left: 20px;
        letter-spacing: 0.5px;
        border: 3px solid olive;
    }

</style>