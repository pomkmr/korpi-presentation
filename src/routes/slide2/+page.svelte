<script>
    import { fade } from 'svelte/transition';

    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let input_text = [["", "Here is the prologue of Romeo and Juliet by Shakespeare."],
                      ["", "Every word in a corpus is annotated with certain attributes."],];

    let page_text = "Two households, both alike in dignity, In fair Verona, where we lay our scene, From ancient grudge break to new mutiny, Where civil blood makes civil hands unclean. From forth the fatal loins of these two foes. A pair of star-cross'd lovers take their life; Whose misadventured piteous overthrows Do with their death bury their parents' strife. The fearful passage of their death-mark'd love, And the continuance of their parents' rage, Which, but their children's end, nought could remove, Is now the two hours' traffic of our stage; The which if you with patient ears attend, What here shall miss, our toil shall strive to mend.".split(' ');
    
    let selectedWord = $state('');
    let base_url = "https://api.dictionaryapi.dev/api/v2/entries/en/";

    let dictData = $state('');

    function onWordClick(e) {
        console.log('word clicked', e.target.innerText);
        selectedWord = e.target.innerText;

        console.log('fetching: ', base_url+selectedWord);
        fetch(base_url+selectedWord)
            .then((res) => res.json())
            .then((res) => dictData = res)

        console.log(dictData);
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
        gap: 3px;
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
        height: 200px;
        margin-top: 10px;


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

<Title 
title="What is a corpus?" 
subtitle="A collection of written or spoken texts." 
--fontsize="2rem"
prevSlide="/slide1" nextSlide="slide3" />

<div class="slidecontent">
    <div class="textcontent">
            <StaggeredText {input_text} --fontsize="2.4rem" />
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
            <p class="word-text">Word: <span class="word-text-entry">{selectedWord}</span></p>
            <p class="word-text">Meaning: <span class="word-text-entry">{selectedWord}</span></p>
            <p class="word-text">Word Class: <span class="word-text-entry">{selectedWord}</span></p>
            <div>
                {dictData[0]}
            </div>
        </div>
    </div>
</div>