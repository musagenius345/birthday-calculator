<script> 
	import '../pico.css'
</script>
  <svelte:head>
<script src="node_modules/eruda/eruda.js"></script>
<script>
$:eruda.init();
</script>

</svelte:head>
<main class="container">
  <slot></slot>
</main>

<style>
  :global(body){
    min-height: 100vh;
    min-height: 100dvh;
  }

  main{
    margin-block: 15vh;
    margin-block: 15dvh;
    padding: 0;
  }
</style>
