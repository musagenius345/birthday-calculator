<script lang="ts">
  import YearSelect from '$lib/YearSelect.svelte';
  import MonthSelect from '$lib/MonthSelect.svelte';
  import DaySelect from '$lib/DaySelect.svelte';
  import { differenceInDays, differenceInMonths, differenceInYears } from 'date-fns';

	let maxDays: number = 31
  let birthYear: number = new Date().getFullYear();
  let birthMonth: number = 1;
  let birthDay: number = 1;
  let years: number = 0;
  let months: number = 0;
  let days: number = 0;

  function calculateAge() {
    const birthDate = new Date(birthYear, birthMonth - 1, birthDay);
    const currentDate = new Date();
    years = differenceInYears(currentDate, birthDate);
    months = differenceInMonths(currentDate, birthDate) % 12;
    days = differenceInDays(currentDate, new Date(birthDate.getFullYear() + years, birthDate.getMonth() + months, birthDate.getDate()));
  }

  $: {
    // Compute the maximum number of days based on the selected year and month
    maxDays = new Date(birthYear, birthMonth, 0).getDate();
  }
</script>

<div class="container">
  <h1>Birthday Calculator</h1>
  <section class="grid">
  <div>
    <label>Year:</label>
    <YearSelect bind:value={birthYear} />
  </div>
  <div>
    <label>Month:</label>
    <MonthSelect bind:value={birthMonth} />
  </div>
  <div>
    <label>Day:</label>
    <DaySelect bind:value={birthDay} maxDays />
  </div>
</section>
  <button on:click={calculateAge}>Calculate Age</button>
  <pre><code>
    {years}, {months}, {days}
  </code></pre>
</div>

<style>
  .container {
    padding: 4.2rem 3.3rem;
    background-color: gray;
    border: 8px solid blue;
    border-radius: 8px;
    border-end-end-radius: 72px;
  }

  div > * {
    margin-bottom: 1rem;
    display: block;
  }
</style>

