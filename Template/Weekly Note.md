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
### 本周工作

| 日期  | 内容                                               |
| :-: | :----------------------------------------------- |
| 周一  | ![[<% tp.date.weekday("YYYY-MM-DD",-1) %>#Work]]  |
| 周二  | ![[<% tp.date.weekday("YYYY-MM-DD",0) %>#Work]] |
| 周三  | ![[<% tp.date.weekday("YYYY-MM-DD",-6) %>#Work]] |
| 周四  | ![[<% tp.date.weekday("YYYY-MM-DD",-5) %>#Work]] |
| 周五  | ![[<% tp.date.weekday("YYYY-MM-DD",-4) %>#Work]]  |
| 周六  | ![[<% tp.date.weekday("YYYY-MM-DD",-3) %>#Work]] |
| 周日  | ![[<% tp.date.weekday("YYYY-MM-DD",-2) %>#Work]]  |

### 记录

| 日期  | 内容                                               |
| :-: | :----------------------------------------------- |
| 周一  | [[<% tp.date.weekday("YYYY-MM-DD",-1) %>#Diary]]  |
| 周二  | [[<% tp.date.weekday("YYYY-MM-DD",0) %>#Diary]] |
| 周三  | [[<% tp.date.weekday("YYYY-MM-DD",-6) %>#Diary]] |
| 周四  | [[<% tp.date.weekday("YYYY-MM-DD",-5) %>#Diary]] |
| 周五  | [[<% tp.date.weekday("YYYY-MM-DD",-4) %>#Diary]]  |
| 周六  | [[<% tp.date.weekday("YYYY-MM-DD",-3) %>#Diary]] |
| 周日  | [[<% tp.date.weekday("YYYY-MM-DD",-2) %>#Diary]]  |

---
<< [[<% tp.date.now("YYYY-[W]ww", -1) %>]] | [[<% tp.date.now("YYYY-[W]ww", 1) %>]] >>