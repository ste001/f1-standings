<script>
  import { onMount } from 'svelte';
  import Driver from './Driver.svelte';

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
  <div class="grid">
    {#each standings as driver}
      <Driver
        position={driver.position}
        givenName={driver.Driver.givenName}
        familyName={driver.Driver.familyName}
        nationality={driver.Driver.nationality}
        constructorName={driver.Constructors[0].name}
        points={driver.points}
      />
	  {/each}
  </div>
</div>

<style>
  .grid {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: baseline;
    gap: 10px;
  }
  h1 {
    color: white;
  }
</style>
  