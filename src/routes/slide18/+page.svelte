<script>
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let discussion_points = [
            
            ["Fokusgrupper och Evaluering", 
                "Alla vill inte nödvändigtvis vara med i en obetald fokusgrupp. Resultat från dessa kan vara partiska. Svårt att göra statistika analyser med få medlemar."],
            ["Webbutveckling", 
                "Det är ett stort och omfattande område där man behöver kunskap om flera olika aspekter."],
            ["Korpuslingvistik", "Nichad fält. Svårt att definera målgrupper såsom allmänheten. Vad vill allmänheten veta om korpusar?"],
        ]

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
    title="Reflektioner" 
    subtitle="Vad har vi lärt oss från Korpi?" 
    nextSlide="slide11"
    prevSlide="slide10"
    --fontsize="2rem"/>
<div class="textcontent">
    <StaggeredText --fontsize="2rem" input_text={discussion_points} />
</div>