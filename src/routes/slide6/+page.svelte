<script>
    import Title from "../../components/Title.svelte";

</script>

<style>
    .maincontent {
        width: inherit;
        height: 900px;
        resize: both;
        overflow: auto;
    }
</style>

<Title 
prevSlide="/slide5" 
nextSlide="/slide7" 
title="Korpi"
subtitle="Live Demo of Korpi"></Title>

<div class="maincontent">
    <iframe style="border: 1px solid rgba(0, 0, 0, 0.1);" width="100%" height="100%" src="https://embed.figma.com/design/uL1WK32pyTGThtqRw6VYqH/korp_test?node-id=2-1&embed-host=share" allowfullscreen></iframe>
    <!-- <iframe 
    title=""
    style="width: 100%;height:100%;"
    src="https://korpi3.netlify.app" 
    frameborder="0"></iframe> -->
</div>