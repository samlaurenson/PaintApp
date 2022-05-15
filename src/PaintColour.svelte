<script lang="ts">
    export let colour : String;
    export let context : any;

    function handleclick() {
        context.strokeStyle = colour;
    }

    //would be cool if i could get the colours in the pallete to bounce 
    //when hovering over them
    //would be nice if they left a shadow below them too 
</script>

<div class="bounce" on:click={handleclick} style="background-color: {colour}"></div>


<style>
    div { 
        background-color: white;
        cursor: pointer;
        height: 30px;
        width: 30px;
        margin: 10px 0px 20px 0px;
        border-radius: 5px 5px 5px 5px;
        border-color: black;
        border-style: solid;
        border-width: 1px;

        box-shadow: 0 1px 2px rgba(0,0,0,0.3);

        animation-duration: 2s;
        animation-iteration-count: infinite;
        transform-origin: bottom;
        
    }

    .bounce:hover {
        animation-name: bounce;
        animation-timing-function: ease;
    }

    /* .bounce:hover::after {
        animation-duration: 2s;
        animation-iteration-count: infinite;
        transform-origin: bottom;
        animation-name: bounce;
        animation-timing-function: ease;
    } */

    @keyframes bounce {
        0%   { transform: translateY(0); }
        50%  { transform: translateY(-8px); box-shadow: 0 5px 15px rgba(0,0,0,0.6); opacity: 1;}
        100% { transform: translateY(0); }
    }
</style>