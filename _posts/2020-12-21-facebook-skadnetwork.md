---
layout: post
title: "SKAdNetwork, Facebook과 Singular: Facebook을 통한 iOS 어트리뷰션 지원 방법"
author: "Susan Kuo"
---
![cover](https://www.singular.net/wp-content/uploads/2020/12/Singular-and-facebook-for-SKAdNetwork.png)

Singular가 Facebook을 통한 iOS 14 앱 인스톨을 측정하고 어트리뷰트하는 방법에 대한 자세한 내용을 안내합니다.

모바일 앱 퍼블리셔와 마케터를 위한 iOS 어트리뷰션과 인스톨 후 인게이지먼트 측정에는 큰 변화가 발생해왔습니다. 좋은 소식은 결정론적 어트리뷰션은 계속 가능하다는 점입니다. 모바일 퍼포먼스 마케팅과 모바일 유저 획득(UA)은 여전히 유지될 것입니다. 또한 모바일 광고 퍼포먼스가 최소한으로 영향받도록 Facebook이 주도적인 역에 나선 것을 기쁘게 생각합니다.

공유할 부분이 많지만 간단하게 다음처럼 정리하겠습니다.

* Facebook은 SKAdNetwork와 iOS 14 지원을 위해 열심히 작업하고 있습니다.
* 광고주는 Singular SDK를 사용해서 전환 목표와 방법론을 유지하고 Facebook과 완전히 호환되도록 유지할 수 있습니다. Facebook SDK를 추가하지 **않아도** 됩니다.
* Facebook은 모든 파트너에서 전환 방법을 일관적으로 유지하도록 **SKAdNetwork 어트리뷰션 관리에 MMP를 사용**하기를 권장합니다.
* Singular는 **연동을 완료하고 정보 상호 운용이 가능하도록** Facebook과 긴밀히 협업하고 있습니다.
* 우리는 광고주가 앱 인스톨과 인스톨 후 이벤트를 **모바일 플랫폼들 사이**에서 균일하게 유지하도록 하는 프레임워크를 함께 개발하고 있습니다.
* Singular는 Facebook과 SKAdNetwork 인프라 스트럭쳐를 테스트했으며 추후에도 전체적인 가독성을 얻을 수 있도록 협업할 예정입니다.

## Facebook과 Singular의 현 상황은?

Facebook과 Singular는 iOS 14의 어트리뷰션과 전환 관리를 해결하기 위해 협업해 왔습니다. Facebook는 10월 29일 초기 가이드를 발표했고, Singular는 [SKAdNetwork 지원](https://singularkorea.github.io/2020-06-28/skadnetwork-support)을 발표한 최초의 모바일 측정 파트너(MMP)이죠.

이제 Facebook은 Singular의 SKAdNetwork 솔루션을 지원합니다. 이를 통해 광고주가 SKAdNetwork를 사용하는 Facebook 캠페인 측정과 최적화에 Singular SDK를 계속 사용할 수 있습니다. Facebook이 고객사가 설정한 Singular 전환 모델을 고객사의 Facebook 광고 어카운트에 사용할 수 있도록 하는 것이 이 연동 사항의 핵심으로 MMP가 SKAdNetwork에서 수행할 중요 역을 잘 보여줍니다.

앞으로 더 많은 작업이 진행되어야 합니다. [Facebook의 언급처럼](https://developers.facebook.com/blog/post/2020/10/29/preparing-our-partners-ios-14-latest-guidance-on-skadnetwork/), 앞으로 달성해야 할 사항이 많고 아직까지 작업이 진행 중이지만 조만간 완료될 예정입니다.  Apple이 iOS 14의 새로운 어트리뷰션 정책을 전체적으로 진행할 시점에 준비가 될 것으로 Facebook과 우리 양사 모두 예상합니다.

## SKAdNetwork와 MMP

모바일 측정 파트너가 SKAdNetwork 세계에서 수행할 역할에 대해 그동안 많은 이야기들이 오고 갔습니다.

우리는 Singular의 [iOS 14 어트리뷰션 솔루션](https://www.singular.net/skadnetwork/)이 SKAdNetwork를 간결하고 확장 가능한 형태로 만들고 더 나은 분석을 제공할 수 있으리라고 명확히 해왔습니다. 더욱 중요한 것은 Singular가 고객사가 SKAdNetwork가 특별히 취약한 부분으로부터 발생하는 새로운 프러드 근원지를 맞닥뜨리지 않도록 막는다는 점입니다.

Facebook 역시 MMP를 통해 iOS 14 측정과 분석을 일치하는 방법이 Facebook이 선호하는 모델이며 광고주에게 가장 좋은 선택지라고 말하고 있습니다. SKAdNetwork를 구현했지만 MMP와 연동하지 않은 플랫폼이 있다면 광고주가 호환되지 않는 데이터를 받고 크로스 플랫폼 측정이 분열되며 전환 방법론의 충돌을 야기할 위험이 있습니다.

이 점이 바로 Singular가 고객사를 위해 해결하고자 하는 중요한 부분입니다.

주목하여야 할 또 다른 중요 부분은 Singular가 최고의 선택인 것이 단순히 [모바일 어트리뷰션](https://www.singular.net/marketing-data/mobile-attribution/) 측면만이 아니라는 점입니다. [비용 집계](https://www.singular.net/marketing-data/cost-aggregation/)와 [마케팅 분석 단일화](https://www.singular.net/marketing-analytics/)를 위한 우리의 오랜 이력을 통해 고객사의 캠페인 데이터와 어트리뷰션 데이터 모두를 수집하고 연결할 수 있습니다. 이를 통해 더 정확한 ROAS와 코호트 리포팅이 가능하며 보다 풍부하고 세분화되며 믿을만한 측정이 가능합니다. 이 전반적이고 통합적 접근은 고객사가 가장 현명한 그로스 인사이트와 가장 정확한 데이터를 받도록 보장하며 가장 시급한 iOS 14와 SKAdNetwork의 제한 상황에서도 창의적인 최적화를 가능하게 합니다.

## 광고 파트너 간의 표준화

Facebook이 SKAdNetwork를 매우 중시하고 모바일 앱 퍼블리셔가 일반적인 전환 모델과 전체 광고 파트너 사이에 통용되는 방법론으로 사용할 수 있도록 전체 업계가 적용해야 하는 것으로 인식함이 자명합니다. SKAdNetwork 전환 목표를 사용한 측정 방법론을 통일하면 광고주가 Facebook SDK나 Singular SDK를 통해 마케팅 최적화와 측정을 할 수 있습니다.

또한 전환 모델을 표준화하면 쉽게 퍼포먼스와 목표 달성 상황을 비교 대조할 수 있습니다.

## Singular는 Facebook SKAdNetwork를 리포팅합니다.

Facebook이 모바일 유저 획득을 위한 주요 플랫폼인 만큼 Facebook은 광고주가 다른 여러 파트너를 사용해서 확장을 하는 사실도 이해하고 있습니다. 이에 따라 Facebook에 제공된 iOS 14 어트리뷰션은 현재와 마찬가지로 대시보드 및 데이터 흐름에서 다른 모든 데이터와 함께 표시됩니다.

## 앞으로 나아갈 길

앞서 언급한 대로, 아직 작업해야 할 것이 많이 남았습니다. 더 많은 테스트가 진행되고 있지만 우리가 기본적으로 준비되어 있고 Facebook이 근접하게 뒤따르고 있다고 말하는 것이 가장 맞는 표현일 것 같습니다. Singular는 iOS 14 SKAdNetwork 솔루션([Singular SKAN](https://singularkorea.github.io/2020-10-16/skadnetwork-ios-14-initial-partners-announcement))을 함께 하는 여러 초기 파트너를 발표했었고, 이제는 Facebook과 협업하고 있으며 전체 연동은 완전히 준비되지 않음을 안내할 수 있는 시점입니다.

Singular가 [LTV 예측](https://www.singular.net/blog/pltv-in-ios14-skadnetwork/)을 위해 작업하고 있는 것처럼, 여러 새로운 도구들을 포함해서 혁신적인 결과를 만들어낼 기회가 있습니다.

이러한 테스팅 옵션과 다음 스텝을 알고 싶은 고객사는 담당 고객 성공 팀과 상의해주세요.

Singular 고객사가 아닌 경우 SKAdNetwork 안내, 데모, 테스트 코드 및 SDK 액세스 권한을 위해 [이 링크](https://www.singular.net/lp/demo/)를 통해 연락해 주세요.

마케터와 광고 파트너: 2021년 초반부 예상 사항
Apple이 내년 중 빠른 시기에 SKAdNetwork로 완전히 전환할 것으로 예상되며, 실제로 1월 중에 발표되더라도 놀랍지 않습니다. 우리는, 또한 Facebook 역시 광고주가 캠페인의 중단을 겪지 않도록 보장하고 캠페인이 가능한 성공적일 수 있도록 돕기 위해 열심히 작업하고 있습니다.

이제 Singular의 SKAdNetwork 솔루션과 다음 리스트 외에도 더 많은 파트너가 협력하고 있습니다.

* Facebook
* Twitter
* Snap
* TikTok
* ironSource
* Liftoff
* Tapjoy
* Vungle
* 그 외 많은 파트너들

이 블로그나 귀사의 고객 성공팀을 통해 추후 이어지는 업데이트를 확인하세요.

<hr>
[Singular 홈페이지에서 원문 보기](https://www.singular.net/blog/facebook-skadnetwork/)
