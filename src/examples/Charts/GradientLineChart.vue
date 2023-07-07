<script setup>
import { onMounted } from "vue";
import Chart from "chart.js/auto";

const props = defineProps({
  id: {
    type: String,
    required: true,
  },
  height: {
    type: String,
    default: "300",
  },
  title: {
    type: String,
    default: "",
  },
  description: {
    type: String,
    default: "",
  },
  chart: {
    type: Object,
    required: true,
    labels: Array,
    datasets: {
      type: Array,
      label: String,
      data: Array,
    },
  },
});

onMounted(() => {
  let ctx = document.getElementById(props.id).getContext("2d");

  let gradientStroke1 = ctx.createLinearGradient(0, 230, 0, 50);

  gradientStroke1.addColorStop(1, "rgba(203,12,159,0.2)");
  gradientStroke1.addColorStop(0.2, "rgba(72,72,176,0.0)");
  gradientStroke1.addColorStop(0, "rgba(203,12,159,0)");

  let chartStatus = Chart.getChart(props.id);
  if (chartStatus != undefined) {
    chartStatus.destroy();
  }

  new Chart(ctx, {
    type: "line",
    data: {
      labels: props.chart.labels,
      datasets: [
        {
          label: props.chart.datasets[0].label,
          tension: 0.4,
          borderWidth: 0,
          pointRadius: 0,
          borderColor: "#cb0c9f",
          // eslint-disable-next-line no-dupe-keys
          borderWidth: 3,
          backgroundColor: gradientStroke1,
          fill: true,
          data: props.chart.datasets[0].data,
          maxBarThickness: 6,
        },
        {
          label: props.chart.datasets[1].label,
          tension: 0.4,
          borderWidth: 0,
          pointRadius: 0,
          borderColor: "#3A416F",
          // eslint-disable-next-line no-dupe-keys
          borderWidth: 3,
          backgroundColor: gradientStroke1,
          fill: true,
          data: props.chart.datasets[1].data,
          maxBarThickness: 6,
        },
      ],
    },
    options: {
      responsive: true,
      maintainAspectRatio: false,
      plugins: {
        legend: {
          display: false,
        },
      },
      interaction: {
        intersect: false,
        mode: "index",
      },
      scales: {
        y: {
          grid: {
            drawBorder: false,
            display: true,
            drawOnChartArea: true,
            drawTicks: false,
            borderDash: [5, 5],
          },
          ticks: {
            display: true,
            padding: 10,
            color: "#b2b9bf",
            font: {
              size: 11,
              family: "Open Sans",
              style: "normal",
              lineHeight: 2,
            },
          },
        },
        x: {
          grid: {
            drawBorder: false,
            display: false,
            drawOnChartArea: false,
            drawTicks: false,
            borderDash: [5, 5],
          },
          ticks: {
            display: true,
            color: "#b2b9bf",
            padding: 20,
            font: {
              size: 11,
              family: "Open Sans",
              style: "normal",
              lineHeight: 2,
            },
          },
        },
      },
    },
  });
});
</script>
<template>
  <div class="p-3 pb-0 card-header">
    <h6>{{ props.title }}</h6>
    <p v-if="props.description" class="text-sm" v-html="props.description" />
  </div>
  <div class="p-3 card-body">
    <div class="chart">
      <canvas
        :id="props.id"
        class="chart-canvas"
        :height="props.height"
      ></canvas>
    </div>
  </div>
</template>
