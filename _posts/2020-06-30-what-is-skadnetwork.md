---
layout: post
title: "SKAdNetwork 101: SKAdNetwork의 의미와 영향 범위"
author: "Yonatan Komornik"
---
![cover](https://www.singular.net/wp-content/uploads/2020/06/SKADnetwork-101-Blog-Banner-Singular-1.png)

지금으로부터 2년 이상을 거슬러간 2018년, Apple은 SKAdNetwork라는 새로운 개념과 API를 소개했습니다. 이 API는 개인 정보를 보호하는 방식으로 모바일 앱 인스톨 어트리뷰션을 가능하게 하는 것이었죠. 당시에는 많은 iOS의 모바일 어트리뷰션의 미래와 SKAdNetwork가 차지할 위치에 대한 많은 의문점이 대두되었습니다. 하지만 제한적인 특성과 도입해서 얻을 실제 이점이 없었기에 SKAdNetwork는 도입되지 않았고 모바일 어트리뷰션에도 변화가 일어나지 않았습니다.

그러나 Apple이 iOS의 앱 트래킹, AppTrackingTransparency 프레임워크의 선언 및 [Apple의 새로운 개인 정보 보호 가이드라인](https://www.singular.net/blog/ios14-idfa-limit-ad-tracking-skadnetwork-wwdc-privacy-update/)에 대한 업데이트를 발표하는 순간 모든 것이 달라졌습니다. 이 업데이트는 자연히 관련 업계가 대안책을 찾도록 했습니다. 동시에 대안책의 하나로 SKAdNetwork가 대두되었습니다.

Singular는 SKAdNetwork의 활용을 위해 [오랜 기간 준비](https://singularkorea.github.io/2020-06-28/skadnetwork-support)해 왔고, 이 것이 현실이 되는 동안 해당 내용을 배우고자 하는 많은 고객사와 파트너사로부터 수많은 질문을 받았습니다. 이에 대한 응답으로 본 포스팅으로부터 시작하여 SKAdNetwork의 동작과 제공하는 데이터 포인트, 마케팅 측정에 사용될 수 있는 방법에 대해 탐구하도록 하겠습니다. 본 포스팅에서는 보다 큰 관점을 다룰 예정으로, 보다 자세한 내용을 심도있게 안내할 다음 포스팅도 기대해주세요. 

## SKAdNetwork란 무엇이며 어떤 기능이 있나요?

SKAdNetwork는 개인 정보를 보호하는 방식의 모바일 인스톨 어트리뷰션을 가능하게 하는 프레임워크입니다. 이는 유저의 고유성을 침해하지 않고서도 앱 인스톨 캠페인(CPI)의 전환율을 측정할 수 있도록 목표하고 있습니다.

어떻게 이런 것이 가능한지 궁금하신가요? Apple 및 App Store 자체가 촉진자로 기능한다는 점이 핵심입니다. 모든 어트리뷰션 과정은 실제로 App Store에 의해 이뤄지고 Apple 서버에 의해 검증됩니다. 이후 유저 식별자(ID)와 임시적인 정보를 제외한 어트리뷰션 정보가 네트워크에 전달됩니다.

![SKAdnetwork flow](https://www.singular.net/wp-content/uploads/2020/06/IDFA_01-1-1024x747.png)

어떻게 동작하게 될까요? 실제로는 더 복잡하지만 최대한 단순하게 설명해보겠습니다.

광고가 클릭되고 Store가 열리면 퍼블리싱 앱과 네트워크는 네트워크, 퍼블리셔, 캠페인 ID 등과 같은 기본적인 정보를 전달합니다. App Store는 네트워크에게 전환 성공을 알려주죠. 이때 전환값과 함께 광고주 앱에 보고할 수 있는 추가 값이 첨부됩니다.

이 알림은 첫 실행으로부터 최소 24시간 이후에 전달되며 디바이스나 유저를 식별할 수 있는 모든 값이 제외됩니다. 또한 App Store가 해당 과정을 진행하므로 광고주 앱은 원래의 광고와 퍼블리셔에 대해 알 수가 없습니다. 같은 방식으로 네트워크는 인스톨이 발생했다는 증명서를 받습니다. 물론 특정 유저를 해당 인스톨과 연결지을 수 없으므로 개인 정보가 보호되는 것입니다.

## SKAdNetwork 인스톨 어트리뷰션 사용으로 무엇을 얻을 수 있나요?

우선, 무엇을 얻을 수 있는지부터 살펴보겠습니다.

1. 모바일 앱에 게재된 광고에 대한 클릭스루 어트리뷰션
2. 퍼블리셔에게 투명하게 제공될 수 있는 퍼블리싱 앱의 퍼블리셔 ID
3. 100개 값으로만 제한된 캠페인 ID - 캠페인 ID 뿐만 아니라 캠페인, 크리에이티브 및 플레이스먼트처럼 퍼블리셔 이외의 다른 캠페인 정보를 포함할 수 있습니다.
4. SKAdNetwork를 통해 첫 번째 인스톨인지 재 다운로드인지 확인할 수 잇습니다.
5. 0부터 63까지의 숫자를 사용할 수 있는 전환값 - 이 값은 전환이 일어난 후 광고주가 설정할 수 있으며 기본적은 포스트 인스톨 트래킹이 가능해집니다. (예: 유저가 유입된 첫째날 달성한 최고 레벨 표시) 유저 퀄리티에 대한 평가를 일정 정도 가능하도록 지원되는 값입니다.
6. Apple의 암호화된 어트리뷰션 및 파라미터 검증, 초기화되지 않음 - 이 값이 중요한 이유는 누구라도 유저 개인 정보를 보호하면서도 인스톨이 이미 발생했는지 확인할 수 있기 때문입니다.
7. 정확하고 가장 프러드로부터 안전한 어트리뷰션

이제, 무엇을 얻을 수 없는지도 살펴보겠습니다.

1. 뷰스루 어트리뷰션은 지원되지 않으며 광고는 클릭으로부터만 어트리뷰션 과정이 시작됩니다.
2. 브라우저, 이메일 캠페인 등 네이티브 광고가 아닌 다른 미디어의 클릭스루 어트리뷰션이 지원되지 않습니다.
3. 실시간 데이터 - 최소 24시간 최대 48시간 이후에 네트워크에 알림이 전달됩니다. 또한 전환 값에 대한 이후의 업데이트는 알림을 지연시킵니다. (다시 말해 앱이 열린 시점이나 전환 값에 대한 최신 업데이트로부터 24시간에서 48시간이 지난 이후 알림이 전송됩니다.) 이를 통해 Apple은 유저를 앱 활동과 연결지으려는 시도를 무효화합니다.
4. 유저 레벨 데이터 - 알림은 유저 ID를 포함하지 않습니다.
5. 작은 캠페인이나 퍼블리셔의 데이터 - Apple은 동일 퍼블래셔 앱과 캠페인 ID에서 일정 이상의 전환이 발생한 이후에만 알림을 전달합니다. 관련하여 아직까지는 어떤 임계치를 넘어야 하는지, 또한 실제로 어떻게 계산되는지에 대한 세부 정보가 확인되지 않았습니다. 
6. 디퍼드 딥링크와 긴 기간의 코호트/LTV와 같은 고급 어트리뷰션 서비스가 지원되지 않습니다.

## 광고주가 SKAdNetwork를 최대한 활용하는 방안은?

광고주로서 SKAdNetwork라는 Apple의 새로운 동작 원리를 가장 잘 활용하는 방법이 뭔지 궁금하실 겁니다. 저희가 제공하는 필수 아이템에 대한 간단한 체크리스트를 활용해 보세요.

1. 미디어 파트너사가 SKAdNetwork API와 올바르게 연동되어 SKAdNetwork를 지원하는지 - 모든 iOS 버전이 그래왔듯 유저들이 iOS 14로 대부분 업데이트할 것으로 예상되므로 대부분의 파트너사가 이에 뒤쳐지길 원하지는 않을 겁니다.
2. 또한 암호로 서명된 인스톨 알림을 모든 미디어 파트너로부터 직접, 혹은 관련 업체와 함께 수집해서 확인하여 문제나 잘못된 사용을 식별해야 합니다.
이 작업의 목표는 모든 사람이 진실을 말하도록 하는 것입니다. 물론 모두가 진실하다고 믿고 싶지만, 직접 리포팅하는 숫자를 신뢰하는 것이 항상 안전하지는 않음을 익히 아실 겁니다.
3. 다음은 모든 것을 이해하기 위한 분석 및 리포팅입니다. SKAdNetwork API는 제한된 값과 ID 세트를 제공해서 이 작업이 어렵긴 하지만 불가능하지는 않습니다. 스마트 인코딩으로 Apple의 API를 통해 전달할 수 있는 정보의 양을 최대화할 수 있습니다.
예를 들어 캠페인 ID는 유용한 값이지만, 캠페인 ID가 할당되는 값이 여러 채널에서 일관적이고 리포팅 가능한 방식이 되도록 현명하게 선택해야 합니다.   
4. 또한 현명하게 선택한 파라미터를 통해 최적화와 포스트 인스톨 측정에도 차이를 만들 수 있습니다. 전환 정보를 위해 값은 6비트로 표시되는 64개의 제한적인 숫자지만 현명하게 사용되는 경우 많은 정보를 인코딩할 수 있습니다. 예를 들어 첫날 활동을 기준으로 유저를 분류해서 추후 그룹화하고 성능 평가를 할 수 있는 세그먼트를 만들 수 있습니다.
전담 엔지니어링 작업 없이도 이러한 값을 자동으로 할당하고 변형할 수 있는 방법이 필요하므로 아마 이를 관리하고 보고서에 연결할 수 있는 도구가 필요할 겁니다.

측정 파트너는 미디어 파트너 연동부터 시작해서 검증, 분석과 리포팅의 중심적인 역할까지 이런 전체 과정을 잘 지원할 수 있는 위치에 있습니다. Singular는 [이미 SKAdNetwork 연동 솔루션을 발표](https://singularkorea.github.io/2020-06-28/skadnetwork-support)했으며, 위 모든 체크리스트가 해당 솔루션의 기반이 될 것입니다. 다른 이들도 저희와 같은 길을 따르길 기대합니다.

이러한 변화가 Singular 제품에서는 자연스러운 진보라고 생각합니다. Singular의 독보적인 위치와 미디어 파트너 사와의 독보적인 연동을 통해 새로운 API를 최대한 활용하여 고객사가 원활하고 매끄럽게 새로운 시대로 전환될 수 있습니다. 고객이 사용 가능한 모든 도구를 활용할 수 있도록 Singular는 끊임없이 진보할 것입니다.

<hr>
[Singular 홈페이지에서 원문 보기](https://www.singular.net/blog/what-is-skadnetwork/)
