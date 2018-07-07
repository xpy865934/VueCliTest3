<template>
    <div>
        <!-- 为ECharts准备一个具备大小（宽高）的Dom -->
        <div id="main" style="width: 600px;height:400px;"></div>
    </div>    
</template>
<script>
    import echarts from 'echarts/lib/echarts'
    export default {
        data () {
            return {
                text:'某地区降水量',
                cate:['1','2','3','4','5','6','7','8','9','10','11','12'],
                nums:['2.6','5.9','9','26.4','28.7','70.7','175.6','182.2','48.7','18.8','6','2.3']
            }
        },
        mounted() {
            this.draw();
        },
        methods:{
            draw(){
                 // 基于准备好的dom，初始化echarts实例
                var myChart = echarts.init(document.getElementById('main'));

                // 指定图表的配置项和数据
                var option = {
                    title: {
                        text: this.text
                    },
                    tooltip: {},
                    legend: {
                        data:['降水量']
                    },
                    xAxis: {
                        data: this.cate
                    },
                    yAxis: {},
                    series: [{
                        name: '降水量',
                        type: 'bar',
                        data: this.nums
                    }]
                };

                // 使用刚指定的配置项和数据显示图表。
                myChart.setOption(option);
            }
        }
    }

   
</script>
<style>

</style>
