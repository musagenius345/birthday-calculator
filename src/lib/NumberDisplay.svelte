<script>
  import { slide, blur } from 'svelte/transition';
  import { linear } from 'svelte/easing';

  export let value;
  export let units;

  let previousValue = null;

  const options = {
        duration: 500, // Animation duration in milliseconds
        easing: linear // Easing function for the animation
    }
</script>

<div> 
  <p>
    {#key value}
    <span class="num" in:slide={options} >{value}</span> 
    {/key}
    <span>{units}</span>
  </p>
</div>

<style>
  .num {
    display: inline-block;
  }
  p{
    font-size: 3.3rem;
    font-weight: 700;
    color: var(--smoke-grey);

  }

  .num{
    color: var(--purple);
  }
  p:not(.num){
    font-style: italic;
    color: black;
  }
</style>
