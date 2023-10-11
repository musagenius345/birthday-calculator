<script>
  export let value

  function handleKeyDown(event) {
    if (event.key === 'ArrowUp' && value < maxDays) {
      value += 1;
    } else if (event.key === 'ArrowDown' && value > 1) {
      value -= 1;
    }
  }
</script>

<input type="number" on:keydown={handleKeyDown} max={new Date().getFullYear()} min="1880" bind:value={value}>
