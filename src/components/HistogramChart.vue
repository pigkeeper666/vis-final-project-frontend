<template>
  <el-card class="box-card histogram">
    <div id="histogram"></div>
  </el-card>
</template>

<script>
export default {
  data() {
    return {
      msg: "welcome to "
    };
  },
  mounted() {
    this.drawLine();
  },
  methods: {
    drawLine() {
      let mychart = this.$echarts.init(document.getElementById("histogram"));
      mychart.setOption({
        title: {
          text: "某站点用户访问来源",

          left: "center"
        },
        xAxis: {
          type: "category",
          data: ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"]
        },
        yAxis: {
          type: "value"
        },
        series: [
          {
            data: [120, 200, 150, 80, 70, 110, 130],
            type: "bar",
            showBackground: true,
            backgroundStyle: {
              color: "rgba(220, 220, 220, 0.8)"
            }
          }
        ]
      });
    }
  }
};
</script>

<style scoped>
#histogram {
  /* width: 800px; */
  height: 250px;
}
.histogram {
  width: 60%;
}
</style>>

