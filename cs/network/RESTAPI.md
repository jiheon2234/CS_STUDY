# <span style="font-size:3em;">RESTAPI</span>
2022-08-30 23:38
### TAG  : #restapi
----

## API란?
```n
	컴퓨터의 기능을 실행시키는 방법을 의미한다
```
---
## REST API란?
``` c
특정한 기술을 의미하는 것이 아닌
남의 컴퓨터를 실행시키는 방법!

HTTP를 이용해서 기계들이 통신할 때, HTTP의 잠재력을 최대한 유도하기 위한 "모범사례"
```

### **예시**
|   id  |title |body|
|--|:--:|:--:|
|1| rest| ...|
|2|  ajax | ...|  
|3|json|...|
``` python
Collection
토픽 전체를 식별하고 싶다면 =>   example.com/topics

Element
하나하나 식별하고 싶다면 =>  example.com/topics/1
					   example.com/topics/rest
```

#### 정보의 가공
**http통신에서는 "메소드" 라고 부른다**

- C => POST
- R => GET
- U =>  PUT | PATCH
- D => DELETE

#### RESTAPI에서 규정하지 않는것
```c
클라이언트와 서버가 어떤 데이터 타입으로 통신할 것인지
xml을 쓰던, 제이슨을 쓰던 상관 x
```
#### 규정하는 것
```c
리소스를 식별할땐 uri를 통해서 식별한다
행위를 할 땐, http의 고유한 "메소드"를 사용한다
결과를 알려줄 때는, "응답코드"를 사용한다
```


---
참고:  [생활코딩 유튜브](https://www.youtube.com/watch?v=PmY3dWcCxXI)