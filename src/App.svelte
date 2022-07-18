<script>
  import logo from "./assets/svelte.png";
  import Counter from "./components/Counter.svelte";
  import VideoPlayer from "./components/VideoPlayer.svelte";
</script>

<main>
  <h1>Live Simulation</h1>
  <div class="video">
    <VideoPlayer />
  </div>
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  }

  main {
    text-align: center;
    padding: 1em;
    margin: 0 auto;
  }

  .video {
    width: 700px;
    height: 550px;
    display: inline-block;
  }

  img {
    height: 16rem;
    width: 16rem;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 3rem;
    font-weight: 300;
    line-height: 1.1;
    margin: 2rem auto;
    /* max-width: 14rem; */
  }

  @media (max-width: 750px) {
    h1 {
      font-size: 2rem;
    }

    .video {
      width: 400px;
      height: 250px;
    }
  }
</style>
