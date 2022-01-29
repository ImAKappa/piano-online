<script lang="ts">
  import { Synth } from 'tone';

  import Key from './Key.svelte';

  let synth = new Synth().toDestination();

  let keys = [
    {keyName: "C4"},
    {keyName: "C#4", keyColor: "#000"},
    {keyName: "D4"}
  ];

  const playTone = (e) => {
    let keyName = e.detail;
    console.log(keyName);
    synth.triggerAttackRelease(keyName, "8n");
  } 
</script>

<div>
  {#each keys as {keyName, keyColor}}
  <Key {keyName} {keyColor} on:key-pressed={playTone}/>
  {/each}
</div>