<script>
  import Input from './Input.svelte'
  export let value
  export let maxDays = 30

</script>
<Input name="day" bind:value={value} min="1" max={maxDays} placeholder="DD"/>
 
