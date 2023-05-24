# 정규 표현식 (Regular Expression)
[BIG:C:강동욱] 중간과제



# 1. 정규 표현식의 정의 및 특징
- 정규 표현식이란 프로그래밍에서 문자열을 처리하기 위해 표현하는 기법으로, 파이썬뿐만 아니라 문자열을 처리하는 모든 곳에서 사용된다.
- 정규 표현식은 메타 문자를 사용하여 문자열의 패턴을 표현한다. (메타 문자 : 원래 그 문자가 가진 뜻이 아닌 특별한 용도로 사용하는 문자)
- 정규 표현식을 통한 문자열 검색을 통해 데이터 추출, 데이터 유효성 검사, 문자열 대체, 패턴 기반의 처리가 가능하다.
- 정규 표현식 사용을 통해 기존 문자열 검색 코드에 비해 간결하고 직관적인 코드 작성이 가능하다.
- 파이썬에서는 re 라이브러리를 통해 정규 표현식을 지원한다. 또한 re 라이브러리는 정규 표현식을 다루기 위한 메서드 제공한다.


# 2. 정규 표현식의 메타 문자
|메타 문자|설명|
|------|---|
|'.'|줄바꿈 문자인 \n을 제외한 모든 문자와 매치|
|'^'|문자열의 처음|
|'$'|문자열의 끝|
|'*'|0회 이상 반복|
|'+'|1회 이상 반복 |
|'{ }'|{m,n}인 경우 m회 이상 n회 이하 반복 |
|'?'|0회 또는 1회|
|'[ ]'|'[ ]' 사이의 문자들과 매치(문자 클래스)|
|'\\'|바로 뒤에 오는 한 문자와 합쳐서 특수기호로 사용|
|'\|' | '\|' 전에 문자 또는 후에 문자(선택)|
|'( )'|여러 식을 하나로 묶음(그룹)|

|자주 사용하는 문자 클래스 및 특수 기호|설명|
|------|---|
|[a-zA-Z]|알파벳 모두|
|[0-9]|숫자|
|\d|숫자와 매치, [0-9]와 동일한 표현식|
|\D|숫자가 아닌 것과 매치, [^0-9]와 동일한 표현식|
|\s|whitespace 문자와 매치, [ \t\n\r\f\v]와 동일한 표현식 |
|\S|whitespace 문자가 아닌 것과 매치, [^ \t\n\r\f\v]와 동일한 표현식 |
|\w|문자+숫자(alphanumeric)와 매치, [a-zA-Z0-9_]와 동일한 표현식|
|\W|문자+숫자(alphanumeric)가 아닌 문자와 매치, [^a-zA-Z0-9_]와 동일한 표현식|



# 3. 정규 표현식 사용 예제(python)

1. 'YYYY-MM-DD' 형식의 날짜 데이터 매칭 확인
```python
import re

re_date = r"\d{4}-\d{2}-\d{2}"
date1 = "2023-05-24"
date2 = "23-05-24"
date3 = "abcd-ef-gh"

m = re.compile(re_date)

print(m.match(date1))
print(m.match(date2))
print(m.match(date3))

# 출력결과
# <re.Match object; span=(0, 10), match='2023-05-24'>
# None
# None

# 설명
# '\d' 특수 기호를 사용하여 'YYYY-MM-DD' 형식의 날짜 데이터를 표현하는 정규 표현식(re_date) 생성
# re 라이브러리의 match() 메소드를 사용하여 date1, date, date3 각각이 정규 표현식과 동일한 형식인지 검사
# 적합한 경우 Match 객체 리턴, 부합한 경우 None 리턴
```
   
2. Extracting Email Domains
```python
import re
email_pattern = r"@(\w+\.\w+)"
email = "Contact us at email@example.com"
domain = re.findall(email_pattern, email)
print(domain)
```
3. Removing Special Characters and Punctuation
```python
import re
text = "Hello! How are you? #Excited"
clean_text = re.sub(r"[^\w\s]", "", text)
print(clean_text)
```

참고 : https://wikidocs.net/4308 (점프 투 파이썬 docs)
