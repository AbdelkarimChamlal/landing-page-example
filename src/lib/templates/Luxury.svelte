<script>
    import Hero from './Hero.svelte';

    export let item;
    export let getItem;
    
</script>


<Hero item={getItem(item, "hero")} getItem={getItem}></Hero>
