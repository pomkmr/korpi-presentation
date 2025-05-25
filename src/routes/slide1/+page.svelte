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
</style> 

<div class="slidecontent">
    <Title nextSlide='slide2' title="Agenda" subtitle="What are we going to talk about?" --fontsize="2rem"/>
    <div class="textcontent">
        <StaggeredText --fontsize="2rem" input_text={agenda_text} />
    </div>
</div>