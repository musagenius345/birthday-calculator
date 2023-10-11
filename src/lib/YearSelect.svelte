<script>
  import Input from './Input.svelte'
  export let value;
  let max = new Date().getFullYear()

</script>
<Input name="year" bind:value={value} min="1880" {max} placeholder="YY"/>
 
