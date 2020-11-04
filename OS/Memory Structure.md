## 메모리 구조

![메모리 구조](https://github.com/zhsks528/TIL/blob/master/Resource/Memory%20Structure.PNG)

사진 주소 : http://tcpschool.com/c/c_memory_structure

### 1. 코드(Code) 영역

메모리의 코드(Code) 영역은 실행할 프로그램의 코드가 저장되는 영역으로 텍스트 영역이라고도 부른다.

- CPU는 코드 영역에 저장된 명령어를 하나씩 가져가서 처리하게 된다.

### 2. 데이터(data) 영역

메모리의 데이터(data) 영역은 **프로그램의 전역 변수와 정적(static) 변수가 저장되는 영역**이다.

- **데이터 영역은 프로그램의 시작과 함께 할당되며, 프로그램이 종료되면 소멸**한다.

### 3. 힙(heap) 영역

메모리의 힙(heap) 영역은 사용자가 직접 관리할 수 있는 '그리고 해야만 하는' 메모리 영역이다.

- **사용자에 의해 메모리 공간이 동적으로 할당되고 해제**된다.
- 메모리의 낮은 주소에서 높은 주소의 방향으로 할당된다.
- 할당해야 할 메모리의 크기를 프로그램이 실행되는 동안 결정해야 하는 경우 (런타임 때) 유용하게 사용되는 공간이다.
- Heap overflow : heap이 커지다 stack을 침범
- ex) c언어 malloc, new
- **힙 영역이 필요한 이유**
  - 사용자의 요구에 맞게 메모리를 할당해 주기 위해서는(런타임에 메모리 크기를 결정하고 싶을 때) 메모리 동적 할당을 통해 힙 영역에 메모리를 할당해야 한다.

### 4. 스택(stack) 영역

메모리의 스택(stack) 영역은 **함수의 호출과 관계되는 지역 변수와 매개변수가 저장되는 영역**이다.

- **함수의 호출과 함께 할당**되며, **함수의 호출이 완료되면 소멸**한다.
- 스택 프레임(stack frame) : 스택 영역에 저장되는 호출 정보
- 후입선출(LIFO, Last-In First-Out) 방식에 따라 동작한다.
- Stack overflow : stack이 커지다 heap을 침범

### 5. 참조

- [메모리의 구조](http://tcpschool.com/c/c_memory_structure)
- [스택(Stack), 힙(Heap), 데이터(Data) 영역](https://dsnight.tistory.com/50)

- [What and where are the stack and heap?](https://stackoverflow.com/questions/79923/what-and-where-are-the-stack-and-heap)
