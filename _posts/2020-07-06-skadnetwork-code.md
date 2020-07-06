---
layout: post
title: "SKAdNetwork Code: Singular에서 매체, 퍼블리셔, 광고주가 사용할 수 있는 코드를 Github에 공개합니다"
author: "Eran Friedman"
---
![cover](https://www.singular.net/wp-content/uploads/2020/06/SKADnetwork-Code-Blog-Banner-Singular-2.png)

IDFA 지원 중단으로 인해 사업에 부정적인 영향을 받지 않을까 걱정하시나요? SKAdNetwork는 어떤 원리로 사용되어 기존 로직을 교체하게 될지 궁금하신가요? 

저희도 십분 공감합니다.

[IDFA는 아직까지 사용되고 있지만](https://singularkorea.github.io/2020-06-25/ios14-idfa-limit-ad-tracking-skadnetwork-wwdc-privacy-update), 앞으로는 사라질 것이 자명합니다. 모바일 마케팅에 있어 큰 임팩트를 남길 이번 변화에 따라 많은 분들이 당장 궁금한 부분이 많으실 겁니다. 다행히 Singular는 몇 년 동안 SKAdNetwork에 대해 준비해왔으므로 [조금이나마 궁금증을 풀어드릴 수 있습니다](https://singularkorea.github.io/2020-06-29/idfa-faq).

**또한 Singular는 여러분을 지원해드릴 겁니다.**

Singular는 SKAdNetwork를 실험해보시고 싶은 분들을 위해 레퍼런스 코드를 출시했습니다. 저희 [Github 리포지토리](https://github.com/singular-labs/Singular-SKAdNetwork-App)에서는 매체, 퍼블리셔, 그리고 광고주들이 새로운 SKAdNetwork의 기능을 확인하실 수 있고 각각 부분들과 어떻게 시너지가 이루어지는지 파악할 수 있도록 샘플 코드를 제공합니다. 또한 오픈 소스 코드를 통해 광고 서버가 어떻게 암호화 서명을 실행할 수 있는지도 알아볼 수 있습니다.

Singular는 [SKAdNetwork를 최초로 지원하는 MMP](https://singularkorea.github.io/2020-06-28/skadnetwork-support)입니다. 저희의 목표는 IDFA 시대와 다름없이 모바일 마케터들이 SKAdNetwork를 쉽게 사용하여 개인 정보가 보호하면서도 캠페인 최적화를 진행할 수 있도록 도와드리는 겁니다.

**또한 Singular는 조만간 SKAdNetwork과 호환 가능하도록 업데이트된 SDK를 출시할 예정이며 Singular와 매체간의 연동에 관련된 내용도 곧 공유드릴 예정입니다.**

Apple이 SKAdnetwork의 적용을 강제하고 있으므로 저희도 최대한 빨리 준비하고자 합니다. 저희는 업계가 빠르게 해당 모델을 적용할 거라고 믿습니다. iOS 14가 9월에 출시되고 iOS의 운영 시스템의 정보에 접하게 되면 모두가 최소 두 달 만에 이 내용을 업데이트할 것으로 예상합니다.

이번 코드 릴리즈는 다음 내용을 포함합니다.

1. 광고주 샘플 앱
2. 퍼블리셔 샘플 앱
3. 매체 API를 시뮬레이션하는 서버 (요구 사항인 암호화 서명 생성도 가능)

이 Code는 메체, 퍼블리셔 및 광고주에게 도움이 될 것입니다. Singular는 저희의 지식을 여러분들께 공유드리고자 많은 시간을 투자하여 SKAdNetwork에 대해 연구했습니다. 저희의 노력이 업계가 조금이나마 쉽고 빠르게 이번 변화에 적응하는데 힘이 되었으면 합니다.

<hr>
[Singular 홈페이지에서 원문 보기](https://www.singular.net/blog/skadnetwork-code/)
