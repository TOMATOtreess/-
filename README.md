# Get Weather Station Data
## 请求参数

名称|类型|说明
--|:--:|:--:
time|number|Get data based on time<br>Default:If there is no parameter, return the last recorded data

## 响应字段
属性名|类型|说明
--|:--:|:--:
result|boolean|False:Get data failure<br>True:Get data success
light|Number|Data of luminosity
humidity|number|Data of humidity
temperature|number|Data of temperature
rainfall|number|Data of rainfall
CO|number|Data of CO concentration
NH3|number|Data of NH3 concentration
airPressure|number|Data of air pressure
batteryLevel|number|Left energy of whether station battery

# Get Field Data
## 请求参数

名称|类型|说明
--|:--:|:--:
id*|number|Get data of specific field based on ID
time|number|Get data based on time


## 响应字段
属性名|类型|说明
--|:--:|:--:
result|number|False:Get data failure<br>True:Get data success
humidity|number|Data of soil humidity
temperature|number|Data of soil temperature
healthCondition|boolean|0:Healthy<br>1:Sick
waterSwitch|boolean|False:Not watering<br>True:Watering
batteryLevel|number|Left energy of field battery


# Get Data of Pump
## 请求参数

名称|类型|说明
--|:--:|:--:
id|number|Get specific status of pump based on ID

## 响应字段
属性名|类型|说明
--|:--:|:--:
status|boolean|False:Pump is not working<br>True:Pump is working


# Control of Water
## 请求参数

名称|类型|说明
--|:--:|:--:
mode|string|waterSwitch, pump
id|number|Control specific pump based on ID
status|boolean|False:Close pump<br>True:Open pump

## 响应字段

属性名|类型|说明
--|:--:|:--:
result|boolean|False:Change status failed<br>True:Change status success


