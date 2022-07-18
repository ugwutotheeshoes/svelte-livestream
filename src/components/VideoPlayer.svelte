<script>
  import { Player, Video } from "@vime/svelte";
</script>

<Player controls >
  <div class="video">
    <Video >
      <source
        data-src="https://res.cloudinary.com/ugwutotheeshoes/video/upload/v1658160734/samples/mac%20miller.mp4"
        type="video/mp4"
      />
    </Video>
  </div>
</Player>
