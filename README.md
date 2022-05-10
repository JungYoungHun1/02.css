## CSS Education

step03
lab02_position
sticky

z-index - 요소 쌓임 순서
: 쌓여 있는 순서를 통해 z축을 결정
1. html순서에서 마지막에 위치할 수록 위에 쌓임

2. position이 있을 경우
- static이면 뒤로 빠짐

step04
flex

:메인축 / 수직축
container / item


flex - 수평, inline-flex

main / cross
flex-dierction : row/column
flex - wrap : 줄넘김 처리(컨테이너가 아이템을 담을 공간이 없을 때 줄바꿈 방식 )
- 창이 좁아졌을때 자동으로 밑으로 내려줌

justify-content : 주축 정렬 - 가로축 정렬
end, space-around(양쪽 간 공백 맞춤), space-between(끝에 맞추고 ), space-evenly(빈 공백 균등 배분)

align - content = 수직 축 정렬 (빈 공간이 있을때 + 여러줄이 있을때)

align-item = 세로축정렬

아이템에 부여하는 속성
- order : 순서지정(숫자 클수록 뒤로 밀림)
- default = 0

flex-grow : 증가하는 너비 비율 설정
grow 1, grow 2
다른 컨텐츠를 쓰고 남은 부분을 1:2로 사용

flew - shrink : 감소하는 너비 비율 설정

flex-basis = 균등한 너비로 배치

flex : 증가, 감소, 기본(0, 1, auto)
기본은 flex-basis를 의미한다 따라서 본래 basis의 기본값은 auto
그런데 축약 표현으로 basis를 표현할때 기본값은 auto가 아니라 0으로 표현된다.


step05
transition
- css 속성의 시작과 끝을 지정하여 중간에 에니메이션 효과를 넣도록 하는 역할
transition-property : 속성 이름 (all) 
transition-duration : 지속 시간(기본 : 0s)
transition-timing-function : 타이밍 함수(ease)
transition-delay : 대기 시간(0s)


transform : 요소의 변환효과 지점
transform : 변환함수 1, 2, 3...
transform : 원근법 이동 크기 회전 기울임
- 2D 변환 함수
이동 : translate(x, y), translateX(x), translateY(y)
크기 : scale(x, y), scaleX(x), scaleY(y)
회전 : rotate(degree(몇 도 회전))
기울임 : skew(x-deg, y-deg) 

- 3D 변환 함수
이동 : translate3d(x, y, z), translateZ(z)
크기 : scale3d(x, y, z), scale(z)
회전 : rotate3d(x, y, z), rotateX rotateY rotateZ
원근법 : perspective(n)


lab03
애니메이션 : 요소의 애니메이션 효과 설정
animation-name : @keyframes 규칙의 이름 지정(none)
animation-duration : 지속시간 설정(0s)
animation-timing-function : 타이밍함수(ease)
animation-delay : 대기 시간 조절(0s)
animation-iteration-count : 반복횟수(1)
animation-direction : 방향설정(normal)
animation-fill-mode : 전후상태(위치)설정(none)
animation-play-state : 재생과 정지 설정(running)

animation : 이름 지속시간 [타이밍함수, 대기시간, 반복횟수, 방향, ..]

timing - function & delay
timing - function = ease 기본값 , linear 균등 속도, ease-in 느렸다가 빠르게, ease-out 빨랐다가 느리게

direction

fill mode
animation: fill-mode 2s 2s;
이름 , 지속시간, 대기시간


step06 grid
2차원 (행, 열)에 관한 레이아웃을 제공하는 css 모듈
1. container
2. template-rows/columns(container)
    - repeat(3, 1fr) - 3칸 1fr 비율로
3. grid-column / row : 아이템의 위치
4. (item) grid-template-areas: 그리드 영역의 이름을 참조하여 템플릿을 생성 
5. row-gap, column-gap
6. grid-auto-rows/columns - 임시적 행의 크기를 정의
7. grid-auto-flow: row dense - 빈 공간을 채워줌
8. 라인의 이름을 지정
.container {
            grid-template-rows: 100px 100px;
            grid-template-columns: 1fr [line1] 1fr [line2] 1fr;
        }
9. align-content/justify-content : 그리드 컨텐츠의 수직/수평 축 정렬
10. self : 단일 아이템의 수직/수평축으로 정렬
11. order : item에 순서 정해줌(default = 0)