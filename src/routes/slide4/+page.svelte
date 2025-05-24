<script>
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let problems = [
        ["Problem Area 1", "Explanation of the problem 1"],
        ["Problem Area 2", "Explanation of the problem 2"],
        ]
</script>

<style>
    .textcontent {
        margin-top: 100px;
    }
</style>

<Title 
    title="Problem Areas" 
    subtitle="The Problems With Korp" 
    nextSlide="slide5"
    prevSlide="slide3"
    --fontsize="2rem"/>
<div class="textcontent">
    <StaggeredText --fontsize="2.4rem" input_text={problems} />
</div>