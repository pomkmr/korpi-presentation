<script>
    import Graph from "../../components/Graph.svelte";
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    import { fade } from "svelte/transition";

    let counter = $state(0);
    let olderData = $state([0, 0, 0, 0, 0]);
    let youngerData = $state([0, 0, 0, 0, 0]);

    let categories = [
        ["Useful", "How useful do you believe Korpi to be?", [0, 0, 3, 0, 1], [1, 0, 1, 0, 1]],
        ["Responsiveness", "How useful do you believe Korpi to be?", [0, 0, 1, 2, 1], [0, 0, 1, 1, 0]],
        ["Speed(Searches)", "How useful do you believe Korpi to be?", [0, 0, 2, 0, 2], [0, 1, 0, 1, 1]],
        ["Navigation", "How useful do you believe Korpi to be?", [0, 0, 0, 3, 1], [0, 1, 0, 1, 1]],
        ["Design", "How useful do you believe Korpi to be?", [0, 0, 1, 1, 2], [0, 0, 1, 1, 1]],
        ["Interesting", "How useful do you believe Korpi to be?", [0, 0, 1, 1, 2], [1, 0, 0, 2, 0]],
        ["Ease of understanding", "How useful do you believe Korpi to be?", [0, 0, 4, 0, 0], [0, 1, 2, 0, 0]],
        ["Experience when using Korpi", "How useful do you believe Korpi to be?", [0, 0, 1, 3, 0], [0, 0, 1, 2, 0]],
        ["Presentation of Information", "How useful do you believe Korpi to be?", [0, 0, 0, 3, 1], [0, 0, 2, 1, 0]],
        ["Presentation of Statistics", "How useful do you believe Korpi to be?", [0, 0, 1, 2, 1], [0, 0, 1, 1, 1]],
        ["Presentation of Results", "How useful do you believe Korpi to be?", [0, 0, 0, 2, 2], [0, 1, 0, 2, 0]],
        ["Overall Impression", "How useful do you believe Korpi to be?", [0, 0, 0, 3, 1], [0, 1, 0, 1, 0]],
    ]

    function onkeydown (e) {
        
    }

    function handleDataChange(entry) {
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
        font-size: var(--fontsize);
        margin-top: 20px;
    }
    .maintext {
        font-weight: bold;
        color: rgb(59, 5, 5);
    }

    .maintext:hover {
        cursor: pointer;
        color: orangered;
        text-shadow: 1px 9px 14px rgba(0,0,0,0.6);
    }

    .subtext {
        font-weight: 400;
        font-size: calc(var(--fontsize) * 0.8);
    }

</style>

<svelte:window onkeydown={onkeydown} />


<Title title="Results" nextSlide="/slide6" />
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
        <!-- <StaggeredText input_text={categories} /> -->
    </div>
    <div class="graphcontainer">
        <Graph graphId="graph1" olderData={olderData} youngerData={youngerData} ></Graph>
    </div>
</div>