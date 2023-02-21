# <b>문자열</b>
<br><br>

## <b>Ⅰ. 문자의 표현 </b>

---

### <b>ⅰ. 컴퓨터에서의 문자 표현</b>
<br>

메모리는 숫자만을 저장할 있기 때문에 각 문자에 대해 대응되는 숫자를 정해서 메모리에 저장

영어가 대소문자 합쳐서 52이므로 6(2^6 = 64가지)비트면 모두 표현 가능

네트워크가 발전하면서 서로 간 정보를 주고 받을 때 서로 다른 코드 체계때문에 정보를 달리 해석하게 됨  

---

### <b>ⅱ. ASCII</b>
<br>
혼동을 피하기 위해 표준안이 만들어짐
- ASCII(American Standard Code for Information Interchange)  

ASCII는 7bit 인코딩으로 128문자를 표현  
- 33개의 출력 불가능한 제어 문자들
- 95개의 출력 가능한 문자들  

|ASCII|String|ASCII|String|ASCII|String|ASCII|String|ASCII|String|ASCII|String|
|---|---|---|---|---|---|---|---|---|---|---|---|
|32||48|0|64|@|80|P|96|`|112|p|
|33|!|49|1|65|A|81|Q|97|a|113|q|
|34|"|50|2|66|B|82|R|98|b|114|r|
|35|#|51|3|67|C|83|S|99|c|115|s|
|36|$|52|4|68|D|84|T|100|d|116|t|
|37|%|53|5|69|E|85|U|101|e|117|u|
|38|&|54|6|70|F|86|V|102|f|118|v|
|39|'|55|7|71|G|87|W|103|g|119|w|
|40|(|56|8|70|H|88|X|104|h|120|x|
|41|)|57|9|73|I|89|Y|105|i|121|y|
|42|*|58|:|74|J|90|Z|106|j|122|z|
|43|+|59|;|75|K|91|[|107|k|123|{|
|44|,|60|<|76|L|92| \ |108|l|124|\||
|45|-|61|=|77|M|93|]|109|m|125|}|
|46|.|62|>|78|N|94|^|110|n|126|~|
|47|/|63|?|79|O|95|_|111|o|||



---

### <b>ⅲ. 확장 ASCII</b>
<br>

표준 문자 이외의 부가적인 문자를 128개 추가할 수있게 하는 부호
- 확장 아스키는 1B내의 8bit를 모두 사용
- 여러 가지 다양한 문자에 할당할 수 있도록 하고 있음 
- 이렇게 할당된 확장 부호는 서로 다른 프로그램이나 컴퓨터 사이에 교환되지 못함
- 프로그램이나 컴퓨터 또는 프린터가 그것을 해독할 수 있도록 설계되어 있어야 함

---

### <b>ⅳ. 유니코드</b>
<br>

국가 간 정보의 교환에서도 문제 발생  

자국의 코드체계를 타 국가가 가지고 있지 않으면 정보 해석 오류 발생  

다국어 처리를 위해 표준을 마련

유니코드도 다시 Charater Set으로 분류
- UCS-2(Universal Character Set 2)
- UCS-4(Universal Character Set 4)
- 유니코드를 저장하는 변수의 크기를 정의
- 바이트 순서에 대해서 표준화하지 못 했음
- 즉, 파일을 인식 시 파일이 UCS-2, UCS-4인지 인식하고 각 경우를 구분해서 모두 다르게 구현해야함
- 유니 코드의 적당한 외부 인코딩이 필요

---

### <b>ⅴ. 인코딩</b>
<br>

유니코드 인코딩(UTF: Unicode Transformation Format)
UTF-8(in web)
- MIN: 8bit, MAX: 32bit(1 Byte * 4)
UTF-16(in windows, java)
- MIN: 16bit, MAX: 32bit(2 Byte * 2)
UTF-32(in unix)
- MIN: 32bit, MAX: 32bit(4 Byte * 1)

Python 인코딩
- 2.x 버전 - ASCII > -\*- coding: utf-8 -\*-(첫 줄에 명시)
- 3.x 버전 - 유니코드 UTF > 생략 가능
- 다른 인코딩 방식으로 처리 시 첫줄에 작성하는 위 항목에 원하는 인코딩 방식을 지정

<br><br>

## <b>Ⅱ. 문자열 </b>

---

### <b>ⅰ. 문자열의 분류</b>
<br>

문자열
- fixed length
- varialbe legnth
- - length controlled (java)
- - delimited (delimited)

java  
java.lang.String 클래스에 네 가지 필드들이 포함
- hash값(hash)
- 문자열의 길이(count)
- 문자열 데이터의 시작점(offset)
- 배열에 대한 참조(value)

C언어  
- 문자들의 배열 형태로 구현된 응용 자료형
- 저장할 때 항상 마지막에 끝을 표시하는 널문자`("\0")`을 넣어주어야함
- 문자열 처리에 필요한 연산을 함수 형태로 제공
> char ary[] = {'a','b','c','\0'}  
또는  
>char ary[] = "abc";

---

### <b>ⅱ. 문자열의 처리</b>
<br>

#### <b>JAVA</b>  
Sring 클래스를 사용  

> String str= "abc"  
> String Str = new String("abc")  

문자열 처리에 필요한 연산을 연산자, 메소드 형태로 제공
- `+`, `length()`, `split()`, `substring()`
- 보다 풍부한 연산을 제공  

#### <b>PYTHON</b>   
char 타입 없음  

텍스트 데이터의 취급방법이 통일되어 있음  

문자열 기호
- `'`, `"`, `'''`, `"""`
- 연결 : `str1 + str2`
- 반복 : `str1 * n`  

문자열은 시퀀스 자료형으로 분류  
시퀀스 자료형에서 사용할 수 있는 연산 사용 가능  

문자열 클래스에서 제공되는 메소드
- `replace()`, `split()`, `isalpha()`, `find()`  

문자열은 튜플과 같이 요소값을 변경할 수 없음

#### <b>각 언어의 기본적인 차이점</b>
C : 아스키 코드로 저장  

JAVA : 유니코드(UTF16, 2byte)로 저장  

PYTHON : 유니코드(UTF8)로 저장

---

### <b>ⅲ. 문자열의 비교</b>
<br>

C : `strcmp()` 함수를 제공  

JAVA : `equals()` 메소드를 제공
- `==` 연산은 메모리 참조가 같은지를 묻는 것  

PYTHON : `==` 연산자와 `is` 연산자를 제공
- `==` : 내부적으로 특수 메서드 `_eq_()`를 호출
>```python 
> s1 = 'abc'
> s2 = 'abc'
> s3 = s1[:2] + 'c'
> s1 == s2 # True
> s1 is s2 # True
> s1 == s5 # True
> s1 is s5 # False
>```
  
---

### <b>ⅳ. 문자열을 정수로 변환</b>
<br>

C : `atoi()` 함수를 제공
- 역함수는 `itoa()`

JAVA : `parse()` 메소드를 제공
- 역함수는 `toString()` 

PYTHON : 숫자와 문자변환 함수를 제공

>```python 
>int('123')
>float('3.14')
>str(123)
>repr(123)
>```

<b>`atoi()`함수 구현하기</b>

>```python
>def atoi(s):
>   i = 0
>   for x in s:
>       i = i*10 +ord(x) - ord('0')
>   return i
>```

<br><br>

## <b>Ⅲ. 패턴 매칭 </b>

---

### <b>ⅰ. Brute Force</b>
<br>

처음부터 끝까지 순회하면서 문자들을 일일이 비교하는 방식

>```python
>p = 'is'  # 찾을 패턴
>t = "This is a book_!"  # 전체 텍스트
>
>def BruteForce(p, t):
>   M = len(p)  # 찾을 패턴의 길이
>   N = len(t)  # 전체 텍스트길이
>   i = 0  # t의 인덱스
>   j = 0  # p의 인덱스
>   while j < M and i < N:
>       if t[i] != p[j]:
>           i = i-j
>           j = -1
>       i = i + 1
>       j = j + 1
>   if j == M : return i - M  # 검색 성공
>   else: return -1
>```

시간복잡도
- 최악의 경우 모든 위치에서 패턴을 비교해야 함
- O(MN)  

---

### <b>ⅱ. KMP</b>
<br>

불일치가 발생한 앞부분에 대하여 다시 비교하지 않고 매칭을 수행  

패턴을 전처리하여 배열 netx[M]을 구해서 잘못된 시작을 최소화
- next[M]: 불일치가 발생했을 경우 이동할 다음 위치  

시간복잡도
- O(M+N)

---

### <b>ⅲ. 보이어-무어</b>
<br>

오른쪽에서 왼쪽으로 비교  

대부분의 상용 소프트웨어에서 채택하고 있는 알고리즘  

끝 문자가 불일치, 이 문자가 패턴 내에 존재하지 않는 경우
- 이동 거리: 패턴 길이

끝문자가 불일치, 이 문자가 패턴에 존재할 경우  
o|o|o|w|a|t|e|r
---|---|---|---|---|---|---|---|
w|a|t|e|<b>r</b>
||||w|<b>a</b>|t|e|r  

앞 두 매칭 알고리즘의 최선의 경우 = O(n)  

보이어-무어 알고리즘은 텍스트 문자를 다 보지 
않아도 됨  

발상의 전환: 패턴의 오른쪽부터 비교  

최악의 경우 수행시간: O(mm)  

입력에 따라 다르지만 일반적으로 O(n)보다 시간이 덜 듦