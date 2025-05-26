<script>
    import { fade } from 'svelte/transition';

    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let input_text = [["", "Varje ord i en korpus är annoterad med vissa ord attribut."],];

    let page_text = "Two households, both alike in dignity, In fair Verona, where we lay our scene, From ancient grudge break to new mutiny, Where civil blood makes civil hands unclean. From forth the fatal loins of these two foes. A pair of star-cross'd lovers take their life; Whose misadventured piteous overthrows Do with their death bury their parents' strife.".split(' ');
    
    let selectedWord = $state('');
    let selectedWordDef = $state('');
    let selectedWordClass = $state('');


    let showPage = $state(false);
    function onkeydown (e) {
        if (e.key === "ArrowDown") {
            showPage = true;      
        } 
    }

    function onWordClick(e) {
        console.log('word clicked', e.target.innerText);
        selectedWord = e.target.innerText;

        if (selectedWord === "households,") {
            selectedWord = "households";
            selectedWordDef = "those who dwell under the same roof and compose a family"
            selectedWordClass = "substantiv";
        }

        if (selectedWord === "ancient") {
            selectedWord = "ancient";
            selectedWordDef = "having had an existence of many years"
            selectedWordClass = "substantiv";
        }

        if (selectedWord === "misadventured") {
            selectedWord = "misadventured";
            selectedWordDef = "unfortunate; marked or accompanied by or resulting in misfortune"
            selectedWordClass = "adjektiv";
        }

        if (selectedWord === "shall") {
            selectedWord = "shall";
            selectedWordDef = "used to express what is inevitable or seems likely to happen in the future"
            selectedWordClass = "verb";
        }


    }

</script>

<style>
    .slidecontent {
        display: inline;
    }
    
    .page {
        border: 2px solid gray;
        margin-top: 50px;
        max-width: 800px;
        padding: 100px;
        border-radius: 8px;
        height: 600px;

        display: flex;
        gap: 1ch;
        flex-wrap: wrap;

        transition: box-shadow 0.3s ease;
    }

    .page:hover {
        box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
    }
 
    .word {
        font-size: 1.3rem;
    }

    .word:hover {
        color: blueviolet;
        cursor: pointer;
        text-shadow: 1px 1px 2px gray;
    }

    .card {
        display: block;
        border: 1px solid gray;
        
        width: 800px;
        padding: 20px 100px;
        height: 250px;
        margin-top: 10px;
        margin-bottom: 100px;

        border: 2px solid gray;
        border-radius: 10px;
        transition: box-shadow 0.3s ease;

    }

    .card:hover {
        box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
    }

    .card-page {
        display: block;
    }

    .word-text {
        font-size: 1.2rem;
        color: rgba(12, 11, 11, 0.842);
        margin-top: 5px;
        padding: 10px;
        width: 100%;
    }

    .word-text-entry {
        font-size: 1.4rem;
        font-weight: 500;
    }

    .textcontent {
        width: inherit;
        text-align: center;
        margin-top: 50px;
    }

</style>

<svelte:window onkeydown={onkeydown} />

<Title 
title="Vad är en korpus?" 
subtitle="En samling av stora mängder skrivna eller talade texter." 
--fontsize="1rem"
prevSlide="/slide1" nextSlide="slide14" />

<div class="slidecontent">
    {#if showPage}    
    <div class="textcontent">
            <StaggeredText {input_text} --fontsize="2rem" />
    </div>
    
    <div class="card-page">
        <div in:fade={{duration:1000, delay:500}} class="page">
            {#each page_text as word, i}
            <!-- svelte-ignore a11y_click_events_have_key_events -->
            <!-- svelte-ignore a11y_no_static_element_interactions -->
            <div in:fade|global={{delay:50*i}} class="word" onclick={(e) => onWordClick(e)}>
                {word}
            </div>    
            {/each}
        </div>
        <div in:fade={{duration:1000, delay:1500}} class="card">
            <p class="word-text">Ord: <span class="word-text-entry">{selectedWord}</span></p>
            <p class="word-text">Definition: <span class="word-text-entry">{selectedWordDef}</span></p>
            <p class="word-text">Ordklass: <span class="word-text-entry">{selectedWordClass}</span></p>
        </div>
    </div>
    {/if}
</div>