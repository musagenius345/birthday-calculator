<script lang="ts">
  export let value: string
  export let units: strings
  export let size 
</script>
<div style="display: contents">
  <p>{value} {units.toUpperCase()}</p>
</div>
<style>
  p{
    --font-size: 2rem;
    font-size: var(--font-size);

  }
</style>
