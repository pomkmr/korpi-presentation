<script>
    import { fade } from "svelte/transition";
    import Title from "../../components/Title.svelte";

    let w, h = "1000px";
    let screenTextVisible = $state(false);
    let screenText = [
        'Sample1', 
        'Sample2', 
        'Sample3', 
        'Sample4'];

    let blurAmount = $state('0px');

    function onkeydown(e) {
        if (e.key === " ") {
            blurAmount = '5px';
            screenTextVisible = true;
        }

        if (e.key === "Backspace") {
            blurAmount = '0px';
            screenTextVisible = false;
        }
    }

</script>

<style>
    .framecontent{
        width: inherit;
        height: 1000px;
        resize: both;
        overflow: hidden;
        transition: all 0.3s ease;
        filter: blur(var(--blur-amount));
    }

    .problems-text {
        position: absolute;
        background-color: transparent;
        top: 500px;
    }

    .screen-text {
        background-color: transparent;
        color: orange;
        font-weight: bold;
        font-size: 2rem;
        margin: 30px 0;
    }
</style>

<svelte:window onkeydown={onkeydown} />

<Title 
    title="Korp" 
    subtitle="Språkbanken" 
    nextSlide="slide4"/>

<div class="slidecontent">
    <div class="framecontent" style="--blur-amount: {blurAmount}">
        <iframe 
        title=""
        style="width: 100%;height:100%;"
        src="https://spraakbanken.gu.se/korp/" 
        frameborder="0"></iframe>
    </div>
    {#if screenTextVisible}
        <div class="problems-text">
            {#each screenText as text, i}
            <div in:fade|global={{duration: 1000, delay:300*i}} class="screen-text">
                {text}
            </div>
            {/each}
        </div>
    {/if}
</div>