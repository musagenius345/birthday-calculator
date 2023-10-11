<script>
  export let value = value < 10 ? value.padStart();
  export let maxUnits


  function handleKeyDown(event) {
    if (event.key === 'ArrowUp' && value < maxDays) {
      value += 1;
    } else if (event.key === 'ArrowDown' && value > 1) {
      value -= 1;
    }
  }
</script>


<input type="number" bind:value={value} on:keydown={handleKeyDown}>
