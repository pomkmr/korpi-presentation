<script>
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    import qrLogo from "$lib/assets/qrcode_korpi.netlify.app.png";
    import { fade } from "svelte/transition";

    let text = [
        ["Peter Ljunglöf", "För din intressanta projekt, att du hjälpt oss med backend-systemet och ökat vår kunskap om språkvetenskap."],
        ["Språkbanken", "För att de tog sig tid att träffa oss och förklara hur Korp samt Korp API fungerar."],
        ["Fokusgruppsdeltagare", "För att ha varit en del av utvärderingen och att ni tog tid från era vardagar för att hjälpa oss utveckla Korpi!"],
    ];
</script>

<style>
    .maincontent {
        display: inline;
    }

    .text-column {
        margin-top: 20px;
    }

    .desc-text {
        font-size: 2rem;
        font-weight: bold;
        color: darkcyan;
        text-align: center;
    }

    .korpi-link {
        font-size: 2rem;
        font-style: italic;
    }
    
    img {
        margin: 0;
    }

    .qr-code-column {
        display: flex;
        align-items: center;
        justify-content: center;
    }

</style>

<Title 
    title="The End" 
    subtitle="Tack till alla som arbetade med projektet!" 
    nextSlide="/slide12"
    prevSlide="/slide11"
    --fontsize="2rem"/>
<div class="maincontent">
    <div class="text-column">
        <StaggeredText --fontsize="2rem" input_text={text} />
    </div>
    <div in:fade={{duration: 1000}} class="qr-code-column">
        <p class="desc-text">Testa Korpi!</p>
        <img src={qrLogo} alt="qrcode"/>
        <a class="korpi-link" href="https://korpi.netlify.app/">korpi.netlify.app</a>
    </div>
</div>