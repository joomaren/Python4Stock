---
title: 파이썬 환경 준비
subtitle: joomaren 
description: Back to the future
---

### Pandas Library를 이용하여 원하는 기간의 주식 정보를 가져오는 방법

<code>주식거래내역 가져오는 코드</code>   
    
```
from pandas_datareader import data
import datetime

start = datetime.datetime(2010,1,1)
end = datetime.datetime(2021,11,29)

dataf = data.DataReader('005930', 'naver', start, end)

print('Read Stock[005930] History')
print(dataf)
```




