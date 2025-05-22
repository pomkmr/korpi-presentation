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
    title="Conclusion" 
    subtitle="Main Findings From Korpi" 
    nextSlide="slide11"
    prevSlide="slide9"/>
<div>
    <StaggeredText --fontsize="1.4rem" input_text={problems} />
</div>