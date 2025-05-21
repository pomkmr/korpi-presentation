<script>
    import { onMount } from "svelte";
    
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
                    scales: {
                        y: {
                            ticks: {
                                stepSize: 1,
                            },
                            beginAtZero: true
                        }
                    },
                    plugins: {
                        legend: {
                            display: true,
                            position: 'right',
                        }
                    }
                }
            }
        )
    });

     /* onMount(() => {
        createChart();
     }); */

</script>

<div class="chartcontainer">
    <canvas bind:this={canvas} id={graphId} width="600px" height="300px"></canvas>
</div>