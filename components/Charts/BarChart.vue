<script>
import { Bar } from "vue-chartjs";
// const { reactiveProp } = mixins;

export default {
  extends: Bar,
  data: () => ({
    chartdata: {
      labels: [
        "Oca",
        "Şub",
        "Mar",
        "Nis",
        "May",
        "Haz",
        "Tem",
        "Ağu",
        "Eyl",
        "Eki",
        "Kas",
        "Ara"
      ],
      datasets: [
        {
          label: "Proje Sayısı",
          weight: 5,
          borderWidth: 0,
          borderRadius: 4,
          backgroundColor: "#3a416f",
          data: [40, 20, 12, 39, 60, 55, 85, 115, 42, 24, 45, 4],
          fill: false,
          maxBarThickness: 35
        }
      ]
    },
    // :options
    options: {
      responsive: true,
      maintainAspectRatio: false,

      legend: {
        display: false,
        position: "bottom"
      },

      tooltips: {
        displayColors: false
      },

      scales: {
        xAxes: [
          {
            gridLines: {
              drawBorder: false,
              display: false,
              drawOnChartArea: true,
              drawTicks: true
            },
            ticks: {
              beginAtZero: true
            }
          }
        ],
        yAxes: [
          {
            gridLines: {
              drawBorder: false,
              display: true,
              drawOnChartArea: true,
              drawTicks: false,
              borderDash: [5, 5]
            },
            ticks: {
              display: true,
              color: "#9ca2b7",
              padding: 10
            }
          }
        ]
      }
    }
  }),
  mounted() {
    // this.chartData is created in the mixin.
    // If you want to pass options please create a local options object
    this.renderChart(this.chartdata, this.options);
  }
};
</script>
