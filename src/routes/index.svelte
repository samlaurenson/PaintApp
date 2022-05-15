<!-- <h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p> -->

<script>
    import Canvas from '../Canvas.svelte';
    let first = 'Samuel';
    let last = 'Laurenson';
    $: name = first + ' ' + last;

    //should change the name of this project to picasso lol
</script>

<main>
    <h1 style='color: red'>Hello {name}</h1>
    <Canvas></Canvas>
</main>

<style>
    :global(body) {
        background-color: rgb(54, 49, 49);
    }
</style>

<!-- <style>
    body {
        background-color: rgb(54, 49, 49);
    }
</style> -->