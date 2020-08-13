---
layout: post
title: "보안 SKAdNetwork 2.0: 신뢰 구축과 매끄러운 설정을 한 번에"
author: "Gadi Eliashiv"
---
![cover](https://www.singular.net/wp-content/uploads/2020/08/Secure-SKAdNetwork-2.0_-Establish-trustworthy-conversion-reporting-blog-banner-4.png)

최초로 마켓에 SKAdNetwork을 위한 솔루션을 도입하겠다고 공표한 6월 23일, 이미 우리는 SKAdNetwork에 다음 두 가지 치명적인 문제점이 존재함을 파악했습니다.

* **Apple이 전환값(Conversion value)을 서명하지 않음**
이로 인해 네트워크가 해당 값을 변경할 수 있고 높은 ROI를 자체적으로 리포트할 가능성이 존재하여 전반적인 SKAdNetwork의 신뢰성을 위협합니다.
* **포스트백 페이로드에 국가 정보가 포함되지 않음**
포스트백의 첫 수신자는 송신자의 IP를 통해 국가를 식별할 수 있지만, 이 데이터는 해당 시점 이후에 유실되어 네트워크가 전달해줘야 하므로 역시 정보 변경 가능성이 존재합니다.

우리는 이 문제를 **보안 SKAN 프로젝트**를 통해 해결하기로 결정했습니다. 또한 이 솔루션을 오픈소스 SKAdNetwork 스펙인 [SKAN](https://github.com/singular-labs/skan)에 제출하여 "[보안 SKAdNetwork 설정](https://github.com/singular-labs/skan#a4)"을 고안해냈습니다.  

* 광고 네트워크와 DSP는 각각의 MMP와 함께 SKAdNetwork에 공동 등록합니다. (예: "Singular+Ad Network")
* MMP는 포스트백의 최초 수신자가 되고 이를 광고 네트워크에 전달합니다.
* 이 방법으로 데이터 조작 관련 우려가 사라지고 리포팅이 매우 쉬워집니다.

해당 솔루션을 런칭한 이후 많은 고객사가 긍정적인 피드백과 관심을 표해주셨고 광고 네트워크로부터 진정한 협업 역시 진행할 수 있습니다. 다만 이 방법은 다수의 SKAdNetwork 등록이 필요하다는 점에서 실현 가능성이 있음에도 크게 능률적이진 않았습니다. 따라서 우리는 동일 선상의 신뢰와 보안성을 유지하면서도 더 쉬운 방법을 찾기 위해 계속 노력했습니다.

**오늘 보안 SKAdNetwork 설정을 혁신적으로 간소화시킬 수 있는 새로운 방법을 공개합니다.**

본 솔루션은 다음 단계로 동작합니다.

1. SKAdNetwork 포스트백의 최초 수신자는 광고 네트워크로, 임시 리다이렉션을 뜻하는 HTTP 307 응답을 반환합니다.
2. 이 HTTP 응답은 디바이스에 정확히 동일한 HTTP 메시지를 Singular 엔드포인트로 재송신하도록 지시합니다.
3. Singular는 우선 이 메시지가 고유하고 중복되지 않음을 검증합니다.
4. 다음으로 이 메시지가 실제 Apple에 의해 암호학적으로 서명되었는지 검증합니다.
5. 마지막으로 부정 참가자가 서버에서 수정한 포스트백을 보내는 것을 방지하기 위해 송신자의 IP 주소가 합리적으로 고유한지 검증합니다.

![Secure SKAdNetwork](https://www.singular.net/wp-content/uploads/2020/08/IDFA_307c-1024x771.png)

많은 장점을 유지하면서도 네트워크가 쉽게 구현할 수 있도록 매끄럽고 편리한 솔루션을 발표할 수 있게 되어 정말 기쁩니다. SKAdNetwork를 테스트하는 것이 쉽지 않은 만큼 이 신규 설정을 검증하는 것에는 시일이 소요되겠지만 본 솔루션의 동작을 이미 우리 실제 디바이스에서 검증하였음을 안내드립니다.

**보안 SKAN 솔루션에서 제공하는 주요 장점은 다음과 같습니다.**

* 프러드 방지
디바이스가 네트워크와 Singular에 정확히 동일한 페이로드를 전송하므로 데이터 조작이 불가능합니다.

* 간단한 설정
SKAdNetwork 서명 프로세스 내의 새로운 SKAdNetworkIdentifier가 필요하지 않으며 퍼블리셔 측면에서도 새 리스트를 업데이트할 필요가 없습니다.

* 쉬운 구현
저희가 유저의 디바이스에서 직접 데이터를 받으므로 광고 네트워크가 SKAdNetwork 데이터 공급을 위한 API를 구현할 필요가 없습니다. 

향후 몇 주간 우리 광고 네트워크 파트너사에게 SKAdNetwork의 보안 구현을 지속적으로 홍보할 예정입니다. 고객사와 파트너와 함께 나아갈 향후 여정을 기대하며 지원에 감사드립니다.

<hr>
[Singular 홈페이지에서 원문 보기](https://www.singular.net/blog/secure-skadnetwork/)
