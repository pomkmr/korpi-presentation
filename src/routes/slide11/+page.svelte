<script>
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let imprv = [
        ["Ytterligare backend-funktionalitet", "Möjligheten att lägga till korpusar i backend-systemet. Mer statistik och källinformation i Korpsearch."],
        ["Bugs", "Utökad sökning fungerar ibland inte. Vissa element är inte anpassade för dark mode. Statistik kräver två knapptryckningar för att få grafen. Exempelsökningar är inte kopplade till alla korpusar."],
        ]
</script>

<style>
    .textcontent {
        margin-top: 100px;
        max-width: 1000px;
        border: 2px solid gray;
        border-radius: 15px;
        padding: 90px;
        padding-bottom: 130px;

        transition: box-shadow 0.3s ease;
    }

    .textcontent:hover {
        box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
        cursor: pointer;
    }
    .korpi-container {
        width: 100%;
        height: 500px;
        text-align: center;
        margin: 10px;
    }
</style>

<Title 
    title="Framtida Förbättringar" 
    subtitle="Vad kan vi göra bättre?" 
    nextSlide="slide12"
    prevSlide="slide10"/>
<div class="textcontent">
    <StaggeredText --fontsize="1.5rem" input_text={imprv} />
    <div class="korpi-container">
        <iframe in:fade={{duration: 1000}}
        title=""
        style="width: 90%;height:100%;"
        src="https://korpi.netlify.app" 
        frameborder="0">
    </iframe>
    </div>
</div>