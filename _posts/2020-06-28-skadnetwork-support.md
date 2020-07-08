---
layout: post
title: "Singular는 IDFA를 대체하는 SKAdNetwork를 마켓 최초로 지원합니다."
author: "Gadi Eliashiv"
---

![cover](https://www.singular.net/wp-content/uploads/2020/06/Hero_General_1980x930.png)

지난 몇 년 동안 Singular는 Apple이 [IDFA](https://www.singular.net/blog/mobile-tutorial-series-idfa-apple-identifier-advertisers/) 기능의 지원을 중단할 것이라고 예측하고 이를 대비하여 준비해왔습니다. 그리고 저희의 예측은 결국 [올해 9월 iOS 14의 공식 출시](https://www.singular.net/blog/ios14-idfa-limit-ad-tracking-skadnetwork-wwdc-privacy-update/)와 동시에 현실로 나타났습니다.

IDFA 기능이 완전히 없어지는 것은 아니지만 옵트인 메커니즘이 추가되면서 IDFA 기능은 사실상 쓸모가 없어집니다. 이로 인해 많은 개발자와 회사들은 큰 고민에 빠질 텐데요.

이번 변화는 모바일 측정 파트너(MMP)들의 역할을 재정의하는 만큼 싱귤러에서도 많은 생각을 했습니다. 

MMP는 모바일 마케팅에 공정한 데이터를 측정하고자 디자인된 플랫폼입니다. 이제까지 MMP들은 iOS는 광고 식별자(Apple의 IDFA, Android는 Google의 ADID 등)에 의존하며 MMP 역할을 해왔습니다. 하지만 앞으로 MMP들은 마케터들이 캠페인을 지속적으로 최적화하는 동시에 유저들은 개인 정보가 보호되어야 하므로, MMP는 광고 캠페인 데이터를 측정할 수 있는 새로운 방법을 찾는 큰 도전 상황에 놓일 겁니다. 

**그래서 Singular는 SKAdNetwork가 널리 사용되고 마케터들에게는 IDFA 시대처럼 사용될 수 있도록 업계에 기여할 수 있게 되어 정말 기쁩니다!**

WWDC에서 발표된 내용은 마케터들에게 큰 충격이었습니다. 향후 캠페인 최적화를 어떻게 해야 할지 궁금해하실 분들이 많을 텐데요. 앞으로 최적화는 여전히 가능하고 더불어 지금처럼 성과 분석도 지속 가능합니다.

(더 자세한 내용은 [다음 포스트](https://singularkorea.github.io/2020-06-29/idfa-faq)를 확인해 주세요!)

## SKAdNetwork는 무엇인가요?

SKAdNetwork는 iOS에서 지원되는 라이브러리이며 개인 정보가 보호되어 마케터들은 이를 통해 마케팅 데이터 수집이 가능합니다.

Apple은 SKAdNetwork 개발에 많은 시간을 투자했습니다. 그리고 Singular도 SKAdNework를 지원할 수 있도록 [일 년 넘게 많은 노력](https://www.singular.net/blog/mobile-marketing-measurement-privacy-idfa/)을 해왔는데요. 다행히 iOS 14에서는 SKAdNetwork이 보다 훨씬 유용하게 개선되었습니다. 마치 열심히 SKAdNetwork의 장단점에 대해 연구한 Singular와 [Mobile Attribution Privacy Coalition](https://joinmap.org/) 회원들의 소리를 들은 것 같습니다.

**SKAdNetwork의 가장 중요한 포인트는 iOS 운영 시스템이 마케팅 어트리뷰션에서의 핵심 역할을 하게 된다는 점입니다.**

SKAdNetwork가 앱 내에서 활성화가 되어 있으면 광고 클릭 후 App Store로 넘어갈 때 App Store에서 어트리뷰션 파라미터를 받게 됩니다. 그 후에 앱이 다운로드 되면 iOS에서 어트리뷰션 파라미터가 포함된 포스트백을 발송합니다. (인스톨 이후에 수집된 데이터도 발송될 가능성이 있습니다. 이 부분은 다음에 자세히 설명하도록 하겠습니다.)

이 점은 어떻게 보면 Google Play 레퍼러의 동작원리와 비슷하다고 볼 수 있습니다. 하지만 SKAdNetwork는 개인 정보 보호가 보장됩니다. 그 이유는 어트리뷰션 파라미터에 디바이스 ID 혹은 유저를 식별할 수 있는 정보가 포함되면 안되기 때문이죠. 추가로 인스톨 포스트백은 인스톨된 앱이 아닌 iOS 시스템에서 자체적으로 발송되므로 광고주들은 앱이 인스톨 되었는지까지는 알 수 있지만 디바이스와 관련된 상세 정보는 알 수 없습니다.

SKAdNetwork 1.0은 이미 2년 전부터 출시되었으나 지원되는 기능이 굉장히 제한적이었고 인스톨 이후의 측정도 불가능했기 때문에 캠페인 최적화에는 거의 소용이 없었습니다.

다행히 SKAdNetwork 2.0에는 “퍼블리셔-앱” 레벨에서 데이터 측정이 될 수 있도록 개선되었습니다. 다시 말해 마케터들은 어떤 퍼블리셔에서 인스톨이 발생했는지 확인할 수 있게 된 것이죠. 이는 MMP 입장에서도 마케터들에게 퍼블리셔 레벨의 인사이트를 제공할 수 있어 매우 중요한 업데이트라고 생각합니다. 또한 updateConversionValue 및 registerAppForAdNetworkAttribution 메서드를 추가함으로써 포스트 인스톨 트래킹도 부분적으로 지원이 가능해졌습니다.

전반적인 플로우를 보실까요?
![SKAdNetwork flow](https://www.singular.net/wp-content/uploads/2020/06/IDFA_01-1-1024x747.png)

## 마케터들에게는 어떤 의미가 있을까요?

현재 마케터들은 주로 두 가지 주요 소스에서 캠페인 데이터를 확인하고 있습니다:

MMP: 인스톨 및 포스트 인스톨의 코호트 매트릭스
광고 네트워크: 임프레션, 클릭, 비디오 뷰, 비용 소진 관련 매트릭스

Singular는 위 두 가지 종류의 데이터를 통합하고 마케터가 다양한 깊이에서 데이터를 확인하실 수 있도록 인사이트를 제공하고 있습니다. 이러한 인사이트를 통해 마케터는 UA 캠페인 및 리타게팅 캠페인 최적화가 가능하고 더불어 빠르게 다양한 매체의 테스팅도 가능합니다.

**iOS 14에서는 모든 것이 바뀝니다.**

앱 어트리뷰션의 데이터 플로우부터 변합니다. 기존에는 앱 자체에서 포스트백을 Singular에 발송했다면 앞으로는 Apple에서 전환을 발생시킨 매체에게 인스톨 포스트백을 직접 전송하게 됩니다. 해당 포스트백에는 Apple에서 암호화하여 서명한 인스톨의 정보가 포함되어 있고 이는 Apple의 공개 키를 통해 입증할 수 있습니다.

iOS 14의 가장 큰 도전은 인스톨 이후의 활동에 대한 측정입니다. SKAdNetwork는 앱에 포스트 인스톨에 대한 전환 데이터를 발송할 수 있는 기능을 지원하지만 한계가 있습니다. (자세한 내용은 [다음 포스트](https://singularkorea.github.io/2020-06-29/idfa-faq)에서 이야기하겠습니다.)

그러나 SKAdNetwork의 장점도 있습니다. Apple이 앱 인스톨을 측정하는 만큼 광고 프러드도 급격히 줄어들 것으로 보입니다.

이 모든 것들은 마케터에게 큰 변화를 줄 것입니다. 기존에는 MMP가 모든 데이터를 수집했다면 앞으로는 iOS 광고주가 직접 각각 매체로부터 모든 인스틀 포스트백과 포스트 인스톨 포스트백을 수집해야 합니다. 여기서 끝이 아닙니다. 광고주들은 이 모든 포스트백을 직접 입증하고 저장한 후 어트리뷰션 파라미터들을 읽기 쉬운 데이터로 변환하고 캠페인의 소진 비용과 연동해서 ROAS 등의 값을 직접 계산해야 합니다. 특히 이 모든 절차는 실시간으로 진행될수록 효율을 높일 수 있다는 점이 중요합니다.

Singular는 이 점에서 여러분둘에게 도움을 드릴 수 있습니다.


## Singular의 솔루션: 더 심플하고 확장 가능한 SKAdNetwork
![solution](https://www.singular.net/wp-content/uploads/2020/06/IDFA_02-1-1024x607.png)

Singular의 장점은 데이터 집계 및 통합 부분의 선두 주자라는 것입니다. 저희는 그 누구보다 많은 소스에서 다양한 방법으로 데이터를 수집해 왔고, 수집된 데이터를 표준화한 후 통합해서 광고주에게 최종 데이터를 제공합니다. 이러한 기능은 Singular의 MMP 어트리뷰션 상품과 완벽하게 호환되어 많은 고객사들이 만족하며 사용하는 핵심 포인트로 손꼽힙니다. 이것이 수많은 유명 브랜드들이 Singular를 선택하는 동기이자 Singular가 지난 2년간 급속도로 성장할 수 있었던 이유입니다.

**Singular의 주요 장점은 SKAdNetwork이 도입되면서 더욱 빛을 발합니다.**

Singular는 태생적으로 데이터 집계 기능이 가장 독보적인 장점이었지만, SKAdNetwork의 변화와 함께 광고주들께 더 많은 편리함을 제공할 수 있습니다. Singular는 향후 Apple에서 발송되는 모든 포스트백을 매체로부터 수집하여 입증하고 중복을 제거한 후 분석하여 광고 비용과 연결해 ROI를 계산하여 리포트할 예정입니다.

이 것이 끝이 아닙니다. Singular는 추후 퍼블리셔 레벨로 세분화하여 마케팅 리포팅 기능을 제공할 예정입니다.

물론 아래 기능들을 포함한 기존 Singular 스택의 MMP 역량 부분에 더해 SKAdNetwork 스택 부분에 있어 긴밀한 협업이 필요합니다: 

iOS 핑거프린팅 (모든 Apple 업데이트를 준수하도록 합니다.)
iOS 딥링크 서포트
iOS 디퍼드 딥링크 서포트
Android 어트리뷰션 (Android는 여전히 중요 고려 사항입니다.)
웹 및 크로스 디바이스 어트리뷰션 (점차 중요성이 높아지고 있습니다.)
비용 및 ROAS 리포팅 (마케팅 최적화에 필수입니다.)
SKAdNetwork는 앞으로도 계속 새로운 도전 사항과 어려움을 가져올 겁니다. 하지만 Singular는 여러분과 함께 이러한 어려움을 같이 해결해 나갈 수 있도록 도와드리겠습니다.

또한 여러분이 직무를 수행할 수 있도록 돕겠습니다. 물론 개인 정보를 보호하는 방향으로요.

PST 6월 30일 화요일에 영어 웨비나 형식으로 마케터를 대상으로 IDFA와 iOS 14에 대해 알아보는 시간을 갖습니다. [Singular가 준비한 프리젠테이션과 Q&A에 참여하세요](https://singular.zoom.us/webinar/register/3815930587328/WN_RUeiSwckQvurSlRk-Hjukg)!


<hr>
[Singular 홈페이지에서 원문 보기](https://www.singular.net/blog/skadnetwork-support/)
