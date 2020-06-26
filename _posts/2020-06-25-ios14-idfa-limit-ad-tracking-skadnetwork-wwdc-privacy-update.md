---
layout: post
title: "iOS 14: IDFA 시대가 저물어 갑니다. 어떻게 대처할 수 있을까요?"
author: "Gadi Eliashiv"
---

![IDFA](https://www.singular.net/wp-content/uploads/2020/06/Asset_1024x1024.png)

Apple은 22일 개최된 WWDC 2020에서 올해 9월에 출시 예정인 iOS 14에 새로 개선된 개인 정보 보호 정책을 발표했습니다. Singular는 오래전부터 이번 변화를 예상했고, 작년부터 직접 SKAdNetwork 개선에 기여할 수 있는 Mobile Attribution Privacy Group (MAP)을 이끌며 꾸준히 새로운 변화를 대비하여 준비해왔습니다. [(MAP에 참여하기)](https://joinmap.org/)

소비자들에게 희소식: 개인 정보가 더 철저히 보장됩니다.
마케터들에게 희소식: data-driven 마케팅은 지속 가능합니다.

이번 Apple의 SKAdNetwork 프레임워크 업데이트는 매우 훌륭해 보이는데요. 해당 업데이트는 앱 퍼블리셔들의 니즈에 귀를 기울이는 동시에 저희도 지속적으로 마케터들에게 필요한 툴을 제공할 수 있도록 개선되었습니다.

Singular는 곧 개인 정보 보호가 보장되는 다양한 솔루션에 대해 발표할 예정입니다.

## 옵트인 (Opt-in) IDFA

신규 iOS 14 버전부터 모든 앱은 [IDFA](https://www.singular.net/blog/mobile-tutorial-series-idfa-apple-identifier-advertisers/)를 사용하기 전에 사용자의 동의를 얻어야 합니다. 사용자 정보를 추적하기 전에 투명하게 허가를 받는 구조입니다. 

[Apple 공식 문서](https://developer.apple.com/documentation/bundleresources/information_property_list/nsusertrackingusagedescription):
> “Your app needs to request permission to track sometime before tracking occurs. This could be at first launch or when certain app features are used. For example, when signing on with a third-party SSO.”

![LAT](https://www.singular.net/wp-content/uploads/2020/06/pasted-image-0.png)

Apple에서 iOS 14에 대해 공식으로 발표한 문서를 보면 유저가 “앱 트래킹 거절” 버튼을 클릭할 경우 해당 앱은 기기의 IDFA 접근이 불가능하고 “광고 추적 차단(Limited Ad Tracking)”이 켜져 있을 때와 동일한 값을 받게 됩니다. 쉽게 말해서 유저 허락 없이 어떠한 식별자도 받을 수 없게 됩니다.

다만 IDFA 수집을 원하는 경우 앱 개발자들이 시스템 권한 알림 요청에서 [맞춤형](https://developer.apple.com/documentation/bundleresources/information_property_list/nsusertrackingusagedescription) 텍스트를 통해 개인 정보 수집 용도를 유저에게 설명할 수 있습니다. 다시 말해 유저들이 옵트인을 하도록 설득할 수 있는 기회가 주어집니다.

하지만 현실적으로 대다수의 유저들은 위와 같은 창을 맞닥뜨리게 되면 메시지의 설득력 여부를 떠나 개인 정보 수집 요청에 동의하지 않습니다.
이제 IDFA를 대체할 방법을 찾아야 할 순간이 왔습니다.

## IDFA Status 확인

Apple은 isAdvertisingTrackingEnabled 기능의 공식 지원을 중단했습니다. 개발자들은 유저가 해당 값을 활성화했는지 확인하기 위해 [AppTrackingTransparency](https://developer.apple.com/documentation/apptrackingtransparency) 프레임워크를 사용해야합니다.

## SKAdNetwork 변화

![SKAdNetwork](https://www.singular.net/wp-content/uploads/2020/06/pasted-image-0-2.png)

또한 Apple은 개인 정보 보호 모바일 속성 프레임 워크인 SKAdNetwork에 몇 가지 부분에 개선을 진행했습니다. 주요한 개선 사항을 간략히 정리해보았습니다.

1. 타이머 적용: 전환 알림을 실시간으로 보내지 않습니다. 본 변화는 개인 정보 보호를 위한 개선이라고 보입니다.

2. 전환값 업데이트 매커니즘 추가: 이는 인스톨 이후의 제한적인 이벤트를 첨부하기 위한 방법이라고 예측됩니다.

3. Redownload (다시 다운로드): 다시 다운로드 / 재인스톨 지원이 추가되었습니다.

4. Source App ID 추가: 퍼블리싱 앱 인식이 가능합니다. (퍼블리셔 레벨의 분석이 가능해지므로 저희에게는 매우 중대한 개선입니다.)

이 외에도 더 많은 부분이 개선되었는데요. Singular에서 지속적으로 조사하여 공유드리도록 하겠습니다.

## 새로운 앱 프라이버시 섹션:

iOS 14 버전부터는 유저가 사용하는 앱의 앱스토어 제품 페이지 내에서 개인 정보 정책 링크와 함께 자신의 개인 정보와 관련된 활동을 요약하여 볼 수 있습니다. 또한 해당 섹션은 유저 추적을 위해 앱을 통해 수집되는 데이터뿐만 아니라 유저와 연동된 데이터에 대해서도 요약 리포트를 제공합니다. 예를 들어 구매, 웹 브라우징 이력, 위치 데이터 및 다른 인구 통계 정보들과 같은 정보입니다.

![App privacy](https://www.singular.net/wp-content/uploads/2020/06/pasted-image-0-3-756x1024.png)

이밖에도 공유드릴 정보가 많습니다. 다음 포스팅에서 더 자세한 내용을 확인해보세요!

<hr>
[Singular 홈페이지에서 원문 보기](https://www.singular.net/blog/ios14-idfa-limit-ad-tracking-skadnetwork-wwdc-privacy-update/)
