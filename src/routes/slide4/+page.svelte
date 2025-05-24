<script>
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let problems = [
        ["Problem 1: Design for User-friendliness", 
            "Adapting the web application for both mobile and desktop devices, as well as presenting large amounts of lexical information without overwhelming the user."],
        ["Problem 2: Functionality for usefulness", 
            "Users might not know what they would like to use these functionalities for, as they are not necessarily applicable to the general public."],
        ]
</script>

<style>
    .textcontent {
        margin-top: 100px;
        max-width: 1200px;
        /* border: 2px solid gray; */
        border-radius: 15px;
        padding: 90px;

        transition: box-shadow 0.3s ease;
    }

    .textcontent:hover {
        box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
    }

</style>

<Title 
    title="Problem Areas" 
    subtitle="The Problems With Korp" 
    nextSlide="slide5"
    prevSlide="slide3"
    --fontsize="2rem"/>
<div class="textcontent">
    <StaggeredText --fontsize="2.5rem" input_text={problems} />
</div>