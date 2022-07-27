<script>
  import { onMount } from 'svelte';

  let standings = [];

  onMount(async () => {
    const res = await fetch(`http://ergast.com/api/f1/current/driverStandings.json`);
    const resJson = await res.json();
    console.log(resJson);
    standings = resJson.MRData.StandingsTable.StandingsLists[0].DriverStandings;
  });
</script>

<div>
  <h1>Driver Standings</h1>
  <ol>
    {#each standings as driver}
		  <li>{driver.Driver.givenName} {driver.Driver.familyName}</li>
	  {/each}
  </ol>
</div>
  