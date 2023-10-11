<script>
  export let value;
  export let maxDays = 30;

function dayArray(value) {
  return Array.from({ length: value }, (_, index) => index + 1);
}

</script>

<select on:change bind:value={value}>
  {#each dayArray(maxDays) as day}
    <option value={day}>{day}</option>
  {/each}
</select>
