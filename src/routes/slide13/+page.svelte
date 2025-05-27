<script>
    import { fade } from "svelte/transition";
    import Title from "../../components/Title.svelte";

    let data = []

    let canvas;
    let ctx;
    let chart;

    $effect(() => {
        ctx = document.getElementById("main-chart");
        if (chart) chart.destroy();
        chart = new Chart(ctx,
            {
                type: 'line',
                data: {
                    labels: ['Användbar', 'Responsiv', 'Snabb(Sökningar)', 'Navigation', 
                            'Design', 'Intressant', 'Tydlig', 'Upplevelse under användning', 
                            'Informationpresentation', 'Statistikpresentation', 'Sökresultatpresentation', 'Korpi i sin helhet'],
                    datasets: [
                        {
                            label: "Yngre #1",
                            data:  [3,4,5,5,5,5,3,4,4,4,4,4],
                        },
                        {
                            label: "Yngre #2",
                            data: [3,3,3,4,3,3,3,3,4,4,4,4],
                        },
                        {
                            label: "Yngre #3",
                            data:  [3,4,3,4,4,4,3,4,4,3,4,4],
                        },
                        {
                            label: "Yngre #4",
                            data: [5,5,5,4,5,5,3,4,5,5,5,5],
                        },
                        {
                            label: "Äldre #1",
                            data:  [3,3,4,4,5,4,3,4,3,3,4,4],
                        },
                        {
                            label: "Äldre #2",
                            data: [1,1,2,2,3,1,2,3,3,4,2,2],
                        },
                        {
                            label: "Äldre #3",
                            data:  [5,4,5,5,4,4,3,4,4,5,4],
                        },
                    ] 
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    elements: {
                        point: {
                            radius: 5, hoverRadius: 10,
                        }
                    },
                    scales: {
                        y: {
                            title: {
                                display: true,
                                text: 'Betyg',
                                font: {size: 20},
                            },
                            ticks: {
                                stepSize: 1,
                                font: {size: 18},
                            },
                            suggestedMax: 5,
                            beginAtZero: true
                        },
                        x: {
                            title: {
                                display: false,
                                text: 'Aspekter',
                                font: {size: 20},
                            },
                            ticks: {
                                stepSize: 1,
                                font: {size: 18},
                                minRotation: 45,
                            },
                        }
                    },
                    plugins: {
                        legend: {
                            display: true,
                            position: 'right',
                            labels: {
                                font: {size: 20},
                            }
                        },
                        tooltip: {
                            titleFont: { size: 20 },
                            bodyFont: {size: 18 },
                        },
                    }
                }
            }
        )
    });

</script>


<style>
    .chartcontainer {
        margin-top: 100px;
        width: inherit;
        height: 600px; 


        border: 2px solid gray;
        border-radius: 15px;
        padding-top: 50px;
        padding-left: 50px;
        padding-right: 50px;
        padding-bottom: 20px;
        transition: box-shadow 0.3s ease;
    }

    .chartcontainer:hover {
        cursor: pointer;
        box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
    }

</style>

<Title 
    title="Resultat" 
    subtitle="Aggregerade resultat från alla deltagare" 
    nextSlide="/slide10"
    prevSlide="/slide5"
    --fontsize="2rem"/>
<div class="chartcontainer" in:fade={{duration:1000}}>
    <canvas bind:this={canvas} id="main-chart" style="width: 100%; height: 100%;"></canvas>
</div>