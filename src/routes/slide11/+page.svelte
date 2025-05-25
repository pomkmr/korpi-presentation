<script>
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let imprv = [
        ["Improvement 1", "Explanation 1"],
        ["Improvement 2", "Explanation 2"],
        ]
</script>

<style>
    .textcontent {
        margin-top: 100px;
        max-width: 1200px;
        border: 2px solid gray;
        border-radius: 15px;
        padding: 90px;
        padding-bottom: 130px;

        transition: box-shadow 0.3s ease;
    }

    .textcontent:hover {
        box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
    }
</style>

<Title 
    title="Future Work" 
    subtitle="Improvements and New Features" 
    nextSlide="slide12"
    prevSlide="slide10"/>
<div class="textcontent">
    <StaggeredText --fontsize="2.5rem" input_text={imprv} />
</div>