<script>
  import Input from './Input.svelte'
  export let value;

</script>
<Input name="month" bind:value={value} min="1" max="12" placeholder="MM"/>
  
