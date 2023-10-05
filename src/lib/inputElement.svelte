<script>
  export let name
  let value
  if((name === day || month) && (value < 10)){
    value = value.padStart(2,0)}
  }
</script>
<input type="number" {name} id={name} {value}>
