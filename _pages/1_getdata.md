---
title: 파이썬 환경 준비
subtitle: joomaren 
description: Back to the future
featured_image:  https://dedostar.github.io/images/about/finger_star.jpg
---

## Python Library 를 이용하기 
Python의 가장 강력한 강점 중에 하나는 너무나도 다양한 Library들을 이용하면 Coding을 좀 더 간단하게 할 수가 있다. 
과거 학교를 다닐 때 생각하면 핑요한 함수들을 만들면서 Coding을 하다 보니 상당한 많은 시간이 Coding을 하는 데 필요하였다. 
하지만 요즘은 몇 줄 되지 않는 라인으로 원하는 결과를 얻을 수 있는데 이것이 Library의 힘이다.
주식 관련해서 가장 많이 사용될 Library는 Pandas Library로써 데이터 분석 Library 중에 하나이다.
Pandas Library는 기본적으로 설치되어진 Library가 아니므로 별도의 install 과정을 하여야 한다.

## Pandas Library를 이욯하여 주식 정보를 가져오기 
Pandas 와 Datetime library를 이용하여 원하는 주직의 과거 데이트를 가져오고 싶다면 아래와 같이 코드를 수행하면 
Naver로 부터 원하는 주식의 정해진 데이트를 가져올 수 있다.
아래의 예는 2010 년 1 월 1일부터 금일 까지의 삼성전자(005930) 주식가격 정보를 가져오는 코드이다.

<code>과거 주식거래내역 가져오는 코드</code>   
    
```
from pandas_datareader import data
import datetime

start = datetime.datetime(2010,1,1)
end = datetime.datetime.now()

dataf = data.DataReader('005930', 'naver', start, end)

print('Read Stock[005930] History')
print(dataf)
```
<code>Datetime library와 Pandas Datareader Library 를 data란 이름으로 import</code>   
    
```
from pandas_datareader import data
import datetime
```

<code>가져오고 싶어하는 기간 설정 : 시작 날부터 오늘까지</code>   
    
```
start = datetime.datetime(2010,1,1)
end = datetime.datetime.now()
```

<code>실제 naver로 부터 dataf란 dataframe으로 가져오기</code>   
    
```
dataf = data.DataReader('005930', 'naver', start, end)
```

<code>가져와서 저장한 dataf 의 내용을 확인하기 위해 내용 출력 </code>   
    
```
print('Read Stock[005930] History')
print(dataf)
```