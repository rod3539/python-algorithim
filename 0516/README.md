# 파이썬

`파이썬` : 네덜란드 컴퓨터 과학자 귀도 반 로섬이 만든 새로운 언어



## 파이썬 문법

* 인덴트(Indent)
  * 공백 4칸 들여쓰기가 원칙이다.
* 네이밍 컨벤션(Naming Convention)
  * 각 단어를 밑줄(_)로 구분하여 표기하는 스네이크 케이스(Snake Case)를 따른다.
  * 파이썬의 PEP 8 및 철학에 따라 스네이크 코딩을 자향한다.
* 타입 힌트
* 리스트 컴프리헨션(List Comprehension)
  * 파이썬은 map, filter와 같은 함수형 기능을 지원하며 람다 표현식도 지원한다.
  * ex) `list(map(lambda x: x + 10, [1, 2, 3]))`

```python
# 리스트 컴프리헨션을 사용한 경우
# 홀수인 경우 2를 곱해 출력
>>> [n * 2 for n in range(1, 10 + 1) if n % 2 == 1]
# 리스트 컴프리헨션을 사용하지 않는 경우
>>> a = []
>>> for n in range(1, 10 + 1):
    	if n % 2 == 1:
            a.append(n * 2)
```

* 제너레이터(Generator)
  * 루프의 반복 동작을 제어할 수 있는 루틴 형태를 말한다.
  * yield 구문을 사용하면 제너레이터를 리턴할 수 있다. 기존 함수는 return 구문을 맞닥뜨리면 값을 리턴하고 모든 함수의 동작을 종료한다. 그러나 yield는 제너레이터가 여기까지 실행중이던 값을 내보낸다는 의미로 중간값을 리턴한 다음 함수는 종료되지 않고 계속해서 맨 끝에 도달할 때까지 실행된다.
  * 만약 값을 생성하려면 next()로 추출하면 된다.

```python
# 이 경우 함수의 리턴 값은 제너레이터가 된다.
>>> def get_natural_number():
    	n = 0
        while True:
            n += 1
            yield n
>>> get_natural_number()
<generator object get_natural_number at 0x10d3139d0>
>>> g = get_natural_number()
	for _ in range(0, 100):
        print(next(g))
...
1
2
3
4
...
98
99
100
```

* range
  * 제너레이터 방식을 활용하는 대표적인 함수로 range()가 있다.
* enumerate
  * 열거하다는 뜻의 함수로 여러가지 자료형(list, set, tuple 등)을 인덱스를 포함한 enumerate 객체로 리턴한다.

```python
>>> a = [1, 2, 3, 2, 45, 2, 5]
>>> list(enumerate(a))
[(0, 1), (1, 2), (2, 3), (3, 2), (4, 45), (5, 2), (6, 5)]
```

## 변수명과 주석

* 파이썬에서 간단한 주석을 부여하는 편이 훨씬 더 가독성이 높아보인다.
* 변수명은 의미 없는 이름보다는 각각의 의미를 부여해 작명해야 한다.