<script>
    import Title from "../../components/Title.svelte";
    import StaggeredText from "../../components/StaggeredText.svelte";

    import pic from "$lib/assets/whiteboard.png";
    import { fade } from "svelte/transition";

    import desktop1 from "$lib/assets/Desktop_Landing_Page_1.png";
    import desktop2 from "$lib/assets/Desktop_Result_Page_1.png";

    import mobile1 from "$lib/assets/Mobile_Landing_Page_1.png";
    import mobile2 from "$lib/assets/Mobile_Landing_Page_2.png";
    import mobile3 from "$lib/assets/Mobile_Result_Page_1.png";

    let showState = $state([...Array(5)].map(() => false));
    function setShowState(n) {
        showState = showState.map(() => false); 
        showState[n] = true;
    }
    
</script>

<style>
    .maincontent {
        text-align: center;
        width: 100%;
        height: 600px;
        margin: 10px 0;
        border-radius: 15px;
        overflow-y: scroll;
        border: 2px solid gray;
    }

    .framecontent{
        width: inherit;
        height: 1000px;
    }

    .timeline-container {
        text-align: center;
    }

    .timeline-dot {
        width: 30px;
        height: 30px;
        padding: 5px;
        border: 0px transparent;
        border-radius: 50%;
        font-weight: bold;
        font-size: 1rem;
        color: white;
        display: inline-block;
        text-align: center;
        background-color: var(--text-secondary-color);

        transition: box-shadow 0.3s ease;
    }

    .timeline-dot:hover {
        box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
        background-color: gray;
        cursor: pointer;
    }

    .mobile-view-container {
        margin: 10px;
        display: flex;
        gap: 3px;
    }

    .mobile-view-container img{
        border: 2px solid gray;
        border-radius: 15px;
        height: 570px;

        transition: box-shadow 0.3s ease;
    }

    .mobile-view-container img:hover {
        cursor: pointer;
        box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
    }

    .staggertext-container {
        text-align: center;
        margin: 20px;
    }

</style>

<Title 
prevSlide="/slide9" 
nextSlide="/slide8" 
title="Metod"
subtitle="Utveckling av designs för Korpi"></Title>

<div class="slidecontainer">
    <div class="maincontent">
    {#if showState[0]}
        <img src={pic} width="100%" alt="" in:fade={{duration: 1000}}/>
    {/if}
    

    {#if showState[1]}
        <img src={desktop1} width="100%" alt="" in:fade={{duration: 1000}}/>
    {/if}

    {#if showState[2]}
        <img src={desktop2} width="100%" alt="" in:fade={{duration: 1000}}/>
    {/if}

    {#if showState[3]}
        <div class="mobile-view-container">
            <img src={mobile1} alt="" in:fade={{duration: 1000}}/>
            <img src={mobile2} alt="" in:fade={{duration: 1000}}/>
            <img src={mobile3} alt="" in:fade={{duration: 1000}}/>
        </div>
    {/if}

    <!-- {#if showState[3]}
    <div class="framecontent">
        <iframe 
        title=""
        style=""
        width="100%" height="100%"
        src="https://pomkmr.github.io/korp-mocks/" 
        frameborder="0"></iframe>
    </div>
    {/if} -->

    </div>
    
    <div class="staggertext-container">
        <StaggeredText input_text={[["", "Korpi gick igenom många design iterationer innan den slutliga produkten!"]]} 
            --fontsize="2rem"></StaggeredText>
    </div>

    <div class="timeline-container">
        <button class="timeline-dot" onclick={() => setShowState(0)}>
            1
        </button>
        <button class="timeline-dot" onclick={() => setShowState(1)}>
            2
        </button>
        <button class="timeline-dot" onclick={() => setShowState(2)}>
            3
        </button>
        <button class="timeline-dot" onclick={() => setShowState(3)}>
            4
        </button>
    </div>
</div>