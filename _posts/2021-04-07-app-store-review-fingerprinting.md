---
layout: post
title: "Apple이 앱 업데이트 반려를 통해 iOS 14 개인정보 보호 정책을 집행하고 있으며, Singular에는 영향이 없습니다."
author: "Eran Friedman"
---
![cover](https://www.singular.net/wp-content/uploads/2021/04/Hero_Integration_FAN_1980_930-5.png)

iOS 14.5가 곧 시작될 것으로 보이는 가운데 Apple이 iOS 14 개인정보 보호 정책을 실제로 집행하기 시작했습니다. 가장 큰 단서는 [핑거프린팅](https://www.singular.net/glossary/fingerprinting-attribution/)을 사용하는 측정 SDK가 포함된 앱의 업데이트가 반려된 것이죠.

다행히 Singular 고객사에는 영향을 끼치지 않습니다.

## 앱 심사에 어떤 문제가 있었을까요?

지난 3월 31일부터 모바일 마케터들이 앱이 반려되는 건수가 비정상적이라고 보고하기 시작했습니다. 그 원인은 삽입된 측정 SDK 내의 "방법론적" 어트리뷰션 기술, 즉 핑거프린팅이었습니다. Apple은 반려 안내에서 해당 앱들이 개인과 디바이스를 식별할 수 있는 너무 많은 정보를 수집하고 있고 iOS 14의 앱 추적 투명성(App Tracking Transparency) 프레임워크의 정신을 위배한다고 밝혔습니다. 다음은 해당 안내의 원문입니다.

“Your app uses algorithmically converted device and usage data to create a unique identifier in order to track the user,” says one email we’ve seen. “The device information collected by your app may include some of the following: NSLocaleAlternateQuotationBeginDelimiterKey, NSTimeZone, NSLocaleGroupingSeparator, NSLocaleDecimalSeparator …”

문제가 되는 가이드라인은 개인정보 보호와 데이터 공유(privacy and data sharing)의 5.1.2 조항입니다.

![privacy and data sharing 5.1.2](https://www.singular.net/wp-content/uploads/2021/04/5.2.1.png)
출처: [Apple](https://developer.apple.com/app-store/review/guidelines/#data-use-and-sharing) 

사실 크게 놀랍거나 충격적인 소식은 아닙니다. Singular는 지난 몇 달간 계속해서 이 상황에 대해 경고해왔죠.

## 원인은 무엇이고 누가 영향받았나요?

현재 Adjust의 SDK가 영향받은 것으로 파악됩니다. 다른 MMP도 영향받았을 가능성도 있으나 밝혀진 바는 없습니다. 

Singular 고객사에서는 단 한 건의 반려도 일어나지 않았으며 이유는 명확합니다. Singular는 처음부터 OS 14에서 유저 동의 없이는 **핑거프린트가 [IDFA](https://www.singular.net/blog/mobile-tutorial-series-idfa-apple-identifier-advertisers/)의 대신이 되지 않도록 노력**해 왔습니다. 사실 모바일 웹에서 앱으로 연결되는 보유 미디어의 경우처럼 [작은 역할](https://www.singular.net/blog/fingerprinting-in-ios-14/)이 있음에도 불구하고 핑거프린팅 사용은 App Store에서의 앱 반려의 원인이 될 수 있음을 지적해왔죠.

실제로 이번 사건과 같이 앱의 업데이트가 금지되었습니다.

![tweet](https://github.com/singularkorea/singularkorea.github.io/blob/master/assets/app_reject_tweet.png?raw=true)

Adjust의 SDK가 GitHub의 오픈 소스로 공개되어 있어서 App Store의 앱 업데이트 반려의 원인을 파악해볼 수 있었습니다. 해당 SDK는 [최근 대규모로 업데이트](https://github.com/adjust/ios_sdk/commit/8790a5300d00a11b8f51c7cc66c94165ac656f8c)를 했음이 확인됩니다. 36개의 파일이 변경되고 44가지의 추가 사항과 622가지의 삭제 사항이 있었죠.

삭제 사항은 전체 핑거프린팅 기술에 관련되어 있습니다.

* NSString \*persistedUuid = [ADJKeychain valueForKeychainKey:@”adjust_uuid” service:@”deviceInfo”];
* (NSString \*)adjDeviceId:(ADJDeviceInfo \*)deviceInfo;
* NSString \*binaryHardwareName = [ADJUtil stringToBinaryString:hardwareName];
* NSUInteger chargingStatus = [ADJSystemProfile chargingStatus];
* NSUInteger batteryLevel = [ADJSystemProfile batteryLevel];
* NSUInteger totalSpace = [ADJSystemProfile totalDiskSpace];
* NSUInteger lastBootTime = [ADJSystemProfile lastBootTime];

본질적으로 하드웨어 정보부터 배터리 상태나 가동 시간, 소프트웨어 버전에 이르기까지 너무 많은 정보를 수집하는 측정 파트너는 문제의 소지가 있습니다. 이 모든 데이터는 모바일 생태계에서 특정 디바이스를 자세히 표시하는데 사용할 수 있고 인스톨/전환 어트리뷰션과 잠재적으로 디바이스를 트래킹하는 것에 사용되어 결국 유저를 식별할 가능성이 있기 때문입니다.

현재 너무 많은 정보를 수집하는 SDK를 사용하는 앱은 반려되고 있습니다.

다만 주지할 점은 Apple이 iOS 14 개인정보 보호 시행을 억제하고 있다는 것입니다. App Store에서 앱을 퇴출하는 대신 업데이트만을 반려하고 있습니다. 앱 퍼블리셔에게는 분명 불편한 일이긴 하지만 비교적 영향이 적고 해결책이 분명한 사항이죠. Apple은 앱 업데이트 반려보다 앱 개발자에게 더 엄격한 영향을 미치는 판단을 내렸을 수도 있었을 겁니다.

## Singular는 어떨까요?

Singular는 수집하는 데이터를 매우 조심스럽고 보수적으로 다뤄왔고, Apple의 정책에 부합하도록 유지하는데 신중을 기했습니다. 사실 너무 엄격한 잣대를 들이댄 것은 아닌지 되물은 적도 있었습니다. 특히 IDFA 상실에 대비해 몇몇 MMP가 핑거프린팅 기능을 준비하는 것을 볼 때 더욱 그랬죠.

현재 우리는 매우 매우 매우 안전한 방향이 되도록 자사의 SDK를 다시 검토하고 있는 가운데 현 상황을 주도면밀하게 관찰하고 있습니다. 2020년 6월 23일 [SKAdNetwork 지원을 처음으로 발표한 MMP](https://singularkorea.github.io/2020-06-28/skadnetwork-support)로서 언제나 우리의 목표는 Apple의 정책에 100% 부합하는 것이며, 이를 이루고 자부합니다. 이는 우리 고객사의 혼란을 최소화하도록 보증하는 길입니다.

추후의 상황 변화에 따라 본 포스트를 업데이트하겠습니다. (하단의 원문 보기를 참조해주세요.)

<hr>
[Singular 홈페이지에서 원문 보기](https://www.singular.net/blog/app-store-review-fingerprinting/)
