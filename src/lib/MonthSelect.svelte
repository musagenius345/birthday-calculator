<script>
  export let value;
  function handleKeyDown(event) {
    if (event.key === 'ArrowUp' && value < maxDays) {
      value += 1;
    } else if (event.key === 'ArrowDown' && value > 1) {
      value -= 1;
    }
  }
</script>

  
<input type="number" bind:value={value} on:keydown={handleKeyDown} min="1" max="12" />
