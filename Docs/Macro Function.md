# Macro Function

주말에 피시방에서 오버워치하다가 갑자기 떠오른 아이디어라서 정리가 잘 되지 않았습니다.

매크로는 동적으로 코드 추가를 함수 사용처럼 해줍니다 (??)
예를 들어, 변수 `a`의 `length` 멤버변수가 어떠한 값을 리턴한다고 할 때,
```python
var macro1 = &(.length)

macro1(a)
```
이 때 `macro1(a)`는 `a.length`와 동일한 코드입니다.
이는 map같은 고계함수를 사용하기 쉽게 해줍니다.
```python
map(&(.length), [[1, 2, 3], [4, 5, 6], [7, 8]])
```

매크로는 단순한 코드 치환에 불과합니다. 예를 들어, 다음과 같은 매크로 `plus_macro`가 있다고 합시다.

```python
var plus_macro = &(+=1)
a, b, c = 1, 2, 3
map(plus_macro, [&a, &b, &c])
print(a, b, c)
```

위 코드는 2, 3, 4를 출력할 것입니다.