---
title: 成果 
nav:
  order: 1
  tooltip: 多方面综合发展
---

# {% include icon.html icon="fa-solid fa-microscope" %}我们的成果

## 历史成绩
WMJ战队是一个以参加RoboMaster机器人比赛为主，其余竞赛为辅，以培养队员全面综合水平目标的综合型团队。


* 24年联盟赛冠军，分区赛16强
* 25年联盟赛亚军

{% include section.html %}
<!-- echarts -->
## 积分榜排名
<div id="echarts" style="width: 100%; height: 300px;"></div>

<script>

console.log("in");
var chartDom = document.getElementById('echarts');
var myChart = echarts.init(chartDom);
var option;
option = {
     tooltip: {
        trigger: 'axis',  // 设置触发类型为坐标轴触发
        axisPointer: {
            type: 'cross'  // 设置指示器类型为十字准星
            
        },
        formatter: function (params) {
            var info = ["国家级二等奖", "分区赛十六强","分区赛八强，全国赛线上评选，国家级一等奖","分区赛十六强，全国赛四十六强，国家级二等奖","联盟赛冠军，分区赛16强"];
            var dataIndex = params[0].dataIndex; // 获取数据点的索引
            return params[0].axisValue + info[dataIndex]+'<br> 排名：' + params[0].value; // 自定义提示框内容，这里显示额外信息
        }
    },
  xAxis: {
    type: 'category',
    data: ['2020 年', '2021 年', '2022 年', '2023 年', '2024 年']
  },
  yAxis: {
    type: 'value',
    inverse: true,
    min: 0, 
    max: 265,
            axisLabel: {
            formatter: function (value) {
                if (value === 0) {
                    return "冠军"; // 将坐标轴等于 0的标签替换为图片
                } else {
                    return value; // 其他情况保持原始数值
                }
            },
        }
  },
  series: [
    {
      data: [16,11,17,45,60],
      type: 'line'
    }
  ]
};
option && myChart.setOption(option);
</script>

{% include section.html %}


## 高光时刻
<div class="card">
<div class="card-text">
<div class="card-title">RoboMaster 2024</div>

RM赛事第一发随机靶命中
</div>
<div class="card-image">
<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=1904739509&bid=BV1YU411o7b5" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true" mute="true"></iframe>
</div>
</div>

<!-- <div class="card">
<div class="card-text">
<div class="card-title">RoboMaster 2024</div>

十六进八，国赛名额关键争夺战，顽强拼搏，三分钟推爆基地。
</div>
<div class="card-image">
<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=1405028929&bvid=BV1sr421L7yP&cid=1557709783&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true" mute="true"></iframe>
</div>
</div> -->


{% include section.html %}



## 荣誉奖项
{% include search-box.html %}
{% include search-info.html %}
{% assign national_awards_count = 0 %}
{% assign international_awards_count = 0 %}
{% assign provincial_awards_count = 0 %}
{% assign other_awards_count = 0 %}
{% for award in site.awards %}
{% if award.type == "国家级" %}
{% assign national_awards_count = national_awards_count | plus: 1 %}
{% elsif award.type == "国际级" %}
{% assign international_awards_count = international_awards_count | plus: 1 %}
{% elsif award.type == "省级" %}
{% assign provincial_awards_count = provincial_awards_count | plus: 1 %}
{% else %}
{% assign other_awards_count = other_awards_count | plus: 1 %}
{% endif %}
{% endfor %}

{% assign awards_count =  national_awards_count | plus: international_awards_count | plus: provincial_awards_count | plus: other_awards_count %}

根据不完全统计，WMJ战队已经获得了总计 {{awards_count}} 项奖项。
<table>
<tr>
  <td>国家级奖项</td>
  <td>国际级奖项</td>
  <td>省级奖项</td>
  <td>其他奖项</td>
</tr>
<tr>
  <td>{{national_awards_count}}</td>
  <td>{{international_awards_count}}</td>
  <td>{{provincial_awards_count}}</td>
  <td>{{other_awards_count}}</td>
</tr>
</table>



### 国家级
{% include list.html data="awards" component="awards" style="rich" filters="type: 国家级" %} 

### 国际级
{% include list.html data="awards" component="awards" style="simple" filters="type: 国际级" %} 

### 省级
{% include list.html data="awards" component="awards" style="simple" filters="type: 省级"%}

### 其他类型
{% include list.html data="awards" component="awards" style="simple" filters="type: 其他"%}



{% include section.html %}

## 大创项目

{% include search-box.html %}
{% include search-info.html %}

根据不完全统计，WMJ战队已经获得了总计 {{site.projects | size}} 项大创项目。

{% include list.html data="projects" component="projects" style="simple" %}

{% include section.html %}

## 专利
  
{% include search-box.html %}
{% include search-info.html %}

根据不完全统计，WMJ战队已经获得了总计 {{site.patents | size}} 项专利。

{% include list.html data="patents" component="patents" style="simple" %}

{% include section.html %}