---
title: Cloud Voice の展開
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: MyAdvisor
description: Microsoft Teams での Cloud Voice の機能の展開についての実践的なガイダンス
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c537f37534c616965b74f5ea268f547cff28d41
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016142"
---
# <a name="cloud-voice-deployment"></a>Cloud Voice の展開

Office 365 でのチームワークおよび通信のためのハブである Microsoft Teams は、公衆交換電話網 (PSTN) を経由して接続される外部パーティを含めるように Teams の会議および通話のエクスペリエンスを拡大することによって追加のビジネス要件にも適合する、電話会議と通話プランが設定された電話システムの機能を提供するようになりました。
 
このページの内容は、Teams の Cloud Voice の追加機能がリリースされるたびに更新されます。



## <a name="audio-conferencing-in-microsoft-teams"></a>Microsoft Teams での電話会議


Office 365 の電話会議では、参加者はどの電話端末からでも Teams 会議に参加できます。

Office 365 の[電話会議](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365)で利用できる機能を以下に示します。


## <a name="phone-system-with-calling-plans-calling-plans-in-microsoft-teams"></a>Microsoft Teams の通話プラン (「通話プラン」) が設定された電話システム

電話システムは通話のルーティング、ポリシー、ユーザー プロビジョニングを管理するための Office 365 の機能です。 この機能には、通話管理システム、通話のルーティング、通話コントロールが含まれます。

通話プランは、オンライン ビジネスのチームと Skype 経由で配信、電話システムの機能のアドオン サービスです。 通話プランには、マイクロソフトのチームで作業するのにはビジネス オンラインの Skype で該当するユーザーが所属することが必要です。 通話プランを提供、お客様のビジネスの基本の電話番号と、行い、PSTN 上で、組織外の電話を受信することができます。

詳細については、「[Office 365 での電話システムで利用できる機能](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system)」と「[Office 365 の通話プランについて](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365)」をご覧ください。


## <a name="phone-system-direct-routing-direct-routing"></a>電話システムのダイレクト ルーティング (「ダイレクト ルーティング」)

ダイレクト ルーティングは、電話システムの機能と連動して、組織内のユーザーが PSTN を介して組織外での通話を発信および受信できる機能を提供します。この場合、PSTN 接続はサード パーティのサービス プロバイダーを介して提供されます。

詳細については、「[ダイレクト ルーティングを計画する](direct-routing-plan.md)」と「[ダイレクト ルーティングを構成する](direct-routing-configure.md)」をご覧ください。

## <a name="practical-guidance-for-audio-conferencing-calling-plans-and-direct-routing-in-microsoft-teams"></a>Microsoft Teams での電話会議、通話プラン、ダイレクト ルーティングの実践的なガイダンス

Office 365 fasttrack というお客様の旅のフレームワークを使用してこの実用的なガイドの構成し、フェーズ 3 つ&mdash;ビジョン化トラック、オンボードとドライブの値です。 計画、配布、およびオーディオ会議、計画を呼び出すこと、または直接ルーティングの実装を成功させるに動作を支援するためのものが。

> [!div class="mx-tableFixed"]
> |構想  |参加  |価値の創出  |
> |---------|---------|---------|
> |[成功を定義する](1-envision-define-my-success-cloud-voice.md) <br> サービスの決定を行う対象 <br>&nbsp;&nbsp;[電話会議](2-envision-make-my-service-decisions-audio-conferencing.md)、<br>&nbsp;&nbsp;[通話プラン](2-envision-make-my-service-decisions-phone-system.md)、または[ダイレクト ルーティング](2-envision-make-my-service-decisions-direct-routing.md) <br> [環境を評価する](3-envision-evaluate-my-environment.md) <br> [サービス管理を計画する](4-envision-plan-my-service-management.md) <br> [ユーザーのエクスぺリエンスを計画する](5-envision-plan-my-users-experience.md) <br> [成功計画を文書化する](6-envision-document-my-success-plan.md)    | [サービスを準備する](1-onboard-prepare-my-service.md) <br> [ユーザーを準備する](2-onboard-prepare-my-users.md) <br> [サービスを展開する](3-onboard-deploy-my-service.md)  <br> <br> <br> <br>     | [サービスを運用する](1-drive-value-operate-my-service.md) <br> [サービスを強化する](2-drive-value-enhance-my-service.md) <br> <br> <br> <br> <br>      |

内容は、順序付けられた方法で表示され、開始から終了まで、エンド ・ ツー ・ エンド展開の旅を見てするよう設計されています。 既に積極的に導入している場合もお勧め適切なコンテンツ領域を参照することです。


> [!TIP]
> この実用的なガイドでは、各アクティビティおよびキーの説明を出力する例を提供しています。 このドキュメントで説明する例がヒントの吹き出しの中に囲まれているし、再利用できるテンプレートとして機能します。 については、計画プロセスの一部として完了する必要がある (追加) するには、"TBA"が表示されます。
