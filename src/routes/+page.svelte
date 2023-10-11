<script lang="ts">
  import YearSelect from '$lib/YearSelect.svelte';
  import NumberDisplay from '$lib/NumberDisplay.svelte'
  import MonthSelect from '$lib/MonthSelect.svelte';
  import DaySelect from '$lib/DaySelect.svelte';
  import { getDaysInMonth, differenceInDays, differenceInMonths, differenceInYears } from 'date-fns';

	let maxDays: number = 31
  let birthYear: number //= new Date().getFullYear()
  let birthMonth: number //= new Date().getMonth() + 1
  let birthDay: number //= new Date().getDay()
  let years
  let months
  let days
  $:maxDays

  function calculateAge() {
    const birthDate = new Date(birthYear, birthMonth - 1, birthDay);
    const currentDate = new Date();
    years = differenceInYears(currentDate, birthDate);
    months = differenceInMonths(currentDate, birthDate) % 12;
    days = differenceInDays(currentDate, new Date(birthDate.getFullYear() + years, birthDate.getMonth() + months, birthDate.getDate()));
  }
$:birthDate = new Date(`${birthYear}-${birthMonth}-${birthDay}`)
    
</script>
{@debug years} 
{@debug months} 
{@debug days}
{@debug birthDate,birthYear}
<div class="container">
  <h1>Birthday Calculator</h1>
  <section class="grid">
    <YearSelect  bind:value={birthYear} />
    <MonthSelect  bind:value={birthMonth} />
    <DaySelect  bind:value={birthDay} maxDays={getDaysInMonth(birthDate)} />  
  <button on:click={calculateAge} >Calculate Age</button>
</section>
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

