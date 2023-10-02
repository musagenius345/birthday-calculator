<script>
	//import 'https://cdn.jsdelivr.net/npm/date-fns@2.30.0/index.min.js'
	import { format, parse } from 'date-fns';
	import '../pico.css'
	const currentDateTime = format(new Date(), 'yyyy-MM-dd HH:mm:ss');
$:currentDateTime
		function parseInput(e) {
    const inputDate = e.target.value; // Get input value
    const parsedDate = parse(inputDate, 'yyyy-MM-dd HH:mm:ss', new Date()); // Parse input using date-fns parse function
    console.log(parsedDate); // Output parsed Date object
}

	
</script>
<svelte:head>
</svelte:head>
<div class="container">
	<h3>Birthday Calculator</h3>
<input type="datetime-local" on:change={parseInput} value={currentDateTime} placeholder="What is your Birthday"/>
    </div>
