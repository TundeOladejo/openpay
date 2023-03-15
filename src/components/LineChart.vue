<script>
import { Line } from 'vue-chartjs'
import { Chart as ChartJS, CategoryScale, LinearScale, PointElement, LineElement, Title, Tooltip, Legend } from 'chart.js'

ChartJS.register(CategoryScale, LinearScale, PointElement, LineElement, Title, Tooltip, Legend)

export default {
    name: 'LineChart',
    components: { Line },
    data() {
        return {
            chartData: {
                labels: ['DEC 2', 'DEC 3', 'DEC 4', 'DEC 5', 'DEC 6', 'DEC 7', 'DEC 8'],
                datasets: [
                    {
                        label: '',
                        borderColor: '#0177FB',
                        backgroundColor: '#ffffff',
                        data: [ 900, 1500, 1300, 2500, 2000, 3000, 3400 ]
                    }
                ]
            },
            chartOptions: {
                tension: 0.4,
                responsive: true
            }
        }
    }
}
</script>

<template>
    <Line id="my-chart-id" :options="chartOptions" :data="chartData" />
</template>