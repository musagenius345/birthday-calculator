<script lang="ts">
  import YearSelect from '$lib/YearSelect.svelte';
  import NumberDisplay from '$lib/NumberDisplay.svelte'
  import MonthSelect from '$lib/MonthSelect.svelte';
  import DaySelect from '$lib/DaySelect.svelte';
  import { getDaysInMonth, differenceInDays, differenceInMonths, differenceInYears } from 'date-fns';

	let maxDays: number = 31
  let birthYear: number = new Date().getFullYear()
  let birthMonth: number = new Date().getMonth() + 1
  let birthDay: number = new Date().getDay()
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
$:birthDate = new Date(`${birthYear}-${birthMonth}-${birthDay}`)
    
</script>
{@debug years }
<div class="container">
  <h1>Birthday Calculator</h1>
  <section class="grid">
  <div>
    <label>Year:</label>
    <YearSelect  bind:value={birthYear} />
  </div>
  <div>
    <label>Month:</label>
    <MonthSelect  bind:value={birthMonth} />
  </div>
  <div>
    <label>Day:</label>
    <DaySelect  bind:value={birthDay} maxDays={getDaysInMonth(birthDate)} />
  </div>
</section>
  <button on:click={calculateAge}>Calculate Age</button>
  <main>
    <NumberDisplay value={years} units="years" --font-size="6rem" /> 
    <NumberDisplay value={months} units="months" /> 
    <NumberDisplay value={days} units="days" /> 
</main>
</div>
<style> 
  .container {
    padding: 4.2rem 3rem;
    background-color: gray;
    border: 8px solid blue;
    border-radius: 8px;
    border-end-end-radius: 72px;
    margin: 2.5rem 1.75rem;
  }

  h1{
    font-size: 1.82rem;
  }

  div > * {
    margin-bottom: 1rem;
    display: block;
  }
</style>

