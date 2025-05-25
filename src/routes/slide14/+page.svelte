<script>
    import { fade } from 'svelte/transition';

    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    import { onMount } from 'svelte';

    let input_text = [["", "There may be hundreds of texts containing millions of annotated words, grouped into large corpora."]]

    const base_url = "rj.txt";
    let dict1 = $state(''); //RJ
    let dict2 = $state(''); //Hamlet
    let dict3 = $state(''); //JC
 
    onMount(() => {
        
        fetch("rj.txt")
            .then((res) => res.text())
            .then(txt => dict1 = txt.split('\n').filter(s => /\w+/.test(s)));
            // above line uses regex to remove the empty strings from the split

        fetch("dict2.txt")
            .then((res) => res.text())
            .then(txt => dict2 = txt.split('\n').filter(s => /\w+/.test(s)));

        fetch("dict3.txt")
            .then((res) => res.text())
            .then(txt => dict3 = txt.split('\n').filter(s => /\w+/.test(s)));
    });
</script>

<style>
    .card {
        height: 150px;
        width: 200px;
        border: 2px solid gray;
        border-radius: 15px;
        padding: 20px;
        margin: 10px;

        transition: box-shadow 0.3s ease;

    }

    .card:hover {
        box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
        cursor: pointer;
    }

    .cards-container {
        margin: 20px;
        padding: 10px;
        width: fit-content;
        display: grid;
        grid-template-columns: repeat(8, 1fr);
        border-radius: 15px;
        border: 2px solid gray;

        transition: box-shadow 0.3s ease;
    }

    .cards-container:hover {
        box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
        border: 2px solid gray;
    }

    .textcontent {
        text-align: center;
    }

    .play-title {
        margin-top: 50px;
        margin-bottom: 30px;
        font-size: 1.8rem;
        font-weight: 600;
        color: var(--text-secondary-color);
        text-align: center;
        text-transform: uppercase;
    }

</style>

{#snippet card(in_text)}
    <div class="card">
        {in_text}
    </div>
{/snippet}


<div class="slidecontent">
    <Title 
        title="What is a corpus?" 
        subtitle="A collection of written or spoken texts." 
        --fontsize="2rem"
        prevSlide="/slide13" nextSlide="/" />
    
    <div class="maincontent" in:fade|global={{duration: 1000}}>
        <div class="textcontent">
            <StaggeredText {input_text} --fontsize="2.4rem" />
        </div>

        <div class="cards-container">
        <p class="play-title">Romeo & Juliet</p>
        {#each dict1 as c, i}
            <div in:fade={{duration:500, delay:100*i}} >
                {@render card(c)}
            </div>
        {/each}
        </div>

        <div class="cards-container">
        <p class="play-title">Hamlet</p>
        {#each dict2 as c, i}
            <div in:fade={{duration:500, delay:100*i}} >
                {@render card(c)}
            </div>
        {/each}
        </div>

        <div class="cards-container">
             <p class="play-title" >Julius Caesar</p>
        {#each dict3 as c, i}
            <div in:fade={{duration:500, delay:100*i}} >
                {@render card(c)}
            </div>
        {/each}
        </div>
    </div>
</div>