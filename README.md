# java-racingcar-kakao

## 기능 요구사항
- Position을 만든다.
- Car를 만든다.
    - 전진 메서드를 만든다.(랜덤)
- 자동차 이름, 게임 횟수를 입력받아 검증한다.
- Racing을 만들어서 입력 문자열을 바탕으로 Car 객체를 생성한다.
- 라운드마다 자동차를 이동시킨다.
- 우승자를 가린다.

### 경기 전
- 경주할 자동차 이름을 받아서 Split을 한다.
    - 예외처리 (InvalidInputException)
        - 각 이름이 5글자
            - length
        - 자동차가 1개 이하
            - split한 배열의 사이즈 1 이하
        - split한 string의 길이 0
        - 자동차 이름 중복
            - HashSet
    - Car 객체들을 생성한다.
        - 이름, 위치를 설정한다.
            - 위치 객체를 생성한다.
- 시도 횟수 입력
    - 예외처리
        - 정수 아닐 때
        - 0 이하일때
- 각 Car마다 초기 위치를 출력한다.

### 경기 중
- 각 턴마다 Car 객체에서 try한다.
    - Random 돌려서 4 이상일 경우 전진
    - 각 Car의 위치를 출력한다.
        - 위치만큼 -를 출력한다.

### 경기종료 후
- 우승자를 출력한다.
    - 전체 Car에 대해 우승자를 가려낸다.
        - 반복문을 통해 Max값, Max값인 차 찾기
    - 우승자가 여럿인 경우 ", "를 구분자로 연결해서 출력한다.


### 도메인
- Car
    - 이름, 위치 객체 초기화
    - 전진 시도
- Position
    - 위치 값 초기화
    - 위치 출력
- Racing
    - 자동차 이름 입력받기
    - 자동차 객체 생성
    - 시도 횟수 입력받기
    - 라운드 진행
    - 결과 출력

## 리펙터링 요구사항
- 핵심 비지니스 로직을 가지는 객체를 domain 패키지, UI 관련한 객체를 view 패키지에 구현한다.
- MVC 패턴 기반으로 리팩토링해 view 패키지의 객체가 domain 패키지 객체에 의존할 수 있지만, 
  domain 패키지의 객체는 view 패키지 객체에 의존하지 않도록 구현한다.
- 테스트 가능한 부분과 테스트하기 힘든 부분을 분리해 테스트 가능한 부분에 대해서만 단위 테스트를 진행한다.

## 리펙터링 목록
[x] 핵심 비지니스 로직을 domain 패키지, UI를 view 패키지로 분리
[ ] domain 내에 UI에 해당하는 부분들을 view 패키지의 별도 클래스로 분리

