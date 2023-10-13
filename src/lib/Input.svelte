<script>
  export let value;
  export let max;
  export let min;
  export let placeholder;
  export let name;

  let isValid = true;
  let errorMessage = "";

  function handleKeyDown(event) {
    if (event.key === 'ArrowUp' && value < max) {
      value += 1;
    } else if (event.key === 'ArrowDown' && value > min) {
      value -= 1;
    }
  }

  function validateInput() {
    if (isNaN(value) || value < min || value > max) {
      isValid = false;
      errorMessage = `${name} must be between ${min} and ${max}.`;
    } else {
      isValid = true;
      errorMessage = "";
    }
  }

  $: {
    validateInput();
    errorMessage
  }
</script>

<div>
  <label class:warning={isValid} for={name}>{name}</label>
  <input
    autocomplete="false"
    step="1"
    name={name}
    id={name}
    type="number"
    bind:value={value}
    placeholder={placeholder}
    on:input={validateInput}
    on:keydown={handleKeyDown}
    min={min}
    max={max}
    class:invalid={isValid === false}
  />
  {#if isValid}
    <div class="error-message">{errorMessage}</div>
  {/if}
</div>

<style>
  label {
    display: block;
    text-transform: uppercase;
  }

  input {
    font-weight: 700;
    font-size: 1.4rem;
  }
  .warning{
    color: var(--lightred);
  }
  input:focus {
    border: 2px var(--purple) solid;
  }

  .error-message {
    color: var(--lightred);
    font-size: 1rem;
    margin-top: 0.5rem;
  }

  .invalid {
    border: 2px var(--red) solid;
  }
</style>

