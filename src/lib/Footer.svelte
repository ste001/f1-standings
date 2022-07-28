<script>
  import svelteLogo from '../assets/svelte.svg'
  import viteLogo from '../assets/vite.svg'
  import githubLogo from '../assets/github-octocat.svg'
</script>

<div class="outerContainer">
  <p class="read-the-docs">
    Powered by:
  </p>
  <div class="footerContainer">
    <a href="https://svelte.dev" target="_blank"> 
      <img src={svelteLogo} class="logo" alt="svelte logo" />
    </a>
    <a href="https://vitejs.dev" target="_blank"> 
      <img src={viteLogo} class="logo" alt="vite logo" />
    </a>
    <a href="https://github.com/" target="_blank"> 
      <img src={githubLogo} class="github-logo" alt="github octocat logo" />
    </a>
  </div>
</div>


<style>
  .outerContainer {
    border-top: 1px solid #eaeaea;
  }
  .footerContainer {
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    align-items: center;
  }
  .read-the-docs {
    color: white;
  }
  .logo {
    height: 3em;
    will-change: filter;
  }
  .github-logo {
    height: 4em;
    will-change: filter;
  }
</style>