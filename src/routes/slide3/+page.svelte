<script>
    import Title from "../../components/Title.svelte";

    let w, h = "900px";
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
    title="Korp" 
    subtitle="Språkbanken" 
    nextSlide="slide4"/>
<div class="maincontent">
    <iframe 
    title=""
    style="width: 100%;height:100%;"
    src="https://spraakbanken.gu.se/korp/" 
    frameborder="0"></iframe>
</div>