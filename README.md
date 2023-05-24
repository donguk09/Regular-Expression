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
|'[ ]'|'[]' 사이의 문자들과 매치|
|'\\'|바로 뒤에 오는 한 문자와 합쳐서 특수기호로 사용|
|\| | \| 전에 문자 또는 후에 문자(선택)|
|'( )'|여러 식을 하나로 묶음(그룹)|


# 3. 정규 표현식 사용 예제(python)




참고 : https://wikidocs.net/4308 (점프 투 파이썬 docs)
