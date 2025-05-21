<script>
    import { onMount } from "svelte";
    
    let { graphId, data } = $props();

    function createChart() {
        const ctx = document.getElementById(graphId);

        new Chart(ctx,
            {
                type: 'bar',
                data: {
                    labels: ['1', '2', '3', '4', '5'],
                    datasets: [
                        {
                            label: "Younger",
                            data: data[0],
                            borderWidth: 1,
                        },
                        {
                            label: "Older",
                            data: data[1],
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
    }

     onMount(() => {
        createChart();
     });

</script>

<div class="chartcontainer">
    <canvas id={graphId} width="600px" height="300px"></canvas>
</div>