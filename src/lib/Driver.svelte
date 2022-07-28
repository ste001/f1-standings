<script>
  export let position;
  export let givenName;
  export let familyName;
  export let nationality;
  export let constructorName;
  export let points;

  $: fullName = `${givenName} ${familyName}`;
</script>

<ul class="driverCard">
  <li class="driverItem">{position}</li>
  <li class="driverNameItem">{fullName}</li>
  <li class="driverItem">{nationality}</li>
  <li class="driverItem">{constructorName}</li>
  <li class="driverItem">{points}</li>
</ul>

<style>
  .driverCard {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    padding: 0;
    margin: 0;
    list-style: none;
  }
  .driverItem {
    background: white;
    margin: auto;
    padding: 5px;
    width: 8em;
    height: 1em;
    color: black;
    font-size: 1.5em;
    text-align: center;
  }
  .driverNameItem {
    background: white;
    margin: auto;
    padding: 5px;
    width: 10em;
    height: 1em;
    color: black;
    font-size: 1.5em;
    text-align: center;
  }
</style>
      