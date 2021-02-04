---
layout: post
title: "Apple의 SKAdNetwork: 뷰스루 어트리뷰션, 핑거프린팅, 앱투웹 측정"
author: "Gadi Eliashiv"
---
![cover](https://www.singular.net/wp-content/uploads/2021/01/Apple-on-SKAdNetwork_-View-through-attribution-fingerprinting-and-app-to-web-measurement-3.png)

데이터 프라이버시에 큰 획이 그어졌습니다. Apple이 프라이버시, 정보 투명성, 그리고 iOS 14가 데이터를 수집하고 공유할 수 있는 앱과 서비스를 어떻게 제어할 지에 대한 새로운 정보를 대량으로 제공했기 때문이죠. 이제 바로 다음 iOS 14 베타(14.5) 버전부터는 앱 트래킹 투명성(App Tracking Transparency) 팝업이 요구되고, 다음 전체 iOS 버전에서는 공개 버전에도 적용될 예정입니다. 아마 3월이 될 가능성이 커 보입니다.

또한, 큰 변화를 가져올 이 발표로 업계에서 논의되던 주요 쟁점 사항 역시 해결되었습니다.

## iOS 14.5의 핑거프린팅과 ATT

iOS 14.5부터 Singular는 같은 회사 소유의 앱이나 사이트 사용자 간의 경우처럼 특별히 허용되는 경우를 제외하고는 확률적 매칭이나 핑거프린팅을 지원하지 않습니다.

우리 모두에게 어려운 상황이 될 겁니다.

사실 Singular는 [지난 여름에 이 상황을 이미 인지](https://singularkorea.github.io/2020-06-29/idfa-faq)했고, iOS App Store에서 [앱이 금지되는 10가지 방법](https://www.singular.net/blog/banned-from-app-store/)이라는 블로그 포스팅을 포함해서 [거듭](https://singularkorea.github.io/2020-07-09/ios14-idfa-qa), [거듭](https://www.singular.net/blog/mobile-app-attribution/), [거듭](https://www.singular.net/blog/ios14-mmp/) 알려왔습니다. 추후에도 핑거프린트를 계속해서 사용할 수 있기를 기도하거나 개인 정보 보호 측면에서의 근본적인 결함이 있는 부분에 투자를 지속하는 대신, 우리는 핑거프린팅이 곧 사장될 것으로 예측하고 최선의 투자는 SKAdNetwork에 우리의 모든 에너지를 쏟아 혁신을 이루는 것이라고 결정했습니다.

그 결과로 우리는 고객사에 업계에서 가장 진보된 SKAdNetwork 솔루션을 제공할 수 있게 되었습니다. [SKAdNetwork](https://www.singular.net/blog/what-is-skadnetwork/)를 계속 진화하고자 하는 Apple의 의도를 통해, 우리는 마케터가 iOS 14 이후에도 효과적인 사용자 확보 및 성장을 계속해서 이뤄나갈 수 있다고 진심으로 믿고 있습니다.

우리는 이미 ironSource, Snap, Vungle, Unity, Liftoff 등과 같은 주요 파트너와 [SKAdNetwork 연동을 이미 시작](https://singularkorea.github.io/2020-10-16/skadnetwork-ios-14-initial-partners-announcement)했으며, 매주 새로운 연동 사항을 계속 출시하고 있습니다. 또한, Facebook의 최근 발표와 Google의 업데이트를 통해 이 두 매체에서도 우리 고객사를 위한 지원이 가능해질 것입니다.

결론적으로 Singular의 고객사는 모든 주요 플랫폼에서 SKAdNetwork를 통해 iOS 전환을 완벽하게 측정할 수 있게 될 것으로 확신합니다.

Apple이 [지난 2년간](https://www.singular.net/wp-content/uploads/2020/06/image-6-2048x1117.png) 일관된 메시지를 전달했음에도 불구하고 핑거프린팅이 허용되리라 희망을 품게 하는 허점들이나 불명확한 용어의 사용들로 인해 지난 6개월간 핑거프린팅에 대한 예측에 혼선이 있었고, 핑거프린팅 지원을 불가하도록 강제하는 것이 어려울 것이라는 예측도 있었습니다. 불명확성에 의한 혼선이었죠.

하지만 이번 발표에 Apple이 모든 것이 명확히 했습니다.

[Apple의 FAQ](https://developer.apple.com/kr/app-store/user-privacy-and-data-use/)에 추가된 최근 업데이트에서 핑거프린팅과 확률적 매칭은 모두 없어지게 되었습니다. 이에 더해 Apple은 확률적 매칭의 기본 요소가 되는 IP 주소("유저의 네트워크 연결")과 유저 에이전트("유저의 웹 브라우저") 마저도 이용 트래킹 중 하나로 부르고 있습니다.

![qna](https://www.singular.net/wp-content/uploads/2021/01/Screen-Shot-2021-01-28-at-1.10.28-PM.png)

> 기기 또는 사용자를 식별하는 데 지문 또는 기기의 신호를 사용할 수 있습니까?

> 아니요. Developer Program 사용권 계약에 따라, 기기에서 해당 기기를 고유하게 식별할 목적으로 데이터를 추출할 수 없습니다. (이후의 번역 내용은 한글 페이지에는 아직 업데이트되지 않은 사항으로 영문 페이지를 번역한 내용입니다.) 유저나 기기 데이터는 다음 사항을 포함하고 반드시 해당 사항에만 국한되지 않습니다: 유저의 웹 브라우저의 자산과 구성 내용, 유저의 기기 및 구성, 유저의 위치, 유저의 네티워크 연결. 이를 사용하는 앱, 혹은 SDK(광고 네트워크, 어트리뷰션 서비스, 분석 서비스 등의 사항을 포함하고 반드시 해당 사항에만 국한되지 않음)를 포함한 경우 App Store에서 반려될 수 있습니다.

오늘날까지 업계의 몇몇 회사는 IDFA 없이, 또한, ATT를 통한 유저의 추적 동의 없이도 핑거프린팅을 통해 [모바일 어트리뷰션 서비스](https://www.singular.net/mobile-attribution/)를 제공할 수 있을 것으로 생각하고 있습니다. 우리가 즉각적으로 SKAdNetwork를 도입하고 [솔루션을 개발](https://singularkorea.github.io/2020-06-28/skadnetwork-support)하는 동안, 몇몇 플레이어는 디바이스 그래프와 데이터 마켓플레이스 개발을 계속해 왔죠.

이제 이러한 행동은 중단될 수밖에 없습니다. (또한, 곧 업계의 모든 회사 이를 인정하는 발표가 잇따를 겁니다. 아마 일부는 기존의 선언을 180도 뒤집는 방향이 될 수 있겠죠.)

핑거프린트가 90% 가량만 정확하다는 사실은 중요치 않습니다. 클릭과 디바이스를 연결하기 위해 일회성으로 사용하더라도 마찬가지입니다. 데이터를 해쉬해서 개인 정보를 일정 정도 불명확하게 만든다고 해도 그렇습니다. Apple은 매우 분명하게 유저의 동의 없는 핑거프린트는 허용되지 않는다고 선언했습니다.

## SKAdNetwork의 뷰스루 어트리뷰션과 크리에이티브 최적화

앱 마케터를 위한 또 다른 대규모 업데이트는 Apple이 제공하는 개인 정보를 보호하면서도 결정론적 모바일 어트리뷰션 솔루션인 SKAdNetwork가 **이제 뷰스루 어트리뷰션(VTA)를 포함한다는 것입니다!**

![vta](https://www.singular.net/wp-content/uploads/2021/01/Screen-Shot-2021-01-28-at-1.12.51-PM.png)

Singular는 SKAdNetwork를 도입한 첫 번째 [모바일 측정 파트너](https://www.singular.net/glossary/mobile-measurement-partner-mmp/)이며 해당 개념을 높게 평가하고 있지만, SKAdNetwork 2.0에 다소 약점이 있는 것도 사실이었습니다. 최초 버전에서 가장 크게 보이던 격차는 뷰스루 어트리뷰션이 지원되지 않는다는 것이었죠. 따라서 마케터와 퍼블리셔에게 해당 기능 추가 소식은 기꺼울 수밖에 없습니다. 또한, 은연중에 마케터에게 크리에이티브 퍼포먼스 측정도 가능해질 가능성도 보이므로 이 역시 좋은 소식일 겁니다.

어떻게 SKAdNetwork가 노출 트래킹을 구현할지, 또한, 어트리뷰션을 뺏어가기 위해 퍼블리셔가 SKAdNetwork에 가짜 "노출"을 리포팅했는지 여부에 대해 검증할지에 대해서는 자세히 알려진 바가 없습니다. 개인적으로 광고 네트워크가 광고 노출을 위해 필수적으로 사용해야 하는 보안 컨테이너를 사용해서 뷰 상태를 검증하기 시작하지 않을까 하고 예측니다.

VTA 지원이 텍스트를 포함한 모든 광고 유형에 사용 가능한지도 아직 불명확합니다. 가능할 것으로 예상하긴 하지만 발표 내용에는 비디오, 오디오, 상호작용 광고까지만 명시됐기 때문입니다.

## 더 복잡한 사항: 앱투앱

Apple이 드디어 ["비공개 클릭 측정(private click measurement)"](https://webkit.org/blog/8943/privacy-preserving-ad-click-attribution-for-the-web/)을 소개하려는 계획을 공유했습니다. 이는 WebKit의 ITP의 목적으로 개발된 개념입니다. Apple은 이를 "앱투웹" 흐름에 더 많은 비공개 측정을 활성화하기 위해 사용하려고 계획하고 있습니다.

오늘날 "앱투웹" 플로우는 UTM 파라미터를 통해 쉽게 측정 가능지만, 비공개는 아닙니다. Apple은 이 데이터 흐름을 강화할 계획 역시 가지고 있으며, 이는 웹 분석 소프트웨어들이 모바일 앱에서 오는 유저를 파악하기 위해 도입해야 할 큰 변화 사항이 될 겁니다.

![private click measurement](https://www.singular.net/wp-content/uploads/2021/01/Screen-Shot-2021-01-28-at-1.21.39-PM.png)

## 더 중요한 점: Apple이 귀 기울이고 있습니다.

최근 발표에서의 뷰스루 어트리뷰션 지원, 또는 핑거프린팅에 대한 100% 명확한 지침보다 어쩌면 더 중요한 점이 있습니다.

Apple의 발표는 Apple이 시장 상황과 마케터들의 의견에 귀기울이고 있다는 것을 시사합니다. 자사 제품에 대해 전 세계에 알려야 하는 앱 개발자와 퍼블리셔의 의견을 듣고 있다는 것이죠.

이는 Apple이 유저의 개인 정보를 마케터의 목적에 따라 해칠 수 없도록 보호하는 와중에도 Apple의 플랫폼에서 사업을 영위하는 퍼블리셔와 브랜드, 회사가 계속 일할 수 있도록 주의를 기울이고 있다는 점에서 의미가 높습니다.

## 더 많은 내용을 공유하고 싶습니다.

핑거프린팅, SDK, ATT, SKAdNetwork, MMP의 역할 등에 대해 Singular 블로그([영문 공식](https://www.singular.net/blog/), [한글](https://singularkorea.github.io/))에서 더 많은 내용이 업데이트될 예정입니다.

어떻게 Singular가 여러분을 개인 정보를 보호하면서도 IDFA 이후 시대에서도 계속 사업을 성장시키도록 도울 수 있는지 궁금하신가요? [전문가와 상의하세요](https://www.singular.net/demo/).

<hr>
[Singular 홈페이지에서 원문 보기](https://www.singular.net/blog/apple-privacy-day-announcement-skadnetwork//)
