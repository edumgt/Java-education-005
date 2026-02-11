# Java 학습 저장소 가이드

이 저장소는 **Java 기초 문법부터 객체지향, 컬렉션, 예외처리까지** 단계적으로 학습할 수 있도록 구성된 예제 모음입니다.

초심자가 따라가기 좋은 구조로 되어 있으며, 각 디렉터리(챕터)마다 핵심 개념을 간단한 실행 코드로 익힐 수 있습니다.

---

## 1) 학습 목표

이 저장소를 통해 아래 내용을 학습할 수 있습니다.

- 배열 선언/초기화/반복문 순회
- 추상 클래스와 상속
- 다형성(업캐스팅, 부모 타입으로 참조)
- 인터페이스 기반 설계
- Wrapper/파싱 개념
- `ArrayList`, `HashMap` 등 컬렉션 기초
- `try-catch-finally` 기반 예외 처리

---

## 2) 저장소 구조

```text
arraytest/   : 배열 기초 실습
chapter09/   : 추상 클래스, 상속, 다형성
chapter10/   : 인터페이스, 구현 클래스, 다형성 활용
chapter11/   : Wrapper 클래스, 문자열/숫자 변환
chapter12/   : 컬렉션(ArrayList, HashMap)
chapter14/   : 예외 처리 기초
```

---

## 3) 챕터별 학습 포인트

### arraytest

- `Array01.java`, `ArrayTest01.java`, `ArrayScore.java`
- 배열에 값 저장하고 인덱스로 접근하는 방법
- `Scanner` 입력값을 배열에 넣어 처리하는 흐름 학습

추천 실습
- 입력 개수를 3개에서 N개로 늘려 평균/최댓값/최솟값 계산해보기

### chapter09 (추상 클래스 + 상속 + 다형성)

- `Animal`, `Dog`, `Cat`, `AnimalMain`
  - 추상 클래스는 직접 객체 생성 불가
  - 자식 클래스에서 추상 메서드 구현
  - 부모 타입(`Animal`)으로 여러 자식을 하나의 타입으로 처리하는 다형성 학습
- `AParent`, `Child`, `AMain`
  - 추상 클래스 생성자 호출 구조 및 상속 관계 학습

추천 실습
- `Animal`을 상속한 `Bird` 클래스를 추가하고 `sound()` 오버라이딩해보기
- `animalSound()` 메서드에 여러 동물을 전달해 동작 확인하기

### chapter10 (인터페이스 중심 설계)

- `IRemoteControl`, `ISearchable`, `TelevisionImpl`, `RemoteMain`
  - 인터페이스 다중 구현을 통한 기능 분리(전원/볼륨/검색)
- `IToy`, `IMoveArmLeg`, `IMissile`, `ILight` 및 `MazingerToyImpl`, `PoohToyImpl`, `BarbieToyImpl`, `ToyMain`
  - 장난감 타입별 기능 조합
  - 사용자 입력(Scanner)에 따라 구현체를 선택하고 공통 인터페이스로 처리
- `InterfaceA`, `InterfaceB`, `InterfaceC`, `CImpl`, `Test`
  - 인터페이스 상속 구조와 구현 클래스 사용 예제

추천 실습
- 새로운 장난감 클래스를 만들어(`IronManToyImpl` 등) `IToy` 규약에 맞춰 확장해보기
- `ToyMain`의 `if-else`를 `switch`로 바꿔 가독성 개선하기

### chapter11 (Wrapper/파싱)

- `Wrapper01.java`
- `Integer.parseInt()`로 문자열을 정수로 변환
- `String.valueOf()`로 숫자를 문자열로 변환
- 외부 데이터 처리 시 자주 쓰이는 파싱 개념 학습

추천 실습
- 숫자가 아닌 문자열 입력 시 예외가 나는 상황을 만들고 `try-catch`로 처리해보기

### chapter12 (컬렉션)

- `ArrayList01.java`
  - `add`, `set`, `remove`, `get`, `size` 사용
  - 일반 `for`와 향상된 `for-each` 순회 비교
- `HashMap01.java`
  - `put`, `get` 기초 사용
  - Key-Value 구조 데이터 처리 학습

추천 실습
- `HashMap`에 학생 이름/점수를 저장하고 평균 점수 계산 로직 작성해보기

### chapter14 (예외 처리)

- `Exception01.java`
- 예외 처리 4가지 개념 소개
  1. `try-catch-finally`
  2. `throw`
  3. `throws`
  4. 사용자 정의 예외

추천 실습
- 실제 예외가 발생하는 코드(0으로 나누기, 배열 인덱스 초과 등)를 넣고 처리 흐름 확인하기

---

## 4) 실행 방법

> 아래 명령은 저장소 루트(`/workspace/java-education-005`)에서 실행합니다.

### 단일 파일 실행 예시

```bash
javac chapter09/AnimalMain.java
java chapter09.AnimalMain
```

```bash
javac chapter10/RemoteMain.java
java chapter10.RemoteMain
```

### 전체 컴파일

```bash
find . -name "*.java" -print0 | xargs -0 javac
```

컴파일 후 실행은 패키지명을 포함해 `java 패키지명.클래스명` 형식으로 실행합니다.

---

## 5) 추천 학습 순서

1. `arraytest` → 배열/반복문 기초
2. `chapter09` → 추상 클래스와 상속, 다형성
3. `chapter10` → 인터페이스 설계와 구현
4. `chapter11` → 데이터 타입 변환
5. `chapter12` → 컬렉션 프레임워크 기초
6. `chapter14` → 예외 처리

---

## 6) 스스로 확장해보기

- 각 챕터 예제를 **메서드 분리**로 리팩터링
- 입력 검증 로직 추가 (`Scanner` 입력 오류 대응)
- 클래스/인터페이스 다이어그램 그리기
- 작은 콘솔 프로젝트로 통합 (예: 학생 성적 관리 프로그램)

---

## 7) 한 줄 정리

이 저장소는 단순 문법 암기가 아니라, **Java의 객체지향 사고(상속/다형성/인터페이스)와 실무 기본기(컬렉션/예외처리)**를 예제로 익히기 좋은 학습용 프로젝트입니다.
