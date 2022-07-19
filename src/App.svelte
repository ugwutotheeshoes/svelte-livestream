<script>
  import VideoPlayer from "./components/VideoPlayer.svelte";
</script>

<main>
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
    display: table;
    padding: 1em;
    margin: 2rem auto;
  }

  .video {
    width: 700px;
    display: inline-block;
  }

  @media (max-width: 750px) {
    .video {
      width: 400px;
    }
  }
</style>
