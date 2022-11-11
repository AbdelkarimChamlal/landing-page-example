<script>
  import data from './assets/data.json';
	import { onMount } from 'svelte';


  let dynamicLoader =  async (templateName) => {
    switch (templateName) {
      case 'luxury':
        return (await import('./lib/templates/Luxury.svelte')).default;
      case 'hero':
        return (await import('./lib/templates/Hero.svelte')).default;
    }
  }


  let getItem = (template, attributeName) => {
    return template.value.filter((item)=>{
      if(item.name == attributeName){
        return item;
      }
    })[0] ?? null;
  }

  let Component;

  onMount(async () => {
		Component = await dynamicLoader(data.name);
	});


</script>


<svelte:component this={Component} item={data} getItem={getItem}>

</svelte:component>
