<template>
  <v-chart class="chart" :option="option" />
</template>

<script>
import { use } from "echarts/core";
import { CanvasRenderer } from "echarts/renderers";
import { PieChart } from "echarts/charts";
import {
  TitleComponent,
  TooltipComponent,
  LegendComponent
} from "echarts/components";
import VChart, { THEME_KEY } from "vue-echarts";
import { ref, defineComponent } from "vue";

use([
  CanvasRenderer,
  PieChart,
  TitleComponent,
  TooltipComponent,
  LegendComponent
]);

export default defineComponent({
  name: "MetricsChart",
  components: {
    VChart
  },
  provide: {
    [THEME_KEY]: "light"
  },
  setup: () => {
    const option = ref({
      title: {
        text: "Pagespeed V5",
        left: "center"
      },
      tooltip: {
        trigger: "item",
        formatter: "{b} : {d}%"
      },
      // legend: {
      //   orient: "vertical",
      //   left: "left",
      //   data: [
      //     "First Contentful Paint", 
      //     "Speed Index", 
      //     "Largest Contentful Paint", 
      //     "Time to Interactive", 
      //     "Total Blocking Time",
      //     "Cumulative Layout Shift"
      //   ]
      // },
      series: [
        {
          name: "Pagespeed V5",
          type: "pie",
          radius: "50%",
          center: ["50%", "50%"],
          data: [
            { value: 20, name: "First Contentful Paint" },
            { value: 27, name: "Speed Index" },
            { value: 7, name: "First Meaningful Paint" },
            { value: 33, name: "Time to Interactive" },
            { value: 13, name: "First CPU Idle" },
          ],
          label: {
            formatter: '{b}\n{d}%',
          },
          emphasis: {
            itemStyle: {
              shadowBlur: 10,
              shadowOffsetX: 0,
              shadowColor: "rgba(0, 0, 0, 0.5)"
            }
          }
        }
      ]
    });

    return { option };
  }
});
</script>

<style scoped>
.chart {
  height: 400px;
  width: 500px;
}
</style>
