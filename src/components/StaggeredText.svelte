<script>
    import { onMount } from "svelte";
    import { fade } from "svelte/transition";

    let visible = $state(false);
    let { input_text, fontsize=16 } = $props();

    onMount(() => {
        setTimeout(() => {
            visible = true;
        })
    }, 2000)

</script>

<style>
    .alltext {
        font-size: var(--fontsize);
        margin-top: 20px;
    }
    .maintext {
        font-weight: bold;
        color: rgb(59, 5, 5);
    }
    .subtext {
        font-weight: 400;
        font-size: calc(var(--fontsize) * 0.8);
    }
    
</style>

{#if visible}
    {#each input_text as inp, i}
        <div class="alltext" in:fade|global = {{duration: 1000, delay: 300 * i}}>
            <p class="maintext">{inp[0]}</p>
            <p class="subtext">{inp[1]}</p>
        </div>
    {/each}
{/if}