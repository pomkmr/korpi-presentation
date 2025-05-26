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
        margin-top: 10px;
    }
    .maintext {
        font-weight: 600;
        color: var(--text-secondary-color);
    }
    .subtext {
        font-weight: 400;
        font-size: calc(var(--fontsize) * 0.8);
        margin-top: 7px;
        line-height: 1.35;
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