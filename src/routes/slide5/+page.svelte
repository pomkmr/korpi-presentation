<script>
    import Graph from "../../components/Graph.svelte";
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let counter = $state(0);

    let categories = [
        ["Useful", [0, 0, 0, 0, 0], "Sample Explanation"],
        ["Responsiveness"],
        ["Speed(Searches)"],
        ["Navigation"],
        ["Design"],
        ["Interesting"],
        ["Ease of understanding"],
        ["Experience when using Korpi"],
        ["Presentation of Information"],
        ["Presentation of Statistics"],
        ["Presentation of Results"],
        ["Overall Impression"],
    ]

    function onkeydown (e) {
        if (e.key === "a") {
            counter -= 1;      
        } 

        if(e.key === 'd') {
            counter += 1;      
        }

        console.log(counter);
        
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

</style>

<svelte:window onkeydown={onkeydown} />


<Title title="Results" nextSlide="/slide6" />
<div class="slidecontent">
    <div class="aspectstext">
        <StaggeredText input_text={categories} />
    </div>
    <div class="graphcontainer">
        <Graph graphId="graph1" data={[[counter,2,3,4,5], [5,4,3,2,1]]}/>
        <Graph graphId="graph2" data={[[1,2,3,4,5], [5,4,3,2,1]]}/>
    </div>
</div>