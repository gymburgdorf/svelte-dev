<script>

</script>

<button on:click>
	<slot></slot>
</button>

<style>
	button {
		padding: 1em;
		background-color: #8888;
		will-change: filter;
    transition: filter 300ms;
	}
 button:hover {
    filter: drop-shadow(0 0 5em #64ffffcc);
  }
</style>