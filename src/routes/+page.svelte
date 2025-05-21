<script>
    import Title from "../components/Title.svelte";
    import StaggeredText from "../components/StaggeredText.svelte";
    import { goto } from "$app/navigation";

    let authors = [
        ['Ludwig Alexandersson',''], 
        ['Erik Dreifeldt', ''],
        ['Pomesh Kumar', ''],
        ['Madeleine Larsson', ''],
        ['Lisa Wadenbrant', ''],
        ['Ida Åberg',''],
    ]

</script>

<style>
    .title-slide {
        margin: 100px;
    }
    .author-text {
        margin-top: 100px;
    }

</style>

<div class="title-slide">
    <Title
    nextSlide='slide1'
    --fontsize="2rem"
    title="Korpi" 
    subtitle="developing a useful and user-friendly frontend for a corpus search engine"/>
    
    <div class="author-text">
        <StaggeredText --fontsize="1.2rem" input_text={authors} />
    </div>
</div>