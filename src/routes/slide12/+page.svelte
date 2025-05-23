<script>
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    import qrLogo from "$lib/assets/qrcode_korpi.netlify.app.png";
    import { fade } from "svelte/transition";

    let text = [
        ["Peter Ljunglöf", "For helping us with the backend and understanding linguistics."],
        ["Språkbanken", "For taking their time to meet with us and explain Korp API and how Korp works."],
        ["Focus Group Participants", "For being part of the evaluation."],
    ];
</script>

<style>
    .maincontent {
        display: flex;
    }

    .qr-code-column {
        display: inline-block;
    }

    .desc-text {
        font-size: 2rem;
        font-weight: bold;
        color: darkcyan;
        text-align: center;
    }

    .korpi-link {
        font-size: 1.2rem;
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
    subtitle="Thank you to everyone who worked on the project!" 
    nextSlide="/slide13"
    prevSlide="/slide11"/>
<div class="maincontent">
    <div class="text-column">
        <StaggeredText --fontsize="1.4rem" input_text={text} />
    </div>
    <div in:fade={{duration: 1000}} class="qr-code-column">
        <p class="desc-text">Test Korpi Right Now!</p>
        <img src={qrLogo} alt="qrcode"/>
        <a class="korpi-link" href="https://korpi.netlify.app/">korpi.netlify.app</a>
    </div>
</div>