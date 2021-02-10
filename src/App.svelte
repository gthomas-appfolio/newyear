<script>
  import { onMount } from 'svelte';
  import { Button, Container } from 'sveltestrap';
  import Envelope from './Envelope.svelte';
  let open = false;
  let data;
  
  onMount(async () => {
    const resp = await fetch('https://randomuser.me/api'); // TODO change URL
    const result = await resp.json();
    data = { code: result.results[0].login.md5 }; // code can be whatever your API sends as data
  });
</script>

<style>
  @import "https://stackpath.bootstrapcdn.com/bootswatch/4.3.1/darkly/bootstrap.min.css";
  @import "https://cdnjs.cloudflare.com/ajax/libs/animate.css/3.7.2/animate.min.css";
  @import "https://fonts.googleapis.com/css?family=Mr+Dafoe&amp;display=swap";
  
  :global(body) {
    background: radial-gradient(rgb(170, 53, 58), #8e0000);
    color: rgb(245, 215, 56);
    padding-top: 25vh;
  }
  h2 {
    font-family: 'Mr Dafoe', cursive !important;
    text-align: center;
  }
  h2 {
    font-size: 4em;
  }
</style>

<Container>
  <div class="animated fadeInDown">
    <Envelope
      open={open}
      on:click={() => open = !open}
    />
  </div>
    {#if open} 
      <div class="animated fadeIn p-5 text-center">
        <h2>Happy New Year!</h2>
        {#if data}
          <h3>Here's an Amazon Gift Card:</h3>
          <p>{data.code}</p>
          <Button color="danger" href="https://www.amazon.com/redeem">
            Redeem here
          </Button>
        {/if}
      </div>
    {/if}
  </Container>

