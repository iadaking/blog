```js
var myChart = echarts.init(document.getElementById('main'));
myChart.showLoading();  //加载数据之前
myChart.setOption(option)  //载入除数据之外的基本配置
$.get('data.json').done(function(data){
    myChart.hideLoading();
    myChart.setOption({
        // 传入data
    });
});
```

