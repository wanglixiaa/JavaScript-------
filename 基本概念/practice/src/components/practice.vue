<template>
<div id="myChart" :style="{width: '700px', height: '500px'}"></div>
</template>

<script>
export default {
  name: 'practice',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
    mounted(){
    this.drawLine();
  },
  methods: {
    drawLine(){
// 基于准备好的dom，初始化echarts实例
    let myChart = this.$echarts.init(document.getElementById('myChart'),'light')
// 绘制图表
    //   myChart.setOption({
    //     title: {
    //         text: 'ECharts 入门示例'
    //     },
    //     tooltip: {},
    //     legend: {
    //         data:['销量']
    //     },
    //     xAxis: {
    //         data: ["衬衫","羊毛衫","雪纺衫","裤子","高跟鞋","袜子"]
    //     },
    //     yAxis: {},
    //     series: [{
    //         name: '销量',
    //         type: 'bar',
    //         data: [5, 20, 36, 10, 10, 20]
    //     }]
    // });
      myChart.setOption({
          series:[
              {
                  name:'访问来源',
                  type:'pie',
                  radius:'55%',
                  roseType:'angle',
                  data:[
                      {value:235,name:'视频'},
                      {value:274,name:'联盟'},
                      {value:310,name:'邮件'},
                      {value:335,name:'直接访问'},
                      {value:400,name:'搜索引擎'}
                  ],
                  itemStyle: {
                    // 阴影的大小
                    shadowBlur: 200,
                    // 阴影水平方向上的偏移
                    shadowOffsetX: 0,
                    // 阴影垂直方向上的偏移
                    shadowOffsetY: 0,
                    // 阴影颜色
                    shadowColor: 'rgba(0, 0, 0, 0.5)'
                   }
                }
           ],
             backgroundColor:'#2c343c',
             textStyle: {color: 'red'},

      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
