# Promise와 Callback의 차이점

Promise와 Callback은 비동기 작업을 다룰 때 사용되는 두 가지 다른 접근 방식이다.

콜백 함수는 비동기 로직의 결과값을 처리하기 위해서 callback 안에서만 처리를 해야하고, 콜백 밖에서는 비동기에서 온 값을 알 수가 없다. 하지만, Promise를 사용하면 비동기에서 온 값이 프로미스 객체에 저장되기 때문에 코드 작성이 용이해진다.

## 가독성과 유지보수성

- **Promise** : `.then()` 및 `.catch()`와 같은 메서드 체인을 사용하여 비동기 작업의 흐름을 쉽게 이해할 수 있다.

- **Callback** : 콜백은 중첩된 형태로 나타날 수 있으며, 이로 인해 코드의 가독성이 떨어질 수 있다.

## 에러 처리

- **Promise** : `.catch()` 블록을 사용하여 에러 처리를 간단하게 수행할 수 있다.

- **Callback** : 콜백에서 에러 처리는 명시적으로 해주어야 하며, 예외를 던지거나 에러를 인수로 받아야 한다.

## 병렬 처리

- **Promise** : 모든 작업이 완료될 때까지 기다릴 수 있는 `Promise.all()`과 같은 메서드를 제공한다.

- **Callback** : 직접적으로 병렬 처리를 지원하지 않으며, 추가적인 코드 논리가 필요

## 취소와 타이밍 제어

- **Promise** : `.then()` 또는 `.catch()` 후에 `.finally()` 블록을 사용하여 작업이 성공 또는 실패와 관계없이 항상 실행될 코드를 작성할 수 있다. 또한 `Promise.race()`를 사용하여 가장 먼저 완료된 프로미스를 처리할 수 있다.

- **Callback** : 타이밍과 취소가 어렵다.

</br>
</br>

**Callback**은 JavaScript에서 오래된 비동기 처리 방법 중 하나이며, 여전히 사용되지만 가독성과 유지보수성을 높이고 복잡한 비동기 코드를 관리하기 위해 프로미스나 최근에는 **async/await**와 같은 새로운 비동기 패턴이 더 일반적으로 사용된다.

**콜백(callback) 예시**

```js
// 비동기 함수
function fetchData(callback) {
  setTimeout(function () {
    const data = "This is some data from the server";
    callback(data); // 콜백 함수 호출
  }, 1000);
}

// 비동기 함수 호출
fetchData(function (result) {
  console.log(result); // 콜백 함수로 전달된 데이터 출력
});
```

**프로미스(Promise) 예시**

```js
// 비동기 함수를 Promise로 래핑
function fetchData() {
  return new Promise(function (resolve, reject) {
    setTimeout(function () {
      const data = "This is some data from the server";
      resolve(data); // 성공 시 resolve 호출
    }, 1000);
  });
}

// Promise를 사용하여 비동기 작업 처리
fetchData()
  .then(function (result) {
    console.log(result); // 작업이 성공하면 데이터 출력
  })
  .catch(function (error) {
    console.error(error); // 작업이 실패하면 에러 출력
  });
```

## 참고

- https://klmhyeonwooo.tistory.com/48
- https://www.daleseo.com/js-async-callback
- https://www.daleseo.com/js-async-promise
