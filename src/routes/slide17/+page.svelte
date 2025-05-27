<script>
    import Title from "../../components/Title.svelte";
    import StaggeredText from "../../components/StaggeredText.svelte";

    import desktop1 from "$lib/assets/Desktop_Landing_Page_1.png";
    import mobile1 from "$lib/assets/Mobile_Landing_Page_1.png";

    import pic from "$lib/assets/whiteboard.png";
</script>


<style>
.maincontent {
        text-align: center;
        width: 100%;
        height: 650px;
        margin: 10px 0;
        border-radius: 15px;
        overflow-y: scroll;
        /* border: 2px solid gray; */

        display: flex;
    }

    .staggertext-container {
        text-align: center;
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
</style>


<div class="slidecontainer">
    <Title 
        title="Metod" 
        subtitle="Utveckling av Korpis Design!" 
        --fontsize="2rem"
        prevSlide="/slide2" nextSlide="/slide15" />
    <div class="maincontent">
        <img src={pic} width="100%" alt="" in:fade={{duration: 1000}}/>
    </div>
    <div class="staggertext-container">
        <StaggeredText input_text={[["", "Skissa prototyper på whiteboard."]]} 
            --fontsize="2.5rem"></StaggeredText>
    </div>
</div>