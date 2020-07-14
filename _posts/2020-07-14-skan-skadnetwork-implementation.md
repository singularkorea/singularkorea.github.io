---
layout: post
title: "SKAN: SKAdNetwork 연동의 표준"
author: "Eran Friedman"
---
![cover](https://www.singular.net/wp-content/uploads/2020/07/SKAN_SKAdNetwork_Implementation_Singular_Blog_Hero.png)

Singular가 [SKAdNetwork 지원](https://singularkorea.github.io/2020-06-28/skadnetwork-support)을 발표하고 [오픈 소스 코드](https://singularkorea.github.io/2020-07-06/skadnetwork-code)를 배포한 이후 업계의 많은 관심이 집중됐습니다. 또한 저희는 여러 광고주, 퍼블리셔, 매체 및 MMP와 함께 SKAdNetowork의 포텐셜에 대해 다각도로 논의해 왔습니다.

저희를 포함한 업계 종사자들은 여러 가치 있는 정보를 얻을 수 있었던 IDFA가 중단된다는 사실을 받아들이고 또 다른 현실을 준비해야 합니다. IDFA가 없는 현실은 파편화된 데이터, 핑거프린팅, 디바이스 내의 솔루션, 그리고 SKAdNetwork라는 모습이죠.

SKAdNetwork는 장점도 있지만 제한적인 부분도 있습니다. Singular에서는 개인 정보 보호 가능한 대체 방법을 찾기 위해 많은 관계자와 함께  지속적으로 개발 활동에 참여해 왔습니다. 이러한 노력으로 모두의 성공에 이바지할 수 있다면 이보다 더 좋은 일이 없을 겁니다.

그러나 아직 답을 찾지 못한 질문과 혼선이 많습니다.

SKAdNetwork는 좋든 싫든 현실로 다가올 것으로 보입니다. SKAdNetwork는 아직 기본만 갖춰져 있는 프레임워크로 기업에서 유용하게 사용되려면 굉장히 조심스럽게 실행되고 철저히 관리되어야 합니다.

이러한 이유로 Singular에서는 SKAN을 개발했습니다. 불확실 속에서도 끊임없이 답을 찾기 위한 시도를 하기 위해서죠.

## SKAdNetwork를 위한 실용적인 모델, SKAN을 소개합니다

SKAN을 발표할 수 있게 되어 정말 기쁩니다. SKAN는 SKAdNetwork의 연동 표준을 위한 제안입니다. SKAN은 모바일 생태계가SKAdNetwork의 어려움을 극복하고 올바르게 사용할 수 있는 방법에 대한 설명하고 있습니다. 추가로 생태계에서 더 가치 있고 널리 사용할 수 있는 방법에 대해서도 알아볼 수 있습니다.

저희는 SKAdNetwork의 문제점을 수많은 업계 종사자와 논의한 후에 이러한 내용을 구축할 수 있었습니다.

SKAN으로 저희는 다음와 같은 목표를 이루고자 합니다.

* 모바일 광고 생태계의 파편화 및 파괴를 막기 위해 SKAdNetwork 레퍼런스 연동 계획 생성
* SKAdNetwork가 (유저 동의를 얻는 경우의) IDFA 기반 어트리뷰션 및 핑거프린팅과 호환될 수 있도록 디자인
* 파편화된 SKAdNetwork 포스트백을 통합할 수 있는 방법 제공
* SKAdNetwork의 전환값(conversion value) 관리 및 연동 표준 정의
* SKAdNetwork에 발생할 수 있는 fraud의 솔루션 제공 (전환값 조작, 반복적인 transaction ID 공격, 지역 값 조작 등)
* 마케터와 매체가 ROAS 및 기타 KPI를 측정할 수 있는 방법 정의
* 광고주에게 통합된 리포팅 제공에 필요한 인프라 정의

[PDF를 다운받고 SKAN에 대해 자세히 알아보세요.](https://drive.google.com/file/d/1Yhri-jG7Jv4zD_Do8_eYBdET2o3uBZQ4/view?usp=sharing?utm_medium=web&utm_source=blog&utm_campaign=skan-practical-standard&utm_content=inline)

## 지금 동참하세요!

SKAN 규격에 기여하실 분은 누구나 환영입니다. SKAN에서는 자유로운 제안과 논의, 개선 및 비판이 진행될 수 있도록 의도적으로 저희를 포함한 모든 해당 기여사의 이름이 제외됩니다.

한 집단에서만 미래를 그릴 수는 없습니다. 저희는 동종업계 종사자로서 함께 마케팅의 미래를 그려야 한다고 생각합니다. 그리고 9월에 예고된 iOS 14에 맞춰 발빠르게 움직여야 합니다.

관련하여 다양한 업계의 리더들과 이야기를 나누면서 더 상세한 정보를 논의하고 싶은 분은 [Mobile Attribution Privacy (MAP) Slack 그룹](https://join.slack.com/t/mapworkinggroup/shared_invite/zt-9vlvhtzn-bqUVQ1zn3o1UorDNIodvZg)으로 참여해 주시고 많은 관심 부탁드립니다.


<hr>
[Singular 홈페이지에서 원문 보기](https://www.singular.net/blog/skan-skadnetwork-implementation/)
