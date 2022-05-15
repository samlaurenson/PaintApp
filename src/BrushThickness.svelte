<script lang="ts">
    export let thickness : any;
    export let context : any;

    function handleClick() {
        context.lineWidth = thickness;
    }
</script>

<div class="brushButton" on:click={handleClick}>
    <div style="height: {thickness}px;"></div>
</div>

<style>
    div {
        width: 100%;
        background-color: black;
        margin: 5px 0px 0px 0px;
    }

    .brushButton {
        height: 25px;
        width: 100%;
        cursor: pointer;
        background-color: rgb(100, 97, 97);

        transition: .2s ease;
    }

    .brushButton:hover {
        transform: scale(1.11, 1.1);
    }
</style>