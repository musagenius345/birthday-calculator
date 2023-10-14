<script>
  import Input from './Input.svelte'
  export let value
  export let maxDays = '31'

</script>
<Input name="day" bind:value={value} min="1" max="31" placeholder="DD"/>
 
