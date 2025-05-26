<script>
    import { fade } from "svelte/transition";
    import Title from "../../components/Title.svelte";

    let w, h = "1000px";
    let screenTextVisible = $state(false);
    let screenText = [
        'Riktad mot lingvister och yrkesverksamma.',
        'Många funktioner som kan vara överväldigande för allmänheten.',
        'Inte anpassad till mindre skärmar och mobila enheter.',
        'Långsam sökning i ett stort antal korpusar.'];

    let blurAmount = $state('0px');

    function onkeydown(e) {
        if (e.key === " ") {
            blurAmount = screenTextVisible ? '0px' : '10px';
            screenTextVisible = !screenTextVisible;
        }
    }

</script>

<style>
    .framecontent{
        width: 100vw;
        height: 100vh;
        resize: horizontal;
        overflow: hidden;
        transition: filter 0.3s ease;
        filter: blur(var(--blur-amount));

        margin-top: 10px;
    }

    .problems-text {
        position: absolute;
        background-color: transparent;
        top: 240px;
    }

    .screen-text {
        background-color: transparent;
        color: var(--text-secondary-color);
        font-weight: bold;
        font-size: 2.0rem;
        margin: 40px 0;
    }
</style>

<svelte:window onkeydown={onkeydown} />

<Title 
    title="Korp" 
    subtitle="Språkbanken erbjuder en sökmotor för hundratals korpora." 
    nextSlide="slide4"
    prevSlide="slide14"
    --fontsize="1rem"/>

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