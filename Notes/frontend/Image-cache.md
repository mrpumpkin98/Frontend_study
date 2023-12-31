# 이미지 캐싱

다운로드된 **이미지를 캐시(메모리 or 디스크)** 에 저장해두었다가 불러오는 방식으로,
한 번 다운받은 이미지는 별도의 리소스를 소모할 필요 없이 빠르게 가져와서 보여줄 수 있다.

## ✅ 주요 이점

- **성능 향상 :** 이미지 캐싱을 사용하면 이미지를 다시 다운로드할 필요가 없으므로 웹 페이지나 애플리케이션의 로딩 시간이 단축된다. 이로 인해 사용자 경험이 향상된다.

- **대역폭 절약 :** 이미지를 캐시하면 이미지를 다운로드할 때 필요한 대역폭을 절약할 수 있다. 특히 모바일 장치에서는 대역폭을 절약하면 사용자의 데이터 비용을 줄일 수 있다.

- **서버 부하 감소 :** 이미지를 로컬에 캐시하면 서버에 대한 요청이 감소하므로 서버의 부하가 감소한다.

- **오프라인 사용 :** 이미지가 로컬에 캐시되어 있으면 사용자가 오프라인 상태일 때에도 해당 이미지를 볼 수 있다.

- **캐시 관리 :** 이미지 캐싱은 캐시를 관리하고 만료된 이미지를 자동으로 업데이트하는 기능을 제공한다.

이미지 캐싱은 웹 브라우저, 모바일 앱 및 웹 서버에서 모두 사용될 수 있으며, **CDN(Content Delivery Network)** 와 같은 서비스를 통해 이미지를 효율적으로 캐시하는 방법도 있다. 캐시 전략은 애플리케이션의 요구 사항 및 성능 목표에 따라 다양하게 구성될 수 있다.

> **💡 CDN이란**
>
> 콘텐츠 전송 네트워크(CDN)는 데이터 사용량이 많은 애플리케이션의 웹 페이지 로드 속도를 높이는 상호 연결된 서버 네트워크다. CDN은 콘텐츠 전송 네트워크 또는 콘텐츠 배포 네트워크를 의미할 수 있다. 사용자가 웹 사이트를 방문할 때 해당 웹 사이트 서버의 데이터는 사용자의 컴퓨터에 도달하기 위해 인터넷을 통해 이동해야 한다. 사용자가 해당 서버에서 멀리 떨어져 있는 경우 동영상 또는 웹 사이트 이미지와 같은 대용량 파일을 로드하는 데 시간이 오래 걸린다. 대신 웹 사이트 콘텐츠는 지리적으로 사용자와 가까운
> CDN 서버에 저장되며 컴퓨터에 훨씬 빨리 도달한다.

## ✅ 브라우저의 캐싱

웹페이지에 접속한 사용자가 웹페이지를 로드할 때, 브라우저는 해당 웹 페이지를 표시하려고 많은 데이터를 요청하고 받는다. 이런 페이지 로드 시간을 줄이기 위해, **브라우저는 웹페이지에 필요한 콘텐츠를 캐싱해 사본을 사용자가 접속중인 기기의 하드 드라이브에 저장**한다. 이렇게 하면 다음번에 사용자가 같은 페이지에 접속했을 때, 필요한 대부분의 콘텐츠가 이미 **로컬에 저장되어 있기에 페이지가 훨씬 더 빠르게 로드된다. 더불어 서버에 요청하는 데이터양이 줄어 네트워크 트래픽도 줄어든다.**

> **💡 브라우저 캐시를 지우면?**
>
> 브라우저 캐시가 지워지면 사용자가 페이지를 처음 방문한 것처럼 로드되는 모든 웹 페이지가 로드된다. 처음에 잘못 로드된 항목이 캐시된 경우 캐시를 지우면 해당 항목이 올바르게 로드될 수 있다. 그러나 브라우저 캐시를 지우면 페이지 로드 시간이 일시적으로 느려질 수도 있다.

## ✅ CDN 캐싱

CDN, 즉 콘텐츠 전송 네트워크는 원본 서버보다 최종 사용자에게 더 가까운 프록시 서버에 콘텐츠(예: 이미지, 비디오, 웹 페이지)를 캐시한다.(프록시 서버는 클라이언트로부터 요청을 받아 다른 서버로 전달하는 서버)서버가 요청을 하는 사용자와 더 가까우므로 CDN은 콘텐츠를 더 빠르게 전달할 수 있다.

![](https://velog.velcdn.com/images/sju4486/post/ca7b7205-424c-4975-8a0a-9f7830a6bba4/image.png)

## 참고

- https://aws.amazon.com/ko/what-is/cdn
- https://www.cloudflare.com/ko-kr/learning/cdn/what-is-caching
