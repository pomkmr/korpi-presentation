<script>
    import Title from "../../components/Title.svelte";
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

</style>

<Title 
prevSlide="/slide5" 
nextSlide="/" 
title="Method"
subtitle="Designs Of Korpi"></Title>

<div class="slidecontainer">
    <div class="maincontent">
        IMAGE
    </div>
    <div class="button-group">
        <button class="circle-button">
            1
        </button>
        <button class="circle-button">
            2
        </button>
        <button class="circle-button">
            3
        </button>
    </div>
</div>