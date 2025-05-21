<script>
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let agenda_text = [
        ['Background', 'What is a corpus? What is Korp?'],
        ['Implementation and Methods', 'Focus Groups. Coding the application.'],
        ['Results', 'Evaluation. Final Korpi Demo'],
        ['Discussions', ['Main Findings']],
        ['Conclusions', 'Ethical Aspects. Future Improvements.'],
    ]

</script>

<Title nextSlide='slide2' title="Agenda" --fontsize="1.5rem"/>
<StaggeredText --fontsize="1.5rem" input_text={agenda_text} />