<script lang="ts">
  
  import { createEventDispatcher } from 'svelte';

  const dispatch = createEventDispatcher();
  
  const keyPressed = () => {
    dispatch('key-pressed', keyName);
  }

  const keyReleased = () => {
    dispatch('key-released', keyName);
  }
  
  // export let isPressed = false;
  export let keyColor = "white";
  export let keyName = "A4";
</script>

<button class={keyColor} on:click={keyPressed}>{keyName}</button>

<style>
  button {
    /* background-color: #fff; */
    border: 2px solid #000;
    color: #ff0000;
  }

  .white {
    background-color: #fff;
    color: #000;
  }

  .black {
    background-color: #000;
    color: #fff;
  }

  button:active {
    background-color: aqua;
  }
</style>