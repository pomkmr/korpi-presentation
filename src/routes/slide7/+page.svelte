<script>
    import Title from "../../components/Title.svelte";

    let showImage = $state(true);
    let showHTMLmock = $state(false);
    let showFigma = $state(false);

</script>

<style>
    .button-group {
        text-align: center;
        margin: 10px;
    }
    
    .circle-button {
        padding: 10px;
        border: 1px solid gray;
        font-size: 15px;
    }

    .circle-button:hover {
        cursor: pointer;
        color: red;
        border: 1px solid black;
        box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
    }

    .maincontent {
        text-align: center;
        width: 100%;
        height: 900px;
        margin: 10px 0;
        border: 1px solid gray;
    }

    .framecontent{
        width: inherit;
        height: 900px;
        resize: both;
        overflow: hidden;
    }


</style>

<Title 
prevSlide="/slide5" 
nextSlide="/slide8" 
title="Method"
subtitle="Designs Of Korpi"></Title>

<div class="slidecontainer">
    <div class="maincontent">
    {#if showImage}
        IMAGE
    {/if}
    {#if showFigma}
        <iframe title="" style="border: 1px solid rgba(0, 0, 0, 0.1);" width="100%" height="100%" 
        src="https://embed.figma.com/design/uL1WK32pyTGThtqRw6VYqH/korp_test?node-id=2-1&embed-host=share" 
        allowfullscreen></iframe>
    {/if}
    {#if showHTMLmock}
    <div class="framecontent">
        <iframe 
        title=""
        style="width: 100%;height:100%;"
        src="https://pomkmr.github.io/korp-mocks/" 
        frameborder="0"></iframe>
    </div>
    {/if}

    </div>
    <div class="button-group">
        <button class="circle-button" onclick={() => {showFigma = false; showHTMLmock = false; showImage = true;}}>
            1
        </button>
        <button class="circle-button" onclick={() => {showFigma = true; showHTMLmock = false; showImage = false;}}>
            2
        </button>
        <button class="circle-button" onclick={() => {showFigma = false; showHTMLmock = true; showImage = false;}}>
            3
        </button>
    </div>
</div>