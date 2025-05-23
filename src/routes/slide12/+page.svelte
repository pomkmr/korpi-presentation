<script>
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let text = [
        ["Peter Ljunglöf", "For helping us with the backend and understanding linguistics."],
        ["Språkbanken", "For taking their time to meet with us and explain Korp API and how Korp works."],
        ["Focus Group Participants", "For being part of the evaluation."],
    ];
</script>

<style>

</style>

<Title 
    title="The End" 
    subtitle="Thank you to everyone who worked on the project!" 
    nextSlide="/slide13"
    prevSlide="/slide11"/>
<div>
    <StaggeredText --fontsize="1.4rem" input_text={text} />
</div>