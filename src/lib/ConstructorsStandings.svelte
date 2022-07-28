<script>
    import { onMount } from 'svelte';
    import Constructor from './Constructor.svelte';
  
    let standings = [];
  
    onMount(async () => {
      const res = await fetch(`https://ergast.com/api/f1/current/constructorStandings.json`);
      const resJson = await res.json();
      console.log(resJson);
      standings = resJson.MRData.StandingsTable.StandingsLists[0].ConstructorStandings;
    });
  </script>
  
  <div>
    <h1>Constructor Standings</h1>
    <div class="grid">
      {#each standings as constructor}
        <Constructor
          position={constructor.position}
          name={constructor.Constructor.name}
          nationality={constructor.Constructor.nationality}
          points={constructor.points}
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
    