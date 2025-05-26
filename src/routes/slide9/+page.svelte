<script>
    import { fade } from "svelte/transition";
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let input_text =[["", "There were three separate meetings where the particpants could evaluate Korp and Korpi as well as provide feedback."]];
    
    let aim = [
        ["Aim", 
            "Develop an interface for Korp that is user-friendly for the general public."],]

    let problems = [
            ["Problem 1: User-friendly Design", 
                "Adapting the web application for both mobile and desktop devices, as well as presenting large amounts of lexical information without overwhelming the user."],
            ["Problem 2: Useful Functionality", 
                "Users might not know what they would like to use these functionalities for, as they are not necessarily applicable to the general public."],
        ];

    let show1 = $state(true);
    let show2 = $state(false);
    let show3 = $state(false);
</script>

<style>

    .slidecontent {
        margin: 20px;
        height: 600px;
    }

    .maincontent {
        display: flex;
        justify-content: space-around;
        align-items: center;
        height: inherit;

        border: 2px solid gray;
        border-radius: 15px;
        margin: 10px;
    }

    .circle {
        width: 300px;
        height: 300px;
        border-radius: 50%;
        color: var(--text-secondary-color);
        font-weight: bold;
        font-size: 1.5rem;
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
        margin: 40px 0;
        text-align: center;
    }

    .timeline-container {
        text-align: center;
    }

    .timeline-dot {
        width: 30px;
        height: 30px;
        padding: 5px;
        border-radius: 50%;
        font-weight: bold;
        color: white;
        display: inline-block;
        text-align: center;
        background-color: var(--text-secondary-color);

        transition: box-shadow 0.3s ease;
    }

    .timeline-dot:hover {
        box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
        background-color: gray;
        cursor: pointer;
    }

    .textcontent {
        width: 600px;
    }

</style>

<Title
    prevSlide="/slide4"
    nextSlide="/slide7"
    title="Method"
    subtitle="Focus Groups Used For Evaluation"
></Title>

<div class="slidecontent">
    
    <div class="maincontent">
        {#if show1}
            
        <div class="content-column" in:fade={{duration:1000}}>
            <div class="circle circle-right">
                4 Participants <br> Age less than 50
            </div>
        </div>
        <div class="content-column">
            <div class="circle circle-left" in:fade={{duration:1000, delay:100}}>
                3 Participants <br> Age greater than 60
            </div>
        </div>
        {/if}

        {#if show2}
        <div class="textcontent">
            <StaggeredText --fontsize="1.5rem" input_text={problems} />
        </div>
        {/if}

        {#if show3}
        <div class="textcontent">
            <StaggeredText --fontsize="1.5rem" input_text={problems} />
        </div>
        {/if}

    </div>
    <div class="staggertext-container">
        <StaggeredText {input_text} --fontsize="2rem"></StaggeredText>
    </div> 
    <!-- svelte-ignore a11y_no_static_element_interactions -->
    <div class="timeline-container">
        <!-- svelte-ignore a11y_click_events_have_key_events -->
        <div class="timeline-dot" onclick={() => {show1=true; show2=false; show3=false;}}>
            1
        </div>
        <!-- svelte-ignore a11y_click_events_have_key_events -->
        <div class="timeline-dot" onclick={() => {show1=false; show2=true; show3=false;}}>
            2
        </div>
        <!-- svelte-ignore a11y_click_events_have_key_events -->
        <div class="timeline-dot" onclick={() => {show1=false; show2=false; show3=true;}}>
            3
        </div>
    </div>
</div>