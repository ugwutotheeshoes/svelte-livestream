<script>
  // @ts-nocheck

  import { Player, Video } from "@vime/svelte";
  import Icon from "svelte-icons-pack/Icon.svelte";
  import RedoOutlined from "svelte-icons-pack/ai/AiOutlineRedo";
  let toMute = true;
  let streamEnded;
  let playbackEnded = false;
  let currentTime = 307;
  let playing = true;
  let playerControl = true;

  const restart = () => {
    currentTime = 0;
    playerControl = true;
    playbackEnded = false;
  };

  const videoEnded = () => {
    playerControl = false;
    playbackEnded = true;
    streamEnded = "this stream has ended";
  };
</script>

{#if playing}
  <Player
    controls={playerControl}
    autoplay
    muted={toMute}
    on:vmPlaybackEnded={videoEnded}
    currentTime={currentTime}
  >
    <div class="video">
      <Video>
        <source
          data-src="https://res.cloudinary.com/ugwutotheeshoes/video/upload/v1658160734/samples/mac%20miller.mp4"
          type="video/mp4"
        />
      </Video>
    </div>
  </Player>
  <h3>Live: Mac miller Tiny Desk Concert</h3>
  <p>1,150 views</p>
  <p>streamed live 5 hours ago</p>
  {#if playbackEnded}
    <button on:click={restart}
      >restart live video
      <Icon
        src={RedoOutlined}
        color="white"
        size="10"
        className="custom-icon"
        title="Custom icon params"
      /></button
    >
    <p class="pos">{streamEnded}</p>
  {/if}
{/if}

<style>
  :global(vm-playback-control) {
    --vm-control-scale: 1.7;
  }

  :global(.custom-icon) {
    margin-left: 3px;
    transform: rotate(20deg);
    width: 20px;
    height: 20px;
  }
  h3 {
    color: #000;
    text-transform: uppercase;
    font-size: 1.2rem;
    font-weight: 500;
    line-height: 1.1;
    margin: 0.4rem auto;
    text-align: left;
  }

  p {
    font-size: 0.9rem;
    color: #000;
    text-transform: uppercase;
    font-weight: 500;
    line-height: 1.1;
    margin: 0.4rem auto;
    text-align: left;
  }

  .pos {
    position: absolute;
    top: 32%;
    left: 35%;
    font-size: 2rem;
    letter-spacing: 2px;
    color: #fff;
    font-weight: 400;
  }
  button {
    position: absolute;
    display: flex;
    justify-content: center;
    align-items: center;
    top: 43%;
    left: 41%;
    font-size: 1.2rem;
    padding: 6px;
    letter-spacing: 2px;
    font-weight: 400;
    border: none;
    border-radius: 25px;
    background: transparent;
    cursor: pointer;
    text-transform: uppercase;
    color: white;
  }

  @media (max-width: 750px) {
    :global(vm-playback-control) {
      --vm-control-scale: 1.7;
    }

    :global(.custom-icon) {
      margin-left: 3px;
      transform: rotate(20deg);
      width: 10px;
      height: 10px;
    }
    h3 {
      font-size: 1rem;
      margin: 0.2rem auto;
    }

    p {
      font-size: 0.7rem;
    }
    .pos {
      position: absolute;
      top: 22%;
      left: 36%;
      font-size: 0.8rem;
      letter-spacing: 2px;
      color: #fff;
      font-weight: 400;
    }
    button {
      position: absolute;
      display: flex;
      justify-content: center;
      align-items: center;
      top: 30%;
      left: 40%;
      font-size: 0.4rem;
      padding: 6px;
      letter-spacing: 2px;
      font-weight: 400;
      border: none;
      border-radius: 25px;
      background: transparent;
      cursor: pointer;
      text-transform: uppercase;
      color: white;
    }
  }
</style>
