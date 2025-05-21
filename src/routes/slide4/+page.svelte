<script>
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let problems = [
        ["Problem 1", "Explanation of the problem 1"],
        ["Problem 2", "Explanation of the problem 2"],
        ]
</script>

<style>

</style>

<Title 
    title="Problem Areas" 
    subtitle="The Problems With Korp" 
    nextSlide="slide5"/>
<div>
    <StaggeredText --fontsize="1.4rem" input_text={problems} />
</div>