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
        ['Peter Ljunglöf', 'Supervisor']
    ]

</script>

<style>
    .title-slide {
        margin-top: 100px;
    }
    .author-text {
        margin-top: 50px;
    }

</style>

<div class="title-slide">
    <Title
    nextSlide='slide1'
    --fontsize="4rem"
    title="Korpi" 
    subtitle="developing a useful and user-friendly frontend for a corpus search engine"/>
    
    <div class="author-text">
        <StaggeredText --fontsize="2rem" input_text={authors} />
    </div>
</div>