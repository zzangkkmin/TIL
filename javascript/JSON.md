# JSON

> 2019-11-01 (작성자: 강민)



### preview

vue와 firebase, 그리고 javascript를 사용하면서 데이터 전송을 실시했다. 하지만 파이어베이스에 객체 데이터를 넣으려 할 때 형식이 안맞아 오류가 생겼다. 그래서 이 객체를 JSON으로 고쳐셔 보내는 생각을 하였다.



### JSON

JSON은 JavaScript Object Notation의 줄인말로, 키-값 쌍으로 이루어진 데이터 오브젝트를 전달하기 위해 인간이 읽을 수 있는 텍스트를 사용할 수 있는 표준 포맷이다. 아래는 JSON형태로 이루어진 데이터 포맷 예제이다.

```json
 {
    "이름": "홍길동",
    "나이": 25,
    "성별": "여",
    "주소": "서울특별시 양천구 목동",
    "특기": ["농구", "도술"],
    "가족관계": {"#": 2, "아버지": "홍판서", "어머니": "춘섬"},
    "회사": "경기 수원시 팔달구 우만동"
 }
```



- 장점: JSON은 텍스트로 이루어져 있으므로, 사람과 기계 모두 읽고 쓰기 쉽다.

- 단점: 문법 오류에 민감하다. 사소한 부분이라도 잘 못되면, 전체가 망가진다. 그리고 주석 지원이 불가.



### JSON.stringify() &  JSON.parse()

json은 텍스트로 구조화되어 이루어진 객체이다. 이를 텍스트화 (스트링화) 할 수도 있고, 역으로 JSON에 맞춰서 이루어진 텍스트를 객체화할 수 있다.

- JSON.stringify()
  - JSON객체를 String객체로 변환
- JSON.parse()
  - JSON형태로 된 String객체를 JSON객체로 변환



***여기서 주의할 점***

- ***JSON.stringify()시, JSON객체에 담겨진 method는 삭제가 된다.***
- ***이를 JSON.parse()로 되살려도 원래 객체의 method를 사용못하게 된다.***



위 주의점 때문에 firebase에 넣는 완전한 객체를 사용할 수 없었다. 이는 명심해두자.
