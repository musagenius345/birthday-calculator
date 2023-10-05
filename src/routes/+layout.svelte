<script> 
	import '../pico.css'
</script>

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
