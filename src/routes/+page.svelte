<script>
    import Title from "../components/Title.svelte";
    import StaggeredText from "../components/StaggeredText.svelte";
    import { goto } from "$app/navigation";

    let authors = [
        ['Ludwig Alexandersson',''], 
        ['Erik Dreifeldt', ''],
        ['Pomesh Kumar', ''],
        ['Lisa Wadenbrant', ''],
        ['Ida Åberg',''],
        ['Peter Ljunglöf', 'Supervisor']
    ]

</script>

<style>
    .title-slide {
        margin-top: 40px;
    }
    .author-text {
        margin-top: 20px;
    }

</style>

<div class="title-slide">
    <Title
    nextSlide='slide1'
    --fontsize="2.5rem"
    title="Korpi" 
    subtitle="developing a useful and user-friendly frontend for a corpus search engine"/>
    
    <div class="author-text">
        <StaggeredText --fontsize="1.5rem" input_text={authors} />
    </div>
</div>