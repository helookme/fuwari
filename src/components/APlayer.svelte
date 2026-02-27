<script>
  import { onMount } from 'svelte';
  import APlayer from 'svelte-aplayer/dist/svelte/svelte-aplayer.es.js';
  import 'svelte-aplayer/dist/svelte/style.css';

  export let audio;
  export let theme = '#b7daff';
  export let autoplay = false;
  export let loop = 'all';
  export let order = 'list';
  export let volume = 0.7;
  export let mutex = true;
  export let mini = false;
  export let listFolded = false;
  export let listMaxHeight = null;
  export let baseFontSize = 12;

  let player;
  let playerElement;

  onMount(() => {
    if (playerElement) {
      player = playerElement;
    }
  });

  $: if (player && audio) {
    // 当 audio 属性变化时，更新播放器
    console.log('Audio updated:', audio);
  }
</script>

<div bind:this={playerElement}>
  {#if audio}
    <APlayer
      {audio}
      {theme}
      {autoplay}
      {loop}
      {order}
      {volume}
      {mutex}
      {mini}
      listFolded={listFolded}
      listMaxHeight={listMaxHeight}
      baseFontSize={baseFontSize}
      on:play
      on:pause
      on:ended
      on:error
    />
  {/if}
</div>

<style>
  div {
    width: 100%;
  }
</style>