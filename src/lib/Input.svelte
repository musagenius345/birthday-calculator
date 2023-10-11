<script>
  export let value;
  export let max
  export let min
  export let placeholder
  export let name
  function handleKeyDown(event) {
    if (event.key === 'ArrowUp' && value < max) {
      value += 1;
    } else if (event.key === 'ArrowDown' && value > 1) {
      value -= 1;
    }
  }

  // function uppercaseName(node){
  //   node.currentTarget.value.toUpperCase()
  //
  //   return{
  //     update(newParam){
  //       node.currentTarget.value.toUpperCase()
  //     }
  //   }
  // }
</script>

 <div>
  <label for={name}>{name}:</label>
<input name={name} id={name} type="number" bind:value={value} placeholder={placeholder} on:keydown={handleKeyDown} min={min} max={max} />
</div>

<style>
  label{
    display: block;
    text-transform: uppercase;
  }
</style>
