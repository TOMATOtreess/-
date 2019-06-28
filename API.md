# get
## 请求参数

名称|类型|说明
--|:--:|:--:
mode*|number|选择数据的来源，可选值：<br>0：气象站数据<br>1：土壤数据
soilId|number|若获取土壤数据，选择土壤的编号，编号为从1开始的整数
timeStart|number|读取该时间戳之后的数据，时间戳精度为时
timeEnd|number|读取该时间戳之前的数据，时间戳精度为时

## 响应字段
mode为0时，响应成功code为200，此时data字段内的属性有
名称|类型|说明
--|:--:|:--:
luminosity|number|
