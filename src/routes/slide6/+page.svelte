<script>
    import { fade } from "svelte/transition";
    import Title from "../../components/Title.svelte";


    let korpVisible = $state(false);

    function onkeydown(e) {
         if (e.key === "0") {
            korpVisible = !korpVisible;
        }
    }
</script>

<style>
    .maincontent {
        margin-top: 10px;
        width: 100vw;
        height: 1000px;
        resize: horizontal;
        overflow: auto;

        display: flex;
        gap: 5px;
    }
</style>

<svelte:window onkeydown={onkeydown} />

<Title 
prevSlide="/slide8" 
nextSlide="/slide17" 
title="Korpi"
subtitle=""
--fontsize="1rem"></Title>

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