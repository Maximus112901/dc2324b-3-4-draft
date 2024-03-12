<script>
    import Container from "./Container.svelte";
    export let value = 0;
    export let state = "Default";
    export let locked = false;

    $: if (value % 3 == 0 && value % 5 == 0) {
        state = "FizzBuzz";
    } else if (value % 3 == 0) {
        state = "Fizz";
    } else if (value % 5 == 0) {
        state = "Buzz";
    } else {
        state = "Default";
    }

    function randomIncrement() {
        value += Math.floor(Math.random() * 10);
    }

    function lockColors() {
        locked = !locked;
    }
</script>

<Container>
    <div
        slot="A"
        data-testid="text-input"
        bind:textContent={state}
        contenteditable
    />

    <button slot="B" data-testid="lock-colors" on:click={lockColors}>
        {#if locked}Unlock{:else}Lock{/if} the Wonky Button
    </button>

    <button
        slot="C"
        data-testid="wonkier-button"
        class={locked ? "locked" : state}
        on:click={randomIncrement}
    >
        {#if value % 3 == 0 && value % 5 == 0}
            {state} {value}
        {:else if value % 3 == 0}
            {state} {value}
        {:else if value % 5 == 0}
            {state} {value}
        {:else}
            {value}
        {/if}
    </button>

    {#if state == "FizzBuzz"}
        <p>FizzBuzz!</p>
    {/if}
</Container>

<style>
    [contenteditable] {
        padding: 0.5em;
        border: 1px solid #eee;
        border-radius: 4px;
    }
    button {
        margin: 1em;
        transform: rotate(0deg);
        transition: transform 0.5;
    }

    .Fizz {
        background-color: red;
        color: white;
    }

    .Buzz {
        background-color: green;
        color: white;
    }

    .FizzBuzz {
        background-color: blue;
        color: white;
    }

    .locked {
        opacity: 0.5;
    }
</style>
