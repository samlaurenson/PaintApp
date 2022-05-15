<script lang="ts">
    import PaintColour from "./PaintColour.svelte";
    import BrushThickness from "./BrushThickness.svelte";
    export let context : any;

    // function handleclick() {
    //     context.beginPath();
    //     context.moveTo(0,0);
    //     context.lineTo(500,500);
    //     context.stroke();
    // }
</script>

<div>
    <div class="column">
        <PaintColour colour="black" context={context}></PaintColour>
        <PaintColour colour="red" context={context}></PaintColour>
        <PaintColour colour="green" context={context}></PaintColour>
        <PaintColour colour="rgb(100, 20, 20)" context={context}></PaintColour>
    </div>
    <div class="column">
        <PaintColour colour="white" context={context}></PaintColour>
        <PaintColour colour="purple" context={context}></PaintColour>
        <PaintColour colour="blue" context={context}></PaintColour>
        <PaintColour colour="rgb(217, 255, 1)" context={context}></PaintColour>
    </div>

    <div class="thicknessContainer">
        <BrushThickness thickness=1 context={context}></BrushThickness>
        <BrushThickness thickness=3 context={context}></BrushThickness>
        <BrushThickness thickness=5 context={context}></BrushThickness>
        <BrushThickness thickness=8 context={context}></BrushThickness>
        <BrushThickness thickness=10 context={context}></BrushThickness>
    </div>
</div>

<style>
    div {
        background-color: rgb(100, 97, 97);
        height: 500px;
        width: 200px;
        border-radius: 5px 5px 5px 5px;
        padding: 5px 5px 5px 5px;
        position: relative;
    }

    .column {
        height: 300px;
        float: left;
        margin: 0 -30px 0 30px;
        width: 75px;
    }

    .thicknessContainer {
        position: absolute;
        bottom: 0px;
        height: 180px;
        width: 190px;
    }
</style>