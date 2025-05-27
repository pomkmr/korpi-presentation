<script>
    import { fade } from "svelte/transition";
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let aim = [
        ["Syfte", 
            "Utveckla ett alternativ till Korp, som är enklare att använda för allmänheten på både stora och små skärmar."],]

    let problems = [
            ["Problem 1: Användarvänlig design", 
                "Anpassning av webbapplikationen för både mobila och stationära enheter, samt presentation av stora mängder lexikal information utan att överbelasta användaren."],
            ["Problem 2: Användbar funktionalitet", 
                "Användare kanske inte vet vad de vill använda dessa funktioner till, eftersom de inte nödvändigtvis är tillämpliga för allmänheten."],
        ]

    let showProblems = $state(false);
</script>

<style>
    .textcontent {
        margin-top: 50px;
        max-width: 600px;
        border: 2px solid gray;
        border-radius: 15px;
        padding: 50px;
        padding-bottom: 50px;
        
        transition: box-shadow 0.3s ease;
    }

    .greenborder {
        border: 2px solid green;

        
    }

    .redborder {
        border: 2px solid red;
    }

    .textcontent:hover {
        box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
        cursor:pointer;
    }

</style>

<Title 
    title="Syfte och Problem" 
    subtitle="Vad vill vi göra?" 
    nextSlide="slide9"
    prevSlide="slide3"
    --fontsize="1rem"/>
<!-- svelte-ignore a11y_click_events_have_key_events -->
<!-- svelte-ignore a11y_no_static_element_interactions -->
<div class="textcontent greenborder" onclick={() => showProblems = true}>
    <StaggeredText --fontsize="1.5rem" input_text={aim} />
</div>

{#if showProblems}
<div class="textcontent redborder" in:fade={{duration: 1000}}>
    <StaggeredText --fontsize="1.5rem" input_text={problems} />
</div>
{/if}