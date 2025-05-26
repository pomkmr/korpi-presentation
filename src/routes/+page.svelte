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
        margin-top: 40px;
    }

    .author-container {
        display: grid;
        grid-template-columns: repeat(2, 1fr);

        margin-top: 50px;
    }
    .author-text {
        color: var(--text-secondary-color);
        font-weight: bold;
        font-size: 1.5em;
        margin: 10px;
    }

    .extra-container {
        margin-top: 40px;
        margin-left:10px;
    }

    .supervisor-text {
        font-weight: bold;
        font-size: 1.2rem;
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
        font-size: 1.1rem;
        color: var(--text-secondary-color);
    }

</style>

<div class="title-slide">
    <Title
    nextSlide='slide1'
    --fontsize="2.5rem"
    title="Korpi"
    subtitle="developing a useful and user-friendly frontend for a corpus search engine"/>

    <div class="subtext" in:fade={{duration: 100, delay: 100}}>Bachelor's Thesis Presentation 2025</div>

    <div class="author-container" in:fade={{duration: 1000, delay: 300}}>
        {#each authors as author}
            <div class="author-text">
                {author[0]}
            </div>
        {/each}
    </div>
    <div class="extra-container" in:fade={{duration: 1000, delay: 600}}>
        <div class="supervisor-text">
            <span class="supervisor-label">Supervisor:</span> Peter Ljunglöf
        </div>
    </div>
    <div class="footer" in:fade={{duration: 1000, delay: 800}}>
        <div class="logo">
            <img src={chalmersLogo} alt=""/>
        </div>
    </div>
</div>