<script>
import Button from "./Button.svelte";

export let open = false
export let close = ()=>{}

let dialog

$: if(dialog) {
    open 
        ? dialog.showModal()
        : dialog.close()
}

$: if(dialog) {
    dialog.addEventListener("click", e => {
        const {clientX: x, clientY: y} = e
        const {left, right, top, bottom} = dialog.getBoundingClientRect()
        if (x < left || x > right || y < top || y > bottom) {
            close()
        }
    })
}
</script>
<dialog bind:this={dialog}>
    <header>
        <button on:click={close}>X</button>
    </header>
    <main>
        <slot></slot>
    </main>
</dialog>

<style>
    header {
        text-align: right;
        background-color: #ccc3;
    }
    header>button {
        background-color: #88d;
        margin: 0;
        border-radius: 0;
    }
    dialog {
        padding: 0;
        min-width: 50vw;
        border: 2px solid whitesmoke;
        filter: drop-shadow(0 0 10em #64ffffff);
    }
    main {
        padding: 1em;
    }

    dialog::backdrop {
        background-color: #222c;
    }
</style>
