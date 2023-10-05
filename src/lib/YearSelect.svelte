<script>
  export let value;
</script>

<select bind:value={value}>
  {#each Array.from({ length: 100 }, (_, i) => new Date().getFullYear() - i) as year}
    <option value={year}>{year}</option>
  {/each}
</select>
