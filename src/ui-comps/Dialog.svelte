<script>
    export let open = false
    export let close = ()=>{}
</script>

<h1>{open}</h1>
<dialog {open}>
    <button on:click={close}>
        joijoi
        <slot></slot>
</dialog>