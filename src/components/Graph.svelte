<script>
 
    let { graphId, olderData, youngerData } = $props();
    let canvas;
    let ctx;
    let chart;

    $effect(() => {
        ctx = document.getElementById(graphId);
        if (chart) chart.destroy();
        chart = new Chart(ctx,
            {
                type: 'bar',
                data: {
                    labels: ['1', '2', '3', '4', '5'],
                    datasets: [
                        {
                            label: "Younger",
                            data: $state.snapshot(youngerData),
                            borderWidth: 1,
                        },
                        {
                            label: "Older",
                            data: $state.snapshot(olderData),
                            borderWidth: 1,
                        },
                    ] 
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    scales: {
                        y: {
                            title: {
                                display: true,
                                text: 'Number of Responses',
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
                                display: true,
                                text: 'Grade',
                                font: {size: 20},
                            },
                            ticks: {
                                stepSize: 1,
                                font: {size: 18},
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
                        }
                    }
                }
            }
        )
    });

</script>

<style>
    .chartcontainer {
        width: 900px;
        height: 600px; 
    }
</style>

<div class="chartcontainer">
    <canvas bind:this={canvas} id={graphId} style="width: 100%; height: 100%;"></canvas>
</div>