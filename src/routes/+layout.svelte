<script> 
	import '../pico.css'
</script>
  <svelte:head>
  <title>Age Calculator</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,400;0,700;0,800;1,400;1,700;1,800&display=swap" rel="stylesheet">
<!-- <script src="node_modules/eruda/eruda.js"></script> -->
<!-- <script> -->
<!-- // $:eruda.init(); -->
<!-- // </script> -->

</svelte:head>
<main class="container">
  <slot></slot>
</main>

<style>
/* @font-face */
  :global(:root){
  --purple: hsl(259 100% 65%);
  --lightred: hsl(0 100% 67%);
  --white: hsl(0 0% 100%);
  --off-white: hsl(0 0% 94%);
  --light-grey: hsl(0 0% 86%);
  --smoke-grey: hsl(0 1% 44%);
  --off-black: hsl(0 0% 8%)
}
  :global(body){
    font-family: 'Poppins', sans-serif, Arial;
    min-height: 100vh;
    background-color: var(--light-grey);
    min-height: 100dvh;
    font-size: 32px;
    padding: clamp(7.5rem, 10vw, 10rem);
  }

  main{
    /* margin-block: 15vh; */
    /* margin-block: 15dvh; */
    padding: 0;
    /* margin-inline: auto; */
  }
</style>
