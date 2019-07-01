# get
## 请求参数

名称|类型|说明
--|:--:|:--:
mode*|number|选择数据的来源，可选值：<br>0：气象站数据<br>1：土壤数据<br>2：水泵数据
soilId|number|若获取土壤数据，选择土壤的编号，编号为从1开始的整数
time|number|读取该时间戳之后的数据，默认为上一次记录数据的时间
item|number|读取数据条数，默认为1
status|number|


请求一条气象站数据示例：
```
{
  "mode":0
  "time":1561729815
}
```

请求编号为2土壤的四条数据示例：
```
{
  "mode":1
  "soilId":2
  "time":1561542332
  "item":4
}
```

请求四条水泵数据实例：
```json
{
  "mode":2
  "time":1561741224
  "item":4
}
```

## 响应字段
mode为0时，响应成功code为200，此时data字段内的属性有

名称|类型|说明
--|:--:|:--:
light|Number|Data of luminosity，范围为1-65535，精度为0.01
humidity|number|Data of humidity，范围为1-100，精度为0.008
temperature|number|Data of temperature，范围为（-）40-85，精度为0.01
rainfall|number|Data of rainfall，范围为0-750，精度为1
CO|number|Data of CO concentration，范围为10-1000，精度为1
NH3|number|Data of NH3 concentration，范围为10-1000，精度为1
airPressure|number|Data of air pressure，范围为300-1100，精度为0.18
batteryLevel|number|Left energy of whether station battery，范围为0-100，精度为1
time|number|得到该数据的时间戳
status|number|

## mode0:响应内容示例：
```
{
  "code": 200,
  "data":{
    "sensor":{
     "light":2233.12,
     "humidity":43.024,
     "temperature":21.43,
     "rainfall":552,
     "CO":435,
     "NH3":236,
     "airPressure":835.36
    },
    "equipment":
      "batteryLevel":5,
      "status":1
  },
}
```

mode为1时，响应成功code为200，此时data字段内的属性有

名称|类型|说明
--|:--:|:--:
humidity|number|Data of soil humidity，范围为0-100，精度为1
temperature|number|Data of soil temperature，范围为（-）55-180，精度为0.6
healthCondition|boolean|False:Healthy<br>True:Sick
switchStatus|boolean|False:Not watering<br>True:Watering
batteryLevel|number|Left energy of field battery，范围为0-100，精度为1
status|number|

## mode1:响应内容示例
```
{
  "code": 200,
  "data":{
    "sensor":{
      "humidity":36,
      "temperature":-88.6,
      "healthCondition":True,
      "switchStatus":False
    },
    "equipment":{
      "status":1,
      "batteryLevel":23
    },
  },
}
```

mode为2时，响应成功code为200，此时data字段内的属性有

名称|类型|说明
--|:--:|:--:
pumpId|number|返回水泵的识别码，编号为从1开始的整数
pumpStatus|boolean|False:不在工作<br>True:正在工作

## mode2:响应内容示例
```
{
  "code": 200,
  "msg":,
  "msg":,
  "pump":[{
    "id":2,
    "status":False
  }],
}
```

# set
## 请求参数

名称|类型|说明
--|:--:|:--:
mode*|number|选择要设置的设备，可选值：<br>0：水泵<br>1：土地开关
id*|number|选择设备的编号，对于水泵和土地开关均为从1开始的整数
status*|boolean|选择设置的模式，False为关闭，True为开启

## 请求内容示例：
```
{
  "mode":1,
  "id":2,
  "status":True
}
```

## 响应字段
响应成功code为200，message为

## 响应内容示例：
```
{
  "code":,
  "msg":
}




