---
layout: post
title: "Apple의 IDFA 선물: SKAdNetwork 준비 시간 연장"
author: "Gadi Eliashiv"
---
![cover](https://www.singular.net/wp-content/uploads/2020/09/iOS-14-delay-announcement-blog-banner.png)

대부분의 마케팅 관계자들이 이미 들은 대로 Apple이 iOS 14에 도입하기로 예고한 개인 정보 측정의 구현 일정을 연장했습니다. 저희도 iOS 14 베타 7 버전에서 IDFA가 사용 가능하다는 사실을 확인했습니다. 정말 좋은 소식입니다.

저희가 공식적으로 [SKAdNetwork를 마켓 최초로 지원](https://singularkorea.github.io/2020-06-28/skadnetwork-support)한다고 발표하고 [활발하게 이를 대변](https://singularkorea.github.io/2020-07-06/skadnetwork-code)해왔지만, 현실적으로 대다수의 모바일 퍼블리셔와 마케터가 준비되지 않은 것이 사실입니다. 그리고 Facebook의 사례처럼 IDFA를 앱 별로 옵트인하는 방향으로의 전환은 큰 영향을 미칠 수밖에 없죠.

따라서 준비할 시간이 늘어났다는 사실이 참 다행입니다.

하지만 Apple이 개인 정보 보호에 대해 100% 공언한 사실을 간과해서는 안됩니다. 다음 문장에서 일정 지연에 대한 공식 [발표](https://developer.apple.com/news/?id=hx9s63c5%27)를 확인해보시죠.

> "다른 회사간 앱이나 웹사이트 간에 유저를 추적하거나 디바이스의 광고 ID에 접근하려면 앱은 유저 승인을 얻어야 합니다. **우리는 유저가 앱에서 추적의 여부를 허용할 수 있도록 보장하기 위해 최선을 다하고 있습니다.** 개발자가 이에 필요한 변경을 진행할 수 있도록, 내년 초부터 앱에서의 유저 추적 승인을 시작할 예정입니다. App Store 리뷰 가이드라인 업데이트 등의 더 많은 정보는 이번 가을에 안내됩니다."

> "Apps will be required to receive user permission to track users across apps or websites owned by other companies, or to access the device’s advertising identifier. We are committed to ensuring users can choose whether or not they allow an app to track them. To give developers time to make necessary changes, apps will be required to obtain permission to track users starting early next year. More information, including an update to the App Store Review Guidelines, will follow this fall."

이 상황 하에서 우리는 SKAdNetwork에 전념하고 있습니다. 하지만 일반적은 모바일 마케터와 우리 고객사에게 알려드리고 싶은 점은 SKAdNetwork에 대한 전념이 단순히 이것만이 보장된 방법이거나 이외의 대안이 없기 때문만은 아닙니다. 우리가 [Singular SKAdNetwork 솔루션](https://singularkorea.github.io/2020-07-14/skan-skadnetwork-implementation)을 구축해 갈수록 SKAdNetwork를 통해 모바일 마케터가 효율적으로 대규모 마케팅 캠페인을 효과적으로 확장하고 최적화할 수 있다고 확신하게 되었기 때문입니다.

다시 말해 ROAS, LTV 예측 등 마케팅 실행을 위해 알아야 할 것들에 대한 이야기입니다. 물론 유저 레벨과 크리에이티브에 대한 세부 정보는 제외됩니다.

저희가 마켓에 드릴 조언은 분명합니다. 미리 준비하세요.

연장된 시간을 준비에 사용하세요.

SKAdNetwork는 여전히 유효합니다. IDFA는 여전히 (대부분) 사라지고 있습니다. Apple이 약 다섯 달 가량의 선물을 주긴 했지만 이 시간을 어떻게 사용해야 할까요? 우리의 조언은 (Singular의 도움 하에) 이를 구현하고, 테스트하는 것입니다. IDFA 옵트인을 테스트하고 ROAS 측정을 테스트하거나 LTV 및 예측 LTV 측정을 테스트해서 마케팅 투자를 안내할 수 있습니다. 코호트 및 SKAdNetwork가 전달하는 인스톨 이후의 포스트 인스톨 컨버전을 위한 6비트 숫자의 각기 다른 사용법 역시 테스트할 수 있습니다.

가장 좋은 점은 이제 SKAdNetwork 테스트를 iOS 13에서의 어트리뷰션과 마케팅 측정과 함께 테스트해볼 수 있다는 것입니다.

**이러한 병렬 테스트를 바로 시작하는 것이 얼마나 중요한지에 대해 아무리 강조해도 지나치지 않습니다.**

Apple의 원래 계획에 따르면 이전 데이터와 iOS 14 데이터를 함께 받아들여야 했었고, iOS 14 데이터는 아직 iOS 14로 업그레이드 하지 않은 데이터와 섞여 있었을 겁니다. SKAdNetwork 측정에 대해 확인해보고 정확성을 비교할 수도 없었을 테죠. 또한 SKAdNetwork 포스트 인스톨 컨버전 전략을 수정하고 전통적인 IDFA 측정과 비교할 방법도 없었을 겁니다.

주의할 점은 이러한 세태에 즉각 합류하지 않는다면 이러한 기회를 잃을 것이라는 것입니다. 즉, SKAdNetwork가 온전히 구현되고 Apple이 iOS 14에서 계획했던 모든 개인 정보 측정을 강행하는 시점이 다가오면 이에 대응할 방법이 없습니다.

지금의 기회는 계획하고 구현하고 테스트하고 최적화해서 실제로 예고된 현실이 다가왔을 때 모바일 유저 확보를 수익성 있게 대규모로 수행할 수 있다는 확신을 다져두는 것입니다. 이를 통해 SKAdetwork 기반의 마케팅 측정 모델이 이미 검증을 마쳤고 신뢰할 수 있음을 자신할 수 있게 됩니다.

**Singular는 추후 다섯 달간 우리 고객사와 함께 IDFA 기반의 마케팅 측정과 SKAdNetwork 마케팅 측정을 테스트하면서 모바일 성장에 필요한 데이터와 인사이트를 얻을 수 있도록 도울 것입니다.**

우리는 여러 파트너와 함께 SKAdNetwork 조건과 방법론의 표준화를 진행하고 있습니다. 또한 생태계 내의 모든 이들이 준비될 수 있도록 돕고 있습니다. 이번 지연은 여러분과 다른 마케터에게 필요한 지원을 제공하고 여러분이 100% 준비될 수 있도록 도울 시간을 주었습니다. 여러분이 새로운 앱, 프레임워크, 툴 등을 배포할 때 한 번에 진행하기 보다는 점진적으로 진행하는 것을 선호하실 테고, Apple은 이를 제대로 진행할 수 있는 기회를 주었습니다.

이제 이 시간을 잘 활용할 기회가 여러분께 주어졌습니다.

다른 주의 사항은 Apple의 발표에 세부 사항이 많이 포함되지는 않았다는 점입니다. IDFA가 iOS 14 베타 7에서 동의없이 사용할 수 있긴 하지만, 발표 자체에서 명시적으로 IDFA가 동의 없이 사용 가능하다거나 핑거프린팅이 허용될 것이라는 내용을 포함하지는 않았습니다.

따라서 평상시의 비즈니스 발표와 다른 이번 발표 내용에 조금 주의를 기울여야 할 필요가 있습니다. 이는 아직 "고" 사인이 나지 않은 준비 사항으로 곧 "고" 사인이 다가옵니다.

어떻게 iOS 14, SKAdNetwork를 준비하고 변경 사항에 따르는 애로 사항을 줄이는지 궁금하시다면 [자세한 사항을 링크에서 알아보세요](https://www.singular.net/skadnetwork/). 또한 [여러분의 의견도 듣고자 합니다](https://www.singular.net/lp/demo/). 또한 이러한 변경 사항을 함께 논의하는 저희 모바일 어트리뷰션 프라이버시 그룹 Slack([Mobile Attribution Privacy group on Slack](https://join.slack.com/t/mapworkinggroup/shared_invite/zt-9vlvhtzn-bqUVQ1zn3o1UorDNIodvZg))에도 참가해보세요.

저를 개인적으로 해당 Slack 채널에서 찾으실 수 있습니다!

<hr>
[Singular 홈페이지에서 원문 보기](https://www.singular.net/blog/idfa-deprecation-postponed/)
