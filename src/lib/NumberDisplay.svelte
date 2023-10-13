<script lang="ts">
  export let value: string
  export let units: strings
  export let size 
</script>
<div style="display: contents">
  <p>
    <span class="num">{value}</span> {units.toUpperCase()}</p>
</div>
<style>
  p{
    --font-size: 2rem;
    font-size: var(--font-size);
    font-weight: 700;
    color: var(--smoke-grey);

  }

  .num{
    color: var(--purple);
  }
</style>
