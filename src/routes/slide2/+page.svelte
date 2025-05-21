<script>
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let input_text = [["What is a corpus?", 
        "A collection of written or spoken data."]]
</script>

<style>
    .slidecontent {
        display: flex;
        justify-content: center;
        align-self: center;
    }
</style>

<Title title="" nextSlide="slide3"/>
<div class="slidecontent">
    <StaggeredText {input_text} --fontsize="2rem" />
</div>