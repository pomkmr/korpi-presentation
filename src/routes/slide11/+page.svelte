<script>
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let imprv = [
        ["Ytterligare backend-funktionalitet", "Möjligheten att lägga till korpusar i backend-systemet. Mer statistik och källinformation i Korpsearch."],
        ["Bugs", "Utökad sökning fungerar ibland inte. Vissa element är inte anpassade för dark mode. Statistik kräver två knapptryckningar för att få grafen. Exempelsökningar är inte kopplade till alla korpusar."],
        ]

    let showPage = $state(false);
    function onkeydown (e) {
        if (e.key === "ArrowDown") {
            showPage = true;      
        } 
    }

</script>

<style>
    .textcontent {
        margin-top: 100px;
        margin-bottom: 100px;
        max-width: 1000px;
        border: 2px solid gray;
        border-radius: 15px;
        padding: 90px;
        padding-bottom: 40px;

        transition: all 0.3s ease;
    }

    .textcontent:hover {
        box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
        cursor: pointer;
    }
    .korpi-container {
        width: 100%;
        height: 600px;
        text-align: center;
    }
</style>

<svelte:window onkeydown={onkeydown} />

<Title 
    title="Framtida Förbättringar" 
    subtitle="Vad kan vi göra bättre?" 
    nextSlide="slide12"
    prevSlide="slide10"
    --fontsize="2rem"/>
<div class="textcontent">
    <StaggeredText --fontsize="2rem" input_text={imprv} />
    {#if showPage}
        
    <div class="korpi-container" in:fade={{duration: 1000}}> 
        <iframe in:fade={{duration: 1000}}
        title=""
        style="width: 90%;height:100%;"
        src="https://korpi.netlify.app" 
        frameborder="0">
    </iframe>
    </div>
    {/if}
</div>