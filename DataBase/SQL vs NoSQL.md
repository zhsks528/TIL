## SQL vs NoSQL

### 1. 관계형 데이터베이스 (SQL)

#### 장점

1. 명확하게 정의된 스키마로 인해 데이터 무결성이 보장된다.
2. 관계를 통해 각 데이터를 중복없이 한 번만 저장할 수 있다.

#### 단점

1. NoSQL에 비해 덜 유연하다.
2. 데이터 스키마를 수정하는 것이 어렵고 불가능할 수 있다.
3. 과도한 JOIN문으로 인해 복잡한 쿼리가 만들어 질 수 있다.
4. 수평 확장이 어렵고, 보통 수직 확장만 가능하다.
   - 즉 어느 시점에서 처리량/처리 능력과 관련하여 약간의 성장 한계에 직면하게 될 수 있다.

#### 사용하는 곳

1. 어플리케이션의 여러 부분에서 관련 데이터가 비교적 자주 변경되는 경우
2. 명확한 스키마가 중요하며, 데이터 구조가 극적으로 변경되지 않을 때

### 2. 비 관계형 데이터베이스 (NoSQL)

#### 장점

1. 데이터 스키마가 없어서 유연성이 높다.
2. 애플리케이션에 필요한 형식으로 데이터를 저장하기 때문에 데이터를 가져오는 속도가 빠르다.
3. 수직 및 수평 확장이 가능하다.
4. 데이터베이스가 애플리케이션에서 발생시키는 모든 읽기 / 쓰기 요청을 처리할 수 있다.

#### 단점

1. 유연성으로 인해, 데이터 구조 결정이 늦어질 수 있다.
2. 복사된 데이터가 변경되면 여러 콜렉션과 문서를 수정해야한다.

#### 사용하는 곳

1. 정확한 데이터 요구사항을 알 수 없거나 관계를 맺고 있는 데이터가 자주 변경되는 경우
2. 읽기 처리를 자주하지만, 데이터를 자주 변경하지 않는 경우
   - 한번의 변경으로 수십 개의 문서를 수정할 필요가 없는 경우
3. 데이터베이스를 수평으로 확장해야 하는 경우
   - 막대한 양의 데이터를 다뤄야 하는 경우, 읽기/쓰기 처리량이 큰 경우

### 3. 참고자료

- [SQL(관계형 데이터베이스)과 NoSQL(비 관계형 데이터베이스) 개념/비교/차이](https://devuna.tistory.com/25)
- [데이터베이스 종류와 장/단점 (계층형/네트워크형/SQL/NoSQL)](https://ourcstory.tistory.com/30)