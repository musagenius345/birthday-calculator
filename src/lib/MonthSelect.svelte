<script>
  export let value;
</script>

<select on:change bind:value={value}>
  {#each Array.from({ length: 12 }, (_, i) => i + 1) as month}
    <option value={month}>{month}</option>
  {/each}
</select>
