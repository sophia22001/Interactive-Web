# CSS 변환과 애니메이션

## Transform

### 01. hover시 변형

- `transform: scale(2) rotate(15deg);` : 두배로 커짖고 15도로 회전
- `transform: skewY(30deg);` : Y축으로 비틀기
- `transform: translate(30px, 10px);` : 30px 오른쪽, 10px 아래쪽으로 위치를 이동

### 01-2. 기준점 이동

- `transform-origin: left top;` : 맨 왼쪽 위에서 기준점 시작

## 02. transition : 동작 시간

- `transition: 1s;` : 1초 동안 애니매이션 동작
- `transition: 1s 2s;` : 2초 딜레이 발생
- `transition: 1s linear;` : 가속도가 아닌 등속도로 동작

## animation

### 03. animation : 위치 이동

- **keyframes** 를 사용하여 경로를 설정한다.
- ```
  @keyframes sample-ani {
          0% {
            transform: translate(0, 0);
          }
          50% {
            transform: translate(300px, 0);
          }
          100% {
            transform: translate(400px, 500px);
          }
        }
  ```
  : 0% ~ 100% 로 변경점인 키 프레임을 설정하여 위치 이동 경로를 설정할 수 있다.
- `animation: sample-ani 2s linear infinite;` : 2초동안 등속도로 무한히 반복하게 동작할 수 있다.
- ` animation: sample-ani 2s linear 3;` : 3번만 반복하기도 가능

### 04. animation : 위치 이동 심화

- `animation: sample-ani 3s linear infinite alternate;` : alternate을 통해 왔던 경로로 다시 가기 -> 왕복
- `animation: sample-ani 3s linear infinite reverse;` : 경로 반대쪽에서 시작
- `animation: sample-ani 3s linear forwards;` : forward를 통해 끝난 지점에 머무르게 하기
- `animation-play-state: paused;`: 애니메이션 멈추기

### 05. animation: 프레임 바이 프레임

- 요즘은 고해상도를 위해 절반 크기로 이용한다.
- `animation: spaceship-ani 1s infinite steps(17);` : steps로 프레임 마다 이동하게 한다.
- 코드로 애니매이션 동작을 제어할 수 있고, 뒷 투명 배경에도 영향을 안끼치기 때문에 gif 보다 좋다.
