<script lang="ts">
    import { onMount } from "svelte";
    import Colours from "./Colours.svelte";


    let drawing = false; //flag to determine if user is currently drawing on the canvas
    let selectedColour = 'black'; //colour user will be drawing with
    let holding = false;

    let prevX = 0;
    let prevY = 0;
    let currX = 0;
    let currY = 0;

    let width = 800;
    let height = 800;

    let canvas : any;
    let ctx : any;

    onMount(() => {
        canvas.width = width;
        canvas.height = height;
        ctx = canvas.getContext('2d');
        ctx.lineWidth = 2;
        ctx.strokeStyle = "black";
    });

    function setMouseCoords(event : MouseEvent) {
        currX = event.offsetX * canvas.width / canvas.clientWidth;
        currY = event.offsetY * canvas.height / canvas.clientHeight;
    }


    function handleMousedown(event: MouseEvent) {
        drawing = true;
        setMouseCoords(event);
        ctx.beginPath();
        ctx.moveTo(currX, currY);
    }

    function handleMouseUp(event : MouseEvent) {
        setMouseCoords(event);
        drawing = false;
    }

    function handleMousemove(event: MouseEvent) {
        if(drawing) {
            setMouseCoords(event);
            draw();
        }
    }

    function handleMouseOut(event : MouseEvent | FocusEvent) {
        drawing = false;
        ctx.lineTo(currX, currY);
        ctx.stroke();
    }

    function draw() {
        ctx.lineTo(currX, currY);
        ctx.stroke();
    }
</script>

<canvas on:mouseout={handleMouseOut} on:blur={handleMouseOut} on:mousemove={handleMousemove} on:mouseup={handleMouseUp} on:mousedown={handleMousedown} bind:this={canvas}>
</canvas>

<Colours context={ctx}></Colours>

<style>
    canvas {
        background-color: white;
        margin-left: 25vw;
        position: absolute;
        cursor: crosshair;
        /* margin: 10vh 20vw 20vw 10vh;
        height: 80vh;*/
    }
</style>