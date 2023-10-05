<script>
  export let value;
  export let maxDays;
</script>

<select bind:value={value}>
  {#each Array.from({ length: maxDays }, (_, i) => i + 1) as day}
    <option value={day}>{day}</option>
  {/each}
</select>
