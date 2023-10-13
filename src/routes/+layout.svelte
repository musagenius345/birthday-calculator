<script> 
	import '../pico.css'
</script>
  <svelte:head>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,400;0,700;0,800;1,400;1,700;1,800&display=swap" rel="stylesheet">
<script src="node_modules/eruda/eruda.js"></script>
<script>
$:eruda.init();
</script>

</svelte:head>
<main class="container">
  <slot></slot>
</main>

<style>
/* @font-face */

  :global(body){
    font-family: 'Poppins', sans-serif, Arial;
    min-height: 100vh;
    min-height: 100dvh;
  font-size: 32px;
  }

  main{
    /* margin-block: 15vh; */
    /* margin-block: 15dvh; */
    padding: 0;
  }
</style>
