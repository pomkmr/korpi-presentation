<script>
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let agenda_text = [
        ['Background', 'What is a corpus? What is Korp?'],
        ['Implementation and Methods', 'Focus Groups. Coding the application.'],
        ['Results', 'Evaluation. Final Korpi Demo'],
        ['Discussions', 'Main Findings'],
        ['Conclusions', 'Ethical Aspects. Future Improvements.'],
    ]

</script>

<style>
    .textcontent {
        margin-top: 100px;
    }

    .title-text {
        margin-top: 1px;
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
        <Title nextSlide='slide2' title="Agenda" subtitle="What are we going to talk about?" --fontsize="1.5rem"/>
    </div>
    <div class="textcontent">
        <StaggeredText --fontsize="1.5rem" input_text={agenda_text} />
    </div>
</div>