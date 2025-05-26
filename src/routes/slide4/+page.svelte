<script>
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let aim = [
        ["Aim", 
            "Develop an interface for Korp that is user-friendly for the general public."],]

    let problems = [
        ["Problem 1: User-friendly Design", 
            "Adapting the web application for both mobile and desktop devices, as well as presenting large amounts of lexical information without overwhelming the user."],
        ["Problem 2: Useful Functionality", 
            "Users might not know what they would like to use these functionalities for, as they are not necessarily applicable to the general public."],
        ]
</script>

<style>
    .textcontent {
        margin-top: 50px;
        max-width: 600px;
        border: 2px solid gray;
        border-radius: 15px;
        padding: 50px;
        padding-bottom: 50px;
        
        transition: box-shadow 0.3s ease;
    }

    .textcontent:hover {
        box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
        cursor:pointer;
    }

</style>

<Title 
    title="Problem Areas" 
    subtitle="The Problems With Korp" 
    nextSlide="slide9"
    prevSlide="slide3"
    --fontsize="1rem"/>
<div class="textcontent">
    <StaggeredText --fontsize="1.5rem" input_text={aim} />
</div>
<div class="textcontent">
    <StaggeredText --fontsize="1.5rem" input_text={problems} />
</div>