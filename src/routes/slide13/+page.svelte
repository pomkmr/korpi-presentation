<script>
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
                    labels: ['Useful', 'Responsiveness', 'Speed(Searches)', 'Navigation', 
                            'Design', 'Interesting', 'Ease of understanding', 'Experience when using Korpi', 
                            'Presentation of Information', 'Presentation of Statistics', 'Presentation of Results', 'Overall Impression'],
                    datasets: [
                        {
                            label: "Young #1",
                            data:  [3,4,5,5,5,5,3,4,4,4,4,4],
                        },
                        {
                            label: "Young #2",
                            data: [3,3,3,4,3,3,3,3,4,4,4,4],
                        },
                        {
                            label: "Young #3",
                            data:  [3,4,3,4,4,4,3,4,4,3,4,4],
                        },
                        {
                            label: "Young #4",
                            data: [5,5,5,4,5,5,3,4,5,5,5,5],
                        },
                        {
                            label: "Old #1",
                            data:  [3,3,4,4,5,4,3,4,3,3,4,4],
                        },
                        {
                            label: "Old #2",
                            data: [1,1,2,2,3,1,2,3,3,4,2,2],
                        },
                        {
                            label: "Old #3",
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
                                text: 'Grade',
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
                                text: 'Aspects',
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
        margin-top: 50px;
        width: inherit;
        height: 900px; 

        border: 2px solid gray;
        border-radius: 15px;
        padding: 100px;

        transition: box-shadow 0.3s ease;
    }

    .chartcontainer:hover {
        cursor: pointer;
        box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
    }

</style>

<Title 
    title="Results" 
    subtitle="Aggregated results from all participants" 
    nextSlide="/slide14"
    prevSlide="/slide12"/>
<div class="chartcontainer">
    <canvas bind:this={canvas} id="main-chart" style="width: 100%; height: 100%;"></canvas>
</div>