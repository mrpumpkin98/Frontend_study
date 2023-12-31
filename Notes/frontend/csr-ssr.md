# CSR과 SSR

## CSR(Client Side Rendering)

> 클라이언트 즉, 사용자 측에서 렌더링하는 방식

**`장점`**

- 초기 로딩 후 사용자의 요청에 따라 **필요한 부분만 업데이트**되므로 **동작 속도가 빠르다.**
- UI에 있어 사용자에게 더 나은 경험을 제공한다.

**`단점`**

- 사용자가 **첫 화면을 보기까지 시간이 오래 걸릴 수 있다.**
- HTML문서가 비어 있기 때문에 SEO에 있어 좋지 않다.

## SSR(Server Side Rendering)

> 서버에서 렌더링이 일어나는 방식이다.
> 초기 웹 사이트들이 주로 갖는 형태이지만 현재까지도 사용되는 기술이다.

**`장점`**

- 초기 페이지 **로딩이 빠르다.**
- **효율적인 SEO(Search Engine Optimization)** 이 가능하다.

**`단점`**

- **매번 새로 고침이 발생**하므로 UI 측면에서 품질 저하가 발생한다.
- **서버에 과부하**가 걸릴 수 있다.
- 사용자가 실제로 웹사이트를 동작(Interaction)하는 데까지 걸리는 시간이 증가할 수 있다.
