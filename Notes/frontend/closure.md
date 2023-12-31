# 클로저(Closure)

함수와 함수가 선언된 어휘적 환경의 조합입니다.(MDN 정의) 또한 **함수가 속한 렉시컬스코프를 기억하여 함수가 렉시컬 스코프 밖에서 실행될 때도 그 스코프에 접근할 수 있게 하는 기능** 을 말합니다.

```
function outer() {
  var outerVar = "I am from outer";

  function inner() {
    console.log(outerVar); // 클로저: inner 함수가 outer 함수의 변수에 접근
  }

  return inner;
}

var closureFunc = outer(); // outer 함수 실행 후 inner 함수 반환
closureFunc(); // "I am from outer" 출력
```

여기서 GC(GarbageCollector)가 `outer()` 의 참조를 없앨 것 같지만 내부함수인 `inner()` 가 해당 스코프의 변수인 a를 참조하고 있기 때문에 없애지 않습니다. 따라서 스코프 외부에서 `inner()` 가 실행되도 해당 스코프를 기억하기 때문에 2를 출력하게 됩니다. 즉, 여기서 클로저는 `inner()` 가 되며 `func` 에 담겨 밖에서도 실행되고 렉시컬 스코프를 기억합니다.

> 위의 코드와 같은 방식으로 자바스크립트에는 없는 **캡슐화라는 개념을 구현**할 수 있고 **정보 은닉**과 **캡슐화**가 가져다주는 이점들을 얻을 수 있습니다.

### 💁‍♂️ 정리

클로저는 함수가 다른 함수 내부에서 정의되고, 외부 함수의 변수를 참조할 때 발생합니다. 이때, 외부 함수의 변수는 외부 함수가 종료된 후에도 접근 가능한 상태를 유지하게 됩니다. **클로저는 이러한 변수와 함수의 조합을 통해 외부 변수의 보호, 데이터 은폐, 비동기 작업 처리, 콜백 함수 등 다양한 상황에서 사용됩니다.** 이것은 함수와 그가 참조하는 외부 스코프를 함께 '닫아두는' 현상으로, 렉시컬 스코프와 밀접한 관련이 있습니다.

#### ⚙️ 렉시컬스코프

- **렉시컬 스코프는 함수를 어디서 호출하는지가 아니라 어디에 선언하였는지에 따라 결정됩니다.** 자바스크립트는 렉시컬 스코프를 따르므로 함수를 선언한 시점에 상위 스코프가 결정됩니다. **함수를 어디에서 호출하였는지는 스코프 결정에 아무런 의미를 주지 않습니다.**

#### ⚙️ GarbageCollector

- 메모리에 할당된 값이 더는 필요하지 않다고 판단될때 메모리를 해제시키는 과정을 가비지 컬렉션이라고 부르며 이 역할을 가비지 컬렉터가 맡고 있습니다. 가비지 컬렉터가 ‘필요없다’라고 판단하는 기준은 더 이상 '객체에 닿을 수 없을 때'를 말합니다. 닿는다는 roots(전역 변수)를 기준으로 참조, 또는 참조의 참조의… 참조가 되는 객체들입니다. 이 알고리즘을 mark and sweep이라고 부르는데 가비지 컬렉터는 ‘root에서 닿을 수 있는’ 객체들의 reachable을 true로 표시하고, false인 객체들은 메모리에서 해제시킵니다.

## 참고

- https://developer.mozilla.org/ko/docs/Web/JavaScript/Closures
- https://github.com/Esoolgnah/Frontend-Interview-Questions
