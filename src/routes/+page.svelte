<script lang="ts">
  import YearSelect from '$lib/YearSelect.svelte';
  import NumberDisplay from '$lib/NumberDisplay.svelte'
  import MonthSelect from '$lib/MonthSelect.svelte';
  import DaySelect from '$lib/DaySelect.svelte';
  import { getDaysInMonth, differenceInDays, differenceInMonths, differenceInYears } from 'date-fns';
  // let inputEmpty = true
	let maxDays: number = 31
  let birthYear: number //=new Date().getFullYear()
  let birthMonth: number //= new Date().getMonth() + 1
  let birthDay: number //= new Date().getDay()
  let years = '--'
  let months = '--'
  let days = '--'

 let isDisabled: boolean = true;

  $: {
    isDisabled = !(birthYear !== undefined && birthMonth !== undefined && birthDay !== undefined);
  }  $:maxDays

 
  function calculateAge() {
    const birthDate = new Date(birthYear, birthMonth - 1, birthDay);
    const currentDate = new Date();
    years = differenceInYears(currentDate, birthDate);
    months = differenceInMonths(currentDate, birthDate) % 12;
    days = differenceInDays(currentDate, new Date(birthDate.getFullYear() + years, birthDate.getMonth() + months, birthDate.getDate()));
  }
$:birthDate = new Date(`${birthYear}-${birthMonth}-${birthDay}`)
    
</script>
<div class="container">
  <h1>Birthday Calculator</h1>
  <section class="grid">
   <YearSelect  bind:value={birthYear} />
    <MonthSelect  bind:value={birthMonth} />
    <DaySelect  bind:value={birthDay} maxDays={getDaysInMonth(birthDate)} />  
  <button disabled={isDisabled}  on:click={calculateAge} ></button>
</section>
  <section>
    <NumberDisplay value={years} units="years" --font-size="6rem" /> 
    <NumberDisplay value={months} units="months" /> 
    <NumberDisplay value={days} units="days" /> 
</section>
</div>
<style> 
  .container {
    padding: 1.2rem 1rem;
    /* margin-inline: .8rem; */
    color: var(--smoke-grey);
    background-color: var(--white);
    /* border: 4px solid var(--off-white); */
    border-radius: 12px;
    border-end-end-radius: 82px;
  }

  button{
    background-image: url('/assets/images/icon-arrow.svg');
    padding: 1.2rem;
    border: none;
    background-color: var(--purple);
    border-radius: 50%;
    background-position: center;
    width: 3.5rem;
    height: 3.5rem;
  }

  h1{
    color: var(--smoke-grey);
    font-size: 1.82rem;
  }


</style>

