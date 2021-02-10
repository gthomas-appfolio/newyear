<script>
  export let open = false;
</script>
<style>
  .envelope {
    background: #c94548;
    border-radius: 0 0 15px 15px;
    box-shadow: 0 0 1px #c94548 inset, 0 4px 8px rgba(0, 0, 0, 0.25);
    cursor: pointer;
    height: 34.5vmin;
    margin: 50px auto 0;
    position: relative;
    -webkit-transform: rotate(5deg);
    transform: rotate(5deg);
    transition: transform 150ms ease-in-out;
    width: 73.5vmin;
  }
  .envelope:before,
  .envelope:after {
    content: '';
    position: absolute;
    width: 0;
    height: 0;
    border: 0 solid transparent;
    border-width: 17.25vmin 36.75vmin;
  }
  .envelope:before {
    border-bottom-color: #c94548;
    top: -100%;
    left: 0px;
  }
  .envelope:after {
    border-bottom-color: #fa565a;
    border-left-color: #fa565a;
    border-radius: 0 0 15px 15px;
    border-right-color: #ed4c50;
    box-shadow: 0 1px 1px rgba(0, 0, 0, 0.25);
    top: 0;
    transform: rotate(360deg);
  }

  .paper {
    background: #fff;
    border-radius: 5px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.25);
    color: white;
    cursor: pointer;
    height: 30.75vmin;
    left: .75vmin;
    margin: 0 auto;
    padding-top: 1em;
    position: absolute;
    text-align: center;
    top: 3px;
    transition: top 500ms ease-in-out, color 500ms ease-in-out;
    width: 72.125vmin;
    background-image: url(https://upload.wikimedia.org/wikipedia/commons/thumb/7/79/US_%2420_Series_2006_Obverse.jpg/1600px-US_%2420_Series_2006_Obverse.jpg);
    background-size: cover;
  }

  .open.envelope {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }

  .open .paper {
    top: -25.875vmin;
  }
</style>
<div class="envelope" class:open={open} on:click {...$$restProps}>
  <div class="paper" />
</div>


