<script>
import { Pie } from "vue-chartjs";
// const { reactiveProp } = mixins;

export default {
  extends: Pie,

  data: () => ({
    chartdata: {
      labels: [
        "Bilişim",
        "Enerji",
        "Sağlık",
        "Yaşam Bilimleri",
        "Teknik Bilimler"
      ],
      datasets: [
        {
          backgroundColor: [
            "#17c1e8",
            "#cb0c9f",
            "#3a416f",
            "#2152ff",
            "#f53939"
          ],
          data: [40, 20, 12, 39, 60],
          hoverOffset: 4
        }
      ]
    },
    // :options
    options: {
      responsive: true,
      maintainAspectRatio: false,
      legend: {
        display: true,
        position: "bottom"
      },
      tooltips: {
        displayColors: false
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
