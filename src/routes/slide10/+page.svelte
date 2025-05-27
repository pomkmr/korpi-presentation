<script>
    import StaggeredText from "../../components/StaggeredText.svelte";
    import Title from "../../components/Title.svelte";

    let conc = [
        ["Användarvänlig och användbar", "Korpi anses av fokusgrupperna vara både användbart och användarvänligt. Det fungerar bra på både stationära och mobila enheter."],
        ["Jämfört med Korp", "För förstagångsanvändare är Korpi mer intuitivt och enklare att använda än Korp."],
        ];

    let problems = [
            ["Problem 1: Användarvänlig design", 
                "Anpassning av webbapplikationen för både mobila och stationära enheter, samt presentation av stora mängder lexikal information utan att överbelasta användaren."],
            ["Problem 2: Användbar funktionalitet", 
                "Användare kanske inte vet vad de vill använda dessa funktioner till, eftersom de inte nödvändigtvis är tillämpliga för allmänheten."],
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
    title="Slutsats" 
    subtitle="Huvudresultat från Korpi" 
    nextSlide="slide11"
    prevSlide="slide13"
    --fontsize="2rem"/>
<div class="textcontent">
    <StaggeredText --fontsize="1.5rem" input_text={problems} />
</div>
<div class="textcontent">
    <StaggeredText --fontsize="2rem" input_text={conc} />
</div>