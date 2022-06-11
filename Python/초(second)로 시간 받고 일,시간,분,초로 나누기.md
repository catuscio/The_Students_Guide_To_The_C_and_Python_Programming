``` python
second = int(input()) #초 입력

#초를 나눌 인자들 정리
d = 24*60*60  #일
h = 60*60     #시
m = 60        #분(초는 분의 나머지가 될 것이다)

days = second // d
second %= d         #계산한 나머지로 다른 날짜 계산을 이어간다
hours = second // h
second %= h
minutes = second // m
second %= m

print("%02ddays %02d:%02d:%02d" %(days, hours, minutes, second))
```
