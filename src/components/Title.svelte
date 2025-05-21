<script>
    import { goto } from '$app/navigation';
    import { onMount } from 'svelte';
    import { fade } from 'svelte/transition';

    let {title, prevSlide="/", nextSlide="/", subtitle = "", fontsize="24px"} = $props();

    let visible = $state(false);

    onMount(() => {
        setTimeout(() => {
            visible = true;
        })
    }, 2000)

    function onkeydown (e) {
        if (e.key === "ArrowRight") {
            goto(nextSlide)            
        } 

        if(e.key === 'ArrowLeft') {
            goto(prevSlide)
        }
    }

</script>

<style>
    .header-title {
        font-weight: 100;
        font-size: var(--fontsize);
        color: gray;
        margin-top: 50px;
    }

</style>

<svelte:window onkeydown={onkeydown} />

{#if visible}
    <div in:fade={{duration:1000}} class="header-title">
        <h1>{title}</h1>
        <h2>{subtitle}</h2>
    </div>
{/if}