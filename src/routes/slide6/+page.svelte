<script>
    import { fade } from "svelte/transition";
    import Title from "../../components/Title.svelte";


    let korpVisible = $state(false);

    function onkeydown(e) {
         if (e.key === "0") {
            korpVisible = true;
        }
    }
</script>

<style>
    .maincontent {
        margin-top: 50px;
        width: inherit;
        height: 900px;
        resize: both;
        overflow: auto;

        display: flex;
        gap: 5px;
    }
</style>

<svelte:window onkeydown={onkeydown} />

<Title 
prevSlide="/slide5" 
nextSlide="/slide7" 
title="Korpi"
subtitle="Live Demo of Korpi"></Title>

<div class="maincontent">
    <iframe in:fade={{duration: 1000}}
    title=""
    style="width: 100%;height:100%;"
    src="https://korpi.netlify.app" 
    frameborder="0"></iframe>

    {#if korpVisible}    
    <iframe in:fade={{duration: 1000}}
        title=""
        style="width: 100%;height:100%;"
        src="https://spraakbanken.gu.se/korp/" 
        frameborder="0"></iframe>
    {/if}
</div>