#day8 - 파이썬 기초


##변수

**변수의 이름 제한** : 소문자, 대문자, 숫자, 언더스코어(_)

**예약어** : false, class, finally, is, return,
			none, continue, for, lambda, try,
			True, def, from, noniocal. while,
			and, del, global, not, with, as, 
			elif, if, or, yield, assert, else,
			import, pass, break, except, in, raise

**type( )**:  괄호 속 변수의 type 을 출력
	

##숫자

**수학 연산자**

|연산자|설명|예|결과|
|----|----|---|---|
|+|더하기|32+7|39|
|-|뺴기|82-2|80|
|*|곱하기|3*7|21|
|/|나누기|7/2|3.5|
|//|정수나누기|7//2|1|
|%|나머지|7%3|1|
|**|지수|2**10|1024|

**진수(base)**

2진수(binary): 0b 로 시작
8진수(octal): 0o 로 시작
16진수(hex): 0x 로 시작

##문자열

**입력 방법**

* ' (작은따옴표), " (큰따옴표)  둘 다 가능
* '''문자열''' (작은따옴표 3개) : 내부에서 띄어 쓰기 가능

**이스케이프 문자**

* \a: 비프음 발생
* \t: 탭
* \n: 줄 바꿈
* \\: \(역슬래시) 입력
* \': 작은따옴표 입력
* \": 큰따옴표 입력

**인덱스 연산**


문자열에서 문자를 추출하기 위해 대괄호와 오프셋을 지정할 수 있다.
가장 왼쪽은 0이며, 가장 오른쪽은 -1로 시작한다.

```
In [13]: string = '안녕하세요'

In [14]: string[0]
Out[14]: '안'

In [15]: string[-1]
Out[15]: '요'
```

**슬라이스 연산**

* [:]
	* 처음부터 끝까지
* [start:]
	* start오프셋부터 마지막 까지
* [:end]
	* 처음부터 end오프셋 까지
* [start:end]
	* start오프셋부터 end오프셋까지
* [start:end:step]
	* start오프셋부터 end오프셋까지, step만큼씩 뛰어넘은 부분

```
In [18]: string[:2]
Out[18]: '안녕'

In [19]: string[2:5:2]
Out[19]: '하요'
```

**문자열 나누기(split)**

```
In [20]: girlsday= '민아,유라,소진,혜리'

In [21]: girlsday.split(',')
Out[21]: ['민아', '유라', '소진', '혜리']
```
split 함수에 인자를 주지 않을 경우, 공백문자를 구분자로 사용한다.


**문자열 결합(join)**

```
In [22]: girlsday_list=girlsday.split(',')

In [23]: girlsday_list
Out[23]: ['민아', '유라', '소진', '혜리']

In [24]: girlsday_str=','.join(girlsday_list)

In [25]: girlsday_str
Out[25]: '민아,유라,소진,혜리'

In [26]: girlsday_str2=''.join(girlsday_list)

In [27]: girlsday_str2
Out[27]: '민아유라소진혜리'
```

**대소문자 다루기**

```
In [1]: lux='lux, the lady of luminosity'

In [2]: lux.upper()
Out[2]: 'LUX, THE LADY OF LUMINOSITY'

In [3]: lux.lower()
Out[3]: 'lux, the lady of luminosity'
```

**문자열 포맷**

```
In [12]: d=37

In [13]: f=3.14

In [14]: s='fastcampus'

In [15]: '%d %f %s' %(d,f,s)
Out[15]: '37 3.140000 fastcampus'

In [16]: '11%d 11%f 11%s' %(d,f,s)
Out[16]: '1137 113.140000 11fastcampus'

In [17]: '%11d %11f %11s' %(d,f,s)
Out[17]: '         37    3.140000  fastcampus'

In [18]: '%-11d %-11f %-11s' %(d,f,s)
Out[18]: '37          3.140000    fastcampus '

In [19]: '%-11.3d %-11.3f %-11.3s' %(d,f,s)
Out[19]: '037         3.140       fas        '

In [20]: '%-11.1d %-11.1f %-11.1s' %(d,f,s)
Out[20]: '37          3.1         f          '
```

**새 스타일({}, format)**

>{}.format(변수)


```
In [23]: dict = {'d':d,'f':f,'s':s}

In [25]: '{0[d]} {0[f]} {0[s]} {1}'.format(dict, 'WPS')
Out[25]: '37 3.14 fastcampus WPS'

```

##시퀀스 타입

###list

**list 생성**

```
In [33]: list2 = list()
In [34]: list3=['a','b','c','d']
In [37]: list2=list('league of legend')
In [38]: list2
Out[38]: 
['l', 'e', 'a', 'g', 'u', 'e', ' ', 'o', 'f', ' ', 'l', 'e', 'g', 'e', 'n', 'd']

```
**슬라이스 연산**

```
In [40]: list2[:3]
Out[40]: ['l', 'e', 'a']

In [41]: list2[:len(list2):2]
Out[41]: ['l', 'a', 'u', ' ', 'f', 'l', 'g', 'n']

In [51]: list2[-1:-len(list2)+1:-1]
Out[51]: ['d', 'n', 'e', 'g', 'e', 'l', ' ', 'f', 'o', ' ', 'e', 'u', 'g', 'a']
```

**list 병합(extends, +=)**

```
In [68]: fruits.extend(colors)

In [69]: fruits
Out[69]: ['apple', 'banana', 'melon', 'red', 'green', 'blue']
```

