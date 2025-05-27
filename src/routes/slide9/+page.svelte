<script>
    import { fade } from "svelte/transition";
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    import desktop1_res from "$lib/assets/Desktop_Result_Page_1.png";
    import desktop2_res from "$lib/assets/Desktop_Result_Page_2.png";

    import desktop2_landing from "$lib/assets/Desktop_Landing_Page_2.png";
    import desktop3_landing from "$lib/assets/Desktop_Landing_page_3.png";

    import mobile1 from "$lib/assets/Mobile_Landing_Page_1.png";
    import desktop_landing_final from "$lib/assets/Desktop_Landing.png";
    import mobile_final_landing from "$lib/assets/Mobile_Landing.png";

    let input_text =[["", "Det fanns tre separata möten där deltagarna kunde utvärdera Korpi och Korpi samt ge feedback."]];
    
    // Change this text
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
    let show4 = $state(false);
</script>

<style>
    .slidecontent {
        width: 100%;
        height: 600px;
        margin: 10px 0;
        border-radius: 15px;
    }

    .maincontent {
        display: flex;
        justify-content: space-around;
        align-items: center;
        height: inherit;

        border: 2px solid gray;
        border-radius: 15px;
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
        display: flex;
    }
    
    .img-container {
        border: 2px solid gray;
        overflow: hidden;
        margin: 10px;
        border-radius: 15px;

        transition: box-shadow 0.3s ease; 
    }

    .img-container:hover {
        box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
        cursor: pointer;
    }

    .final-container {
        text-align: center;
        width: 100%;
        height: 100%;
        margin: 10px 0;
        border-radius: 15px;
        overflow-y: scroll;
        /* border: 2px solid gray; */

        display: flex;
    }
    .desktop-image-final {
    }
    .mobile-image-final {
        width: 40%;
    }

</style>

<Title
    prevSlide="/slide4"
    nextSlide="/slide7"
    title="Metod"
    subtitle="Fokusgrupper användes för utvärdering"
></Title>

<div class="slidecontent">
    
    <div class="maincontent">
        {#if show1}  
        <div class="content-column" in:fade={{duration:1000}}>
            <div class="circle circle-right">
                4 personer <br> Ålder mindre än 50
            </div>
        </div>
        <div class="content-column">
            <div class="circle circle-left" in:fade={{duration:1000, delay:100}}>
                3 personer <br> Ålder över 60
            </div>
        </div>
        {/if}

        {#if show2}
        <div class="textcontent">
            <div class="desktop-image img-container">
                <img src={desktop1_res} width="100%" alt="" in:fade={{duration: 1000}}/>
            </div>
            <div class="mobile-image img-container">
                <img src={desktop2_res} width="100%" alt="" in:fade={{duration: 1000}}/>
            </div> 
        </div>
        {/if}

        {#if show3}
        <div class="textcontent">
            <div class="desktop-image img-container">
                <img src={desktop2_landing} width="100%" alt="" in:fade={{duration: 1000}}/>
            </div>
            <div class="mobile-image img-container">
                <img src={desktop3_landing} width="100%" alt="" in:fade={{duration: 1000}}/>
            </div> 
        </div>
        {/if}

        {#if show4}
        <div class="textcontent final-container">
            <div class="mobile-image-final img-container">
                <img src={mobile_final_landing} width="100%" alt="" in:fade={{duration: 1000}}/>
            </div> 

            <div class="desktop-image-final img-container">
                <img src={desktop_landing_final} width="100%" alt="" in:fade={{duration: 1000}}/>
            </div>
        </div>
        {/if}


    </div>
    <div class="staggertext-container">
        <StaggeredText {input_text} --fontsize="2rem"></StaggeredText>
    </div> 
    <!-- svelte-ignore a11y_no_static_element_interactions -->
    <div class="timeline-container">
        <!-- svelte-ignore a11y_click_events_have_key_events -->

        <div class="timeline-dot" onclick={() => {show1=true; show2=false; show3=false; show4=false;}}>
            0
        </div>
        <!-- svelte-ignore a11y_click_events_have_key_events -->
        <div class="timeline-dot" onclick={() => {show1=false; show2=true; show3=false; show4=false;}}>
            1
        </div>
        <!-- svelte-ignore a11y_click_events_have_key_events -->
        <div class="timeline-dot" onclick={() => {show1=false; show2=false; show3=true; show4=false;}}>
            2
        </div>
        <!-- svelte-ignore a11y_click_events_have_key_events -->
        <div class="timeline-dot" onclick={() => {show1=false; show2=false; show3=false; show4=true;}}>
            3
        </div>
    </div>
</div>