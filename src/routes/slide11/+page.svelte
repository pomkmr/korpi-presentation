<script>
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let imprv = [
        ["Additional Backend Functionality", "The ability to add corpora to the backend. More statistics and source information in Korpsearch."],
        ["Bugs", "Extended search sometimes does not work. Some elements are not adapted for dark mode. Statistics requires two button presses to get graph. Example searches are not connected to all corpora."],
        ]
</script>

<style>
    .textcontent {
        margin-top: 100px;
        max-width: 1000px;
        border: 2px solid gray;
        border-radius: 15px;
        padding: 90px;
        padding-bottom: 130px;

        transition: box-shadow 0.3s ease;
    }

    .textcontent:hover {
        box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
        cursor: pointer;
    }
</style>

<Title 
    title="Future Work" 
    subtitle="Improvements and New Features" 
    nextSlide="slide12"
    prevSlide="slide10"/>
<div class="textcontent">
    <StaggeredText --fontsize="1.5rem" input_text={imprv} />
</div>