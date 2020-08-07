---
layout: post
title: "iOS 어트리뷰션의 미래: 모바일 측정 메서드 예측도"
author: "Gadi Eliashiv"
---
![cover](https://www.singular.net/wp-content/uploads/2020/07/090387631e1e1c4d5d9455e51753a0d2.png)

iOS 14는 모바일 마케팅 역사상 큰 영향으로 다가오고 있으며 많은 이들이 향후 어떤 일이 일어날 지 궁금해하고 있습니다.

Singular는 이미 일년 이상 준비해온 만큼 이 변화에 발빠르게 대응하고 있습니다. 우리는 2019년 6월에 20명 이하의 초기 회원들과 함께 모바일 어트리뷰션 프라이버시 연합(Mobile Attribution Privacy Coalition) 구성을 시작했고 현재는 천 명 이상의 멤버가 모였습니다([Slack 채널](https://join.slack.com/t/mapworkinggroup/shared_invite/zt-9vlvhtzn-bqUVQ1zn3o1UorDNIodvZg)에 참여하세요.) 우리는 핑거프린팅 지속 여부를 예측하고자 [ITP](https://webkit.org/blog/category/privacy/)를 모니터링하고 있으며 [SKAdNetwork](https://singularkorea.github.io/2020-06-30/what-is-skadnetwork)의 리버스 엔지니어링으로 공식 문서가 제공되기 전 동작 원리를 이해했습니다. 또한 [유익하고 실용적](https://singularkorea.github.io/2020-07-14/skan-skadnetwork-implementation)일 것으로 기대되는 [다양한 컨텐츠](https://singularkorea.github.io/2020-06-29/idfa-faq)와 [Github에 샘플 코드](https://www.singular.net/blog/skan-skadnetwork-implementation/) 역시 배포했습니다.

이제 Apple이 iOS 14에서의 IDFA 지원 중단을 발표한지 한달 이상이 지났지만 마케팅 측정에 미치는 영향에 대한 질문은 급격한 증가세를 지속하고 있습니다. 저희의 고객사와 예비 고객사들은 계속 어트리뷰션에서 가능한 결과에 대해 물어오고 계시므로 해당 시나리오가 일어날 가능성에 대한 저희 의견을 포함한 의사 결정 트리를 구축하여 가능한 솔루션과 시나리오를 설명하는 것이 좋겠다고 생각했습니다. 아래 이미지에서 각 시나리오에 대한 저희 예측을 볼 수 있습니다.

주의: 본 의사 결정 트리는 새로운 상황이 생기면 업데이트될 수 있으므로, 가능한 [원문](https://www.singular.net/blog/attribution-in-ios-14/)에서 업데이트된 사항을 확인하시기를 권장합니다.

![map](https://github.com/singularkorea/singularkorea.github.io/blob/master/assets/KR_iOS14Map.jpg?raw=true)


<hr>
[Singular 홈페이지에서 원문 보기](https://www.singular.net/blog/attribution-in-ios-14/)
