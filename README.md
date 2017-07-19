<img src='http://d-miller.github.io/images/D3.png'>
D3Network 한국서부발전_신재생에너지+사업현황 시각화
========

>D3Network 라이브러리를 이용한 공공 데이터 시각화
 
Demo
===
<img src=".\img\캡처.PNG" />

Motivation
===
> 지금 이 포트폴리오를 쓰고 있는 오늘, 경주
온도가 39도를 찍고, 미세 먼지가 사회의 심각한 문제가 되고 있다.  
 공공 데이터 포털에서 친환경 발전 현황을 나타내는 데이터를 좀 더 효과적으로 표현하기 위해서 D3.js의 Radial Tidy Tree 형식을 이용해봤다.
=======
D3Network 라이브러리를 이용해서 공공 데이터를 시각화

Main Technology Stack
===
* Python3
* R

Data Example
===
```
{"name":"flare","children":[{"name": "건설", "children": [{"name": "학교 태양광", "children": [{"name": "전국 학교"}]}, {"name": "서남해 해상풍력", "children": [{"name": "전북 부안 위도 ~ 전남 영광 안마도 해상"}]}, {"name": "발전본부 부지내 태양광 1단계", "children": [{"name": "충남 태안군 태안읍 원북면"}]}, {"name": "발전본부 부지내 태양광 2단계", "children": [{"name": "충남 태안군 태안읍 원북면"}]}]}, {"name": "운영", "children": [{"name": "영암 F1 경기장", "children": [{"name": "전남 영암군 삼호읍 삼포리 "}]}, {"name": "경기 안산배수지", "children": [{"name": "경기도 안산시 단원구"}]}, {"name": "태안 IGCC", "children": [{"name": "충남 태안군 태안읍 원북면"}]}, {"name": "세종시 2차 1단계 KDI  ", "children": [{"name": "세종특별자치시 남세종로 263"}]},
```

---

<img src=".\img\공공데이터.PNG" />

Hierarchy Example
===

<img src=".\img\diagram.PNG" />

* 계층적 구조를 표현 예

R Script
===
```R
library(d3network)
library(RCurl)
URL <- "https://gist.github.com/tjdgns8047/a9da753691fd22e9858592fb67d08145"
Flare <- getURL(URL)
Flare <- rjson::fromJSON(Flare)
d3Tree(List = Flare, fontsize = 8, diameter = 1200, zoom=TRUE, file="result.html")
shell.exec(text.thml)
```

Python Code
===
> 공공데이터 포털의 기존 **csv**형식 데이터를 **d3.js**에서 필요한 계층형 **json**형식으로 파싱하기 위해서 파이썬 코드를 이용함
[https://gist.github.com/tjdgns8047/412efb3d1cba79cba130ae60b2a34505](https://gist.github.com/tjdgns8047/412efb3d1cba79cba130ae60b2a34505)

Parsing Data 
===
[https://gist.github.com/tjdgns8047/a9da753691fd22e9858592fb67d08145](https://gist.github.com/tjdgns8047/a9da753691fd22e9858592fb67d08145)


