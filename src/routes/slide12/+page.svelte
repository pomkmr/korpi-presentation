<script>
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let problems = [
        ["Finding 1", "Explanation 1"],
        ["Finding 2", "Explanation 2"],
        ]
</script>

<style>

</style>

<Title 
    title="The End" 
    subtitle="Main Findings From Korpi" 
    nextSlide="/slide13"
    prevSlide="/slide11"/>
<div>
    <StaggeredText --fontsize="1.4rem" input_text={problems} />
</div>