<script lang="ts">
import svelteLogo from './assets/svelte.svg'
import viteLogo from '/vite.svg'
import Button from './ui-comps/Button.svelte';
import Dialog from './ui-comps/Dialog.svelte';

let count = 0
let showDialog = false
const open = () => {
  showDialog=true
}
const close = () => {
  showDialog=false
}
</script>

<main>
  <Button on:click={()=>count = count+1}>Count is {count}</Button>
  <Dialog open={showDialog} {close}>111</Dialog>
  <Button on:click={open}>Open Dialog</Button>
  <div>
    <a href="https://vitejs.dev" target="_blank" rel="noreferrer">
      <img src={viteLogo} class="logo" alt="Vite Logo" />
    </a>
    <a href="https://svelte.dev" target="_blank" rel="noreferrer">
      <img src={svelteLogo} class="logo svelte" alt="Svelte Logo" />
    </a>
  </div>
</main>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
</style>
