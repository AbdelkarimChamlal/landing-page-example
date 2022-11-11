<script>
    import { bind } from "svelte/internal";

    export let item;
    export let getItem;

    let text;
</script>

<div class="row">
    <img src={getItem(item, "image").value} alt="hero is a hero">
    <div class="hero-text">
        <h1>{getItem(item, "headline").value}</h1>
        <h2>{getItem(item, "subtitle").value}</h2>
    </div>

    <input bind:value={text} >
</div>


<style>
    .row{
        display: flex;
    }
</style>