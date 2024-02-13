# CPU 성능 향상 기법

### 5-1 빠른 CPU를 위한 설계 기법

###### 클럭

- 컴퓨터 부품들은 클럭 신호에 맞춰 일사불란하게 움직인다.

- CPU는 명령어 사이클이라는 정해진 흐름에 맞춰 명령어들을 실행한다.

- 클럭 속도는 헤르츠 단위로 측정한다. 1초에 몇번 진동하는지 나타내는데, 1번이면 1Hz 100번이면 100Hz이다.

- 클럭 속도는 절대적이지 않고 유동적이며 클럭 속도가 높을수록 컴퓨터 실행속도가 빠르나 발열문제가 발생한다. 그래서 클럭속도를 높이는 것만으로 CPU의 성능을 올리는데는 한계가 있다.

###### 코어와 멀티코어

- 요새는 CPU내에 여러개의 명령어를 처리하는 부품을 만들어내는데 이러한 것들을 코어라고 부른다.

- 이러한 코어가 여러개 있으면 멀티코어라고 부른다. 코어 수가 많을 수록 속도는 증가한다.

- 하지만 무제한적으로 늘어나지 않으며, 그 이유는 코어마다 맡는 일이 적절하게 분배되지 않기 때문이다.

###### 스레드와 멀티스레드

- **하드웨어적 스레드** : 하나의 코어가 동시에 처리하는 명령어 단위

- **소프트웨어적 스레드** : 하나의 프로그램에서 독립적으로 실행되는 단위, 한번에 여러 개실행 가능 

### 5-2 명령어 병렬 처리 기법

- 명령어 파이프라인
  
  1. 명령어 인출
  
  2. 명령어 해석
  
  3. 명령어 실행
  
  4. 결과 저장
  
  ![컴퓨터의 구조: 명령어 파이프라인](data:image/png;base64,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)

위 처럼 하나의 명령어 단계를 나누어서 동시에 실행하는 것을 명령어 파이프라이닝이라고 한다.

하지만 이러한 파이프라인닝도 특정한 상황에서 위험한 경우가 있다.

1. 데이터 위험 
   
   - 데이터가 서로 의존적인 상황에서 실행을 동시에 해버리면 서로의 값을 인지하지 못한채 실행되 에러가 발생한다.

   2. 제어 위험

- 분기 등으로 프로그램카운터의 변화가 발생하면 미처 실행을 전부 완료 못한 명령어들이 의미가 없어지게 된다.  
3. 구조적 위험
- 명령어들이 겹처 실행하는 과정에서 서로 다른 명령어가 동시에 ALU, 레지스터 등과 같은 CPU 부품을 사용하려고 할 때를 말한다.

###### 슈퍼스칼라

- CPU 내부에 여러 개의 명령어 파이프라인을 포함한 구조

- 슈퍼스칼라 구조로 명령어 처리가 가능한 CPU를 슈퍼스칼라 프로세서, 슈퍼스칼라 CPU라고 한다.

- 이론적으로 파이프라인 개수에 비례해서 프로그램 처리속도가 빨라지지만 예상치 못한 문제가 있어 비례해서 빨라지지는 않는다. 

###### 비순차적 명령어 처리

- 파이프라인 위험과 같은 예상치 못한 문제들로 명령어들이 곧바로 처리되지 못할 때, 합법적인 새치기를 해서 명령어들을 처리하는 방식

![CS] 명령어 병렬 처리 기법](https://velog.velcdn.com/images/kdi2514/post/2ea50506-64fe-462e-b354-2859f49efabe/image.png)

### 5-3 CISC와 RISC

###### CISC : 명령어 길이가 가변적으로 짧으나 복잡한 명령어 사용으로 클록을 다채롭게 사용해서 파이프라이닝 하기어렵다.

###### RISC : 명령어 길이가 고정적이고, 명령어의 수가 많아지나 단순하고 적은 명령어에 1클럭 내외로 명령어를 수행해서 파이프라이닝에 유리하다.

| CISC                 | RISC                 |
| -------------------- | -------------------- |
| 복잡하고 다양한 명령어         | 단순하고 적은 명령어          |
| 가변 길이 명령어            | 고정 길이 명령어            |
| 다양한 주소 지정 방식         | 적은 주소 지정 방식          |
| 프로그램을 이루는 명령어의 수가 적음 | 프로그램을 이루는 명령어의 수가 많음 |
| 여러 클럭에 걸쳐 명령어 수행     | 1클럭 내외로 명령어 수행       |
| 파이프라이닝하기 어려움         | 파이프라이닝하기 쉬움          |
