<script>
    import Title from "../../components/Title.svelte";

    import reactLogo from "$lib/assets/ReactLogo.svg";
    import jsLogo from "$lib/assets/JavaScriptLogo.png";
    import bsLogo from "$lib/assets/BootstrapLogo.png";
    import sbLogo from "$lib/assets/SprakbankenLogo.png";

    import { fade } from "svelte/transition";

</script>

<style>

    .maincontent {
        border: 2px solid gray;
        width: 100%;
        height: 600px;
        margin: 10px 0;
        border-radius: 15px;

        transition: box-shadow 0.3s ease;
    }

    .maincontent:hover {
         box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
    }

    .react-text {
        margin:40px 90px;
        display: flex;
        align-items: center;
    }
    
    .text-block {
        margin-left: 30px;
    }

    .logo-main-text {
        font-size: 1.5rem;
        font-weight: bold;
        color: darkslategray;
    }

    .logo-main-desc {
        font-size: 1.3rem;
        margin-top: 5px;
        letter-spacing: 0.5px;
    }

    .highlight-word {
        color: darkred;
        font-weight: bold;
    }
    
    img {
        margin: 0;
    }
</style>


<Title
    prevSlide="/slide7"
    nextSlide="/slide6"
    title = "Method"
    subtitle = "Tech stack used to develop Korpi"
    --fontsize="1rem"
></Title>

<div class="slidecontent">
    <div in:fade={{duration: 1000, delay: 500}} class="maincontent">
        <div class="react-text">
            <img alt="react logo" src={jsLogo} style="height: 100px; width: 100px;"/>
            <div class="text-block">
                <p class="logo-main-text">Javascript</p>
                <p class="logo-main-desc">All coding was done with Javascript.</p>
            </div>
        </div>
        <div class="react-text">
            <img alt="react logo" src={reactLogo} style="height: 100px; width: 100px;"/>
            <div class="text-block">
                <p class="logo-main-text">React</p>
                <p class="logo-main-desc">Main UI Rendering Library. Component-based architecture.</p>
            </div>
        </div>
        <div class="react-text">
            <img alt="react logo" src={bsLogo} style="height: 100px; width: 100px;"/>
            <div class="text-block">
                <p class="logo-main-text">Bootstrap</p>
                <p class="logo-main-desc">Base CSS framework, many components had custom styles.</p>
            </div>
        </div>
        <div class="react-text">
            <img alt="react logo" src={sbLogo} style="height: 100px; width: 100px;"/>
            <div class="text-block">
                <p class="logo-main-text">Språkbanken Korp API + Korpsearch</p>
                <p class="logo-main-desc">The backend was composed of the publically avaliable <span class="highlight-word">Korp API</span> and a custom-made <span class="highlight-word">Korpsearch</span>.</p>
            </div>
        </div>
    </div>
</div>