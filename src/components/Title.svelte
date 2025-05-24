<script>
    import { goto } from '$app/navigation';
    import { onMount } from 'svelte';
    import { fade } from 'svelte/transition';

    let {title, prevSlide="/", nextSlide="/", subtitle = ""} = $props();

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
        margin-top: 50px;
        font-size: var(--fontsize);
        
    }
    .header-main-title {
        font-weight: bold;
        color: var(--text-main-color);
        background-color: transparent;
    }

    .header-main-subtitle {
        color: var(--text-secondary-color);
        background-color: transparent;
    }

</style>

<svelte:window onkeydown={onkeydown} />

{#if visible}
    <div in:fade={{duration:1000}} class="header-title">
        <h1 class='header-main-title'>{title}</h1>
        <h2 class='header-main-subtitle'>{subtitle}</h2>
    </div>
{/if}