<script>
    import { fade } from "svelte/transition";
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let input_text =[["", "There were three separate meetings where the particpants could evaluate Korp and Korpi as well as provide feedback."]];

</script>

<style>

    .slidecontent {
        margin: 50px;
        height: 600px;
    }

    .maincontent {
        display: flex;
        justify-content: space-around;
        align-items: center;
        height: inherit;
    }

    .circle {
        width: 400px;
        height: 400px;
        border-radius: 50%;
        color: var(--text-secondary-color);
        font-weight: bold;
        font-size: 2rem;
        border: 2px solid gray;
        display: flex;
        justify-content: space-around;
        align-items: center;
        text-align: center;

        transition: box-shadow 0.3s ease;
    }

    .circle:hover {
        box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
        cursor: pointer;
    }

    .circle-left {
        background-color: #ffadad;
    }

    .circle-right {
        background-color: #dedaf4;
    }

    .staggertext-container {
        text-align: center;
    }

</style>

<Title
    prevSlide="/slide8"
    nextSlide="/slide10"
    title="Method"
    subtitle="Focus Groups Used For Evaluation"
></Title>

<div class="slidecontent">
    <div class="staggertext-container">
        <StaggeredText {input_text} --fontsize="2.3rem"></StaggeredText>
    </div>
    <div class="maincontent">
        <div class="content-column" in:fade={{duration:1000}}>
            <div class="circle circle-right">
                4 Participants <br> Age less than 40
            </div>
        </div>
        <div class="content-column">
            <div class="circle circle-left" in:fade={{duration:1000, delay:100}}>
                3 Participants <br> Age greater than 60
            </div>
        </div>
    </div> 
</div>