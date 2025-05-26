<script>
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let conc = [
        ["User-friendly and Useful", "Korpi is considered by the focus groups to be both useful and user-friendly. It works well on both desktop and mobile devices."],
        ["Compared against Korp", "For first-time users, Korpi is more intuitive and easier to use than Korp provides."],
        ];

    let problems = [
        ["Problem 1: Design for User-friendliness", 
            "Adapting the web application for both mobile and desktop devices, as well as presenting large amounts of lexical information without overwhelming the user."],
        ["Problem 2: Functionality for usefulness", 
            "Users might not know what they would like to use these functionalities for, as they are not necessarily applicable to the general public."],
        ];

</script>

<style>
.textcontent {
        margin: 100px;
        max-width: 1200px;
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
    title="Conclusion" 
    subtitle="Main Findings From Korpi" 
    nextSlide="slide11"
    prevSlide="slide9"/>
<div class="textcontent">
    <StaggeredText --fontsize="1.5rem" input_text={problems} />
</div>
<div class="textcontent">
    <StaggeredText --fontsize="2rem" input_text={conc} />
</div>