<script>
    import Title from "../components/Title.svelte";
    import StaggeredText from "../components/StaggeredText.svelte";
    import { goto } from "$app/navigation";
    import { fade } from "svelte/transition";

    import chalmersLogo from "$lib/assets/chalmers_logo_tall.png";

    let authors = [
        ['Ludwig Alexandersson',''],
        ['Erik Dreifeldt', ''],
        ['Pomesh Kumar', ''],
        ['Lisa Wadenbrant', ''],
        ['Ida Åberg',''],
    ]

</script>

<style>
    .title-slide {
        margin-top: 200px;
    }

    .author-container {
        display: grid;
        grid-template-columns: repeat(1, 1fr);

        margin-top: 50px;
    }
    .author-text {
        color: var(--text-secondary-color);
        font-weight: bold;
        font-size: 1.5em;
        margin: 5px 0;
    }

    .extra-container {
        margin-top: 40px;
        margin-left:0px;
    }

    .supervisor-text {
        font-weight: bold;
        font-size: 1.5rem;
    }

    .supervisor-label {
        font-style: italic;
    }

    .logo {
        margin-top: 200px;
        text-align: center;
    }

    img {
        width: 300px;
    }
    .subtext {
        margin-top: 10px;
        font-style: italic;
        font-size: 1.3rem;
        color: var(--text-secondary-color);
    }

</style>

<div class="title-slide">
    <Title
    nextSlide='slide1'
    --fontsize="2.5rem"
    title="Korpi"
    subtitle="utveckling av ett användbart och användarvänligt gränssnitt för en korpussökmotor"/>

    <div class="subtext" in:fade={{duration: 100, delay: 100}}>Kandidatarbete 2025</div>

    <div class="author-container">
        {#each authors as author, i}
            <div class="author-text" in:fade={{duration: 1000, delay: 100*i}}>
                {author[0]}
            </div>
        {/each}
    </div>
    <div class="extra-container" in:fade={{duration: 1000, delay: 600}}>
        <div class="supervisor-text">
            <span class="supervisor-label">Handledare:</span> Peter Ljunglöf
        </div>
    </div>
</div>