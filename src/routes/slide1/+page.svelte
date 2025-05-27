<script>
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let agenda_text = [
        ['Bakgrund', 'Vad är en korpus? Vad är Korp?'],
        ['Metoder och Implementering', 'Design. Fokusgrupper. Tech stack.'],
        ['Resultat', 'Utvärdering. Korpi Demo.'],
        ['Slutsatser', 'Utvärdering. Framtida förbättringar.'],
    ]

</script>

<style>
    .textcontent {
        margin-top: 100px;
    }

    .title-text {
        margin-top: 100px;
    }

    @keyframes move-top {
        0% {
            margin-top: 50%
        }
        100% {
            margin-top: 0px;
        }
    }
</style> 

<div class="slidecontent">
    <div class="title-text">
        <Title nextSlide='slide2' title="Agenda" subtitle="Vad ska vi prata om?" --fontsize="2rem"/>
    </div>
    <div class="textcontent">
        <StaggeredText --fontsize="2rem" input_text={agenda_text} />
    </div>
</div>