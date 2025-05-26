<script>
    import Graph from "../../components/Graph.svelte";
    import Title from "../../components/Title.svelte";

    import { fade } from "svelte/transition";

    let currentAspect = $state('Evaluation');
    let counter = $state(0);
    let olderData = $state([0, 0, 0, 0, 0]);
    let youngerData = $state([0, 0, 0, 0, 0]);

    let categories = [
        ["Useful", "", [0, 0, 3, 0, 1], [1, 0, 1, 0, 1]],
        ["Responsiveness", "", [0, 0, 1, 2, 1], [0, 0, 1, 1, 0]],
        ["Speed(Searches)", "", [0, 0, 2, 0, 2], [0, 1, 0, 1, 1]],
        ["Navigation", "", [0, 0, 0, 3, 1], [0, 1, 0, 1, 1]],
        ["Design", "", [0, 0, 1, 1, 2], [0, 0, 1, 1, 1]],
        ["Interesting", "", [0, 0, 1, 1, 2], [1, 0, 0, 2, 0]],
        ["Ease of understanding", "", [0, 0, 4, 0, 0], [0, 1, 2, 0, 0]],
        ["Experience when using Korpi", "", [0, 0, 1, 3, 0], [0, 0, 1, 2, 0]],
        ["Presentation of Information", "", [0, 0, 0, 3, 1], [0, 0, 2, 1, 0]],
        ["Presentation of Statistics", "", [0, 0, 1, 2, 1], [0, 0, 1, 1, 1]],
        ["Presentation of Results", "", [0, 0, 0, 2, 2], [0, 1, 0, 2, 0]],
        ["Overall Impression", "", [0, 0, 0, 3, 1], [0, 1, 0, 1, 0]],
    ]

    function onkeydown (e) {
        
    }

    function handleDataChange(entry) {
        currentAspect = entry[0];
        youngerData = [...entry[2]];
        olderData = [...entry[3]];
    }

</script>

<style>
    .slidecontent {
        display: flex;
        align-items: center;
    }
    .aspectstext {
        margin: 0px;
    }

    .alltext {
        font-size: 1.2rem;
        margin-top: 10px;
    }
    .maintext {
        font-weight: bold;
        color: var(--text-secondary-color)
    }

    .maintext:hover {
        cursor: pointer;
        color: orangered;
    }

    .subtext {
        font-weight: 400;
        font-size: 0.9rem;
    }
    .current-aspect-text {
        text-align: center;
        font-weight: bold;
        font-size: 2rem;
        margin: 10px;
        color: darkslategray;
    }

    .rightside {
        margin: 100px;
        width: 800px;
        border: 2px solid gray;
        border-radius: 15px;
        padding: 10px;

        transition: box-shadow 0.3s ease;
    }
    
    .rightside:hover {
         box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
    }

</style>

<svelte:window onkeydown={onkeydown} />

<Title title="Results" subtitle="What the focus groups thought of Korpi!" nextSlide="/slide13" prevSlide="/slide6"/>
<div class="slidecontent">
    <div class="aspectstext">
    <!-- svelte-ignore a11y_no_static_element_interactions -->
    {#each categories as inp, i}
        <!-- svelte-ignore a11y_click_events_have_key_events -->
        <div onclick={() => handleDataChange(inp)} class="alltext" in:fade|global = {{duration: 1000, delay: 300 * i}}>
            <p class="maintext">{inp[0]}</p>
            <p class="subtext">{inp[1]}</p>
        </div>
    {/each}
    </div>
    <div class="rightside">
        <div class="current-aspect-text">{currentAspect}</div>
        <Graph graphId="graph1" olderData={olderData} youngerData={youngerData} ></Graph>
    </div>
</div>