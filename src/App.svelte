<script>

  import DriverStandings from './lib/DriverStandings.svelte';
  import ConstructorsStandings from './lib/ConstructorsStandings.svelte';
  import Footer from './lib/Footer.svelte';

  let constructors = false;
</script>

<main>

  <div class="card">
    <label class="switch">
      <input type="checkbox" bind:checked={constructors}>
      <span class="slider round"></span>
    </label>

    {#if !constructors}
      <DriverStandings />
    {/if}
    {#if constructors}
      <ConstructorsStandings />
    {/if}
  </div>

  <Footer />
</main>

<style>
  /* The switch - the box around the slider */
  .switch {
    position: relative;
    display: inline-block;
    width: 60px;
    height: 34px;
  }

  /* Hide default HTML checkbox */
  .switch input {
    opacity: 0;
    width: 0;
    height: 0;
  }

  /* The slider */
  .slider {
    position: absolute;
    cursor: pointer;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: white;
    -webkit-transition: .4s;
    transition: .4s;
  }

  .slider:before {
    position: absolute;
    content: "";
    height: 26px;
    width: 26px;
    left: 4px;
    bottom: 4px;
    background-color: black;
    -webkit-transition: .4s;
    transition: .4s;
  }

  input:checked + .slider {
    background-color: white;
  }

  input:focus + .slider {
    box-shadow: 0 0 1px white;
  }

  input:checked + .slider:before {
    -webkit-transform: translateX(26px);
    -ms-transform: translateX(26px);
    transform: translateX(26px);
  }

  /* Rounded sliders */
  .slider.round {
    border-radius: 34px;
  }

  .slider.round:before {
    border-radius: 50%;
  }
</style>
