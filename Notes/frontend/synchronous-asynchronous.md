# 동기와 비동기

![](https://velog.velcdn.com/images/sju4486/post/3269eb24-625e-49be-bc19-4d6d449289fd/image.png)

![](https://velog.velcdn.com/images/sju4486/post/3c96a738-b0ad-4cd2-85ba-4ab151ec541b/image.png)

## 동기(Synchronous: 동시에 일어나는)

- 동기는 말 그대로 동시에 일어난다는 뜻이다. 요청과 그 결과가 동시에 일어난다는 약속이다.
- 바로 요청을 하면 시간이 얼마나 걸리던지 요청한 자리에서 결과가 주어져야 한다.
- 순서에 맞춰 진행되는 장점이 있지만, 여러 가지 요청을 동시에 처리할 수 없다.

## 비동기(Asynchronous: 동시에 일어나지 않는)

- 비동기는 동시에 일어나지 않는다를 의미한다. 요청과 결과가 동시에 일어나지 않을 거라는 약속이다.
- 하나의 요청에 따른 응답을 즉시 처리하지 않아도, 그 대기 시간동안 또 다른 요청에 대해 처리 가능한 방식이다.

## 상황에 따른 장점과 단점

- **동기방식**
  **장점:** 설계가 매우 간단하고 직관적이다.
  **단점:** 결과가 주어질 때까지 아무것도 못하고 대기해야 한다.

- **비동기방식**
  **장점:** 자원을 효율적으로 사용할 수 있다.
  **단점:** 동기보다 복잡하다.

## 동기방식의 예

1. `A`의 계좌는 10,000원을 뺄 생각을 하고 있다.

2. `A`의 계좌가 `B`의 계좌에 10,000원을 송금한다.

3. `B`의 계좌는 10,000원을 받았다는 걸 인지하고, `A`의 계좌에 10,000원을 받았다고 전송한다.

4. `A`, `B` 계좌 각각 차감과 증가가 동시에 발생한다

**계좌이체**같은 작업은 동기방식으로 처리해야 `A`에서 보냈는데 `B`에서 못 받는 상황이 없을 것이다.

## 비동기 방식의 예

1. `학생`은 시험문제를 푼다.

2. 시험문제를 모두 푼 `학생`은 `선생`에게 전송한다.

3. `선생`은 `학생`의 시험지를 채점한다.

4. 채점이 다 된 시험지를 `학생`에게 전송한다.

5. `학생`은 `선생`이 전송한 시험지를 받아 결과를 확인한다.

`학생`과 `선생`은 시험지라는 연결고리가 있지만 시험지에 행하는 행위(목적)는 서로 다르다.
`학생`은 시험지를 푸는 역할을 하고 선생은 시험지를 채점하는 역할을 한다.
**서로의 행위(목적)가 다르기 때문에 둘의 작업 처리 시간은 일치하지 않고, 일치하지 않아도 된다.**

> **💡 자바스크립트에는 아래와 같이 3가지 비동기 처리방식이 있다.**
>
> - 콜백 함수 사용
> - Promise
> - Promise를 활용한 async/await

> **💡 비동기의 주요 사례**
>
> - **DOM Element 의 이벤트 이벤트 핸들러 :** 마우스, 키보드 입력 (click, keydown 등), 페이지 로딩 (DOMContentLoaded 등)
> - **타이머 :** 타이머 API (setTimeout 등), 애니메이션 API (requestAnimationFrame)
> - **서버에 자원 요청 및 응답 :** fetch API, AJAX (XHR)

## 참고

- https://dev-coco.tistory.com/46
- https://velog.io/@slobber/%EB%8F%99%EA%B8%B0%EC%99%80-%EB%B9%84%EB%8F%99%EA%B8%B0%EC%9D%98-%EC%B0%A8%EC%9D%B4
- https://ynzu-dev.tistory.com/105
- https://tlsdnjs12.tistory.com/12