<script>
					import Event from "./Event.svelte";

					let url = "https://api.github.com/events";

					async function getEvents() {
					  const res = await fetch(url);
					  const text = await res.text();

					  if (res.ok) {
					    console.log(JSON.parse(text));

					    return JSON.parse(text);
					  } else {
					    throw new Error(text);
					  }
					}

					let events = getEvents();

					function handleClick() {
					  events = getEvents();
					}
</script>

<style>
  main {
    padding: 20px;
  }
</style>

<main>
<!-- Raised button -->
<button on:click={handleClick} class="mdl-button mdl-js-button mdl-button--raised mdl-button--colored">
  Load Events
</button>
	<div class="mdl-grid">

{#await events}
	<!-- MDL Spinner Component -->
    <div class="mdl-spinner mdl-js-spinner is-active"></div>
    {:then events}
      {#each events as event}
		    <Event name={event.type} date={event.created_at}/>
	    {/each}
    {:catch error}
      <p style="color: red">{error.message}</p>
    {/await}
	</div>
</main>