<%* 
let weatherUrl = 'https://restapi.amap.com/v3/weather/weatherInfo'
let key = '70d36e100bf55af4ba7ad6919f501fb0'

let tencentIpUrl = 'https://apis.map.qq.com/ws/location/v1/ip';
let tencentKey = 'DGQBZ-DTK37-2PUXB-PYUIZ-3T2RS-KRBSC'

let ipResult = eval("(" + await request({url: tencentIpUrl + `?key=${tencentKey}`, method: "GET"}) + ")").result
console.log("ipResult: ", ipResult)

let adcode = ipResult.ad_info.adcode
console.log("adcode: " + adcode)

let 位置 = ''
let 天气 = ''
let 温度 = ''
let 风向 = ''
await fetch(weatherUrl + `?key=${key}&city=${adcode}&extensions=all`)
.then(res => res.json())
.then((data) => {
	let info = data.forecasts[0]
	
	console.log("info:" + info)
	
	位置 = info.province + '-' + info.city
	天气 = '🌅' + info.casts[0].dayweather + ' / 🌃' + info.casts[0].nightweather
	温度 = '🌅' + info.casts[0].daytemp_float + '℃' + '/ 🌃' + info.casts[0].nighttemp_float + '℃'
})
-%>
---
🌻日期🌻: <% tp.file.creation_date("YYYY MM DD HH:mm:ss") %>
🌙星期🌙: <% tp.file.creation_date("dddd") %>
⌚️时间⌚️: <% tp.file.creation_date("HH:mm:ss") %>
🌍位置🌍: <% 位置 %>
☁️天气☁️: <% 天气 %>
🌡️温度🌡️: <% 温度 %>
---
<%*
let 一言 = ""
let 来源 = ""
let 作者 = ""

await fetch('https://v1.hitokoto.cn/?c=d&c=h&c=i&c=j')
.then(response => response.json())
.then(data => { 
	一言 = data.hitokoto
	来源 = data.from
	作者 = data.from_who === null ? '佚名' : data.from_who
})
-%>
>[!quote] 一言
 <% 一言 %>  —— 《<% 来源 %>》 · <% 作者 %>

---
# Day planner
-  08:00 - 08:30 起床
- [ ]  09:00 - 11:00 工位
-  11:00 - 11:30 午饭
-  11:30 - 13:00 午休
- [ ]  13:00 - 16:00 工位
-  16:50 - 18:30 锻炼及晚饭
- [ ]  18:30 - 22:00 工位
-  23:30 - 23:59 上床睡觉
# Work

# To do list

# Diary





---
<< [[<% tp.date.now("YYYY-MM-DD", -1) %>]] | [[<% tp.date.now("YYYY-MM-DD", 1) %>]] >>