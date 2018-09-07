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
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 001c1b0f69108630267f368b065cc8d72c0b38c5
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23855280"
---
# <a name="cloud-voice-deployment"></a>Cloud Voice の展開

マイクロソフト チーム、チームワークと、Office 365 での通信用のハブでは、オーディオ会議、計画を呼び出すには、電話システムを提供し、電話システムは、チーム会議を拡張することによって新たなビジネス要件に対応するルーティング機能を直接、呼び出し元に公衆交換電話網 (PSTN) を介して接続されている外部の関係者を含めることがあります。
 
このページのチームの他のクラウドの音声機能がリリースされると時間の経過と共に更新します。



## <a name="audio-conferencing-in-microsoft-teams"></a>Microsoft Teams での電話会議


Office 365 の電話会議では、参加者はどの電話端末からでも Teams 会議に参加できます。

ここでは、Office 365 では、[オーディオ会議](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365)を表示します。


## <a name="phone-system-with-calling-plans-calling-plans-in-microsoft-teams"></a>通話の電話システムは、マイクロソフトのチームで (「通話プラン」) を計画

電話システムは通話のルーティング、ポリシー、ユーザー プロビジョニングを管理するための Office 365 の機能です。 この機能には、通話管理システム、通話のルーティング、通話コントロールが含まれます。

通話プランは、オンライン ビジネスのチームと Skype 経由で配信、電話システムの機能のアドオン サービスです。 通話プランには、マイクロソフトのチームで作業するのにはビジネス オンラインの Skype で該当するユーザーが所属することが必要です。 通話プランを提供、お客様のビジネスの基本の電話番号と、行い、PSTN 上で、組織外の電話を受信することができます。

詳細についてを参照して[ここでは Office 365 の電話システムで取得して](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system) [Office 365 のプランを呼び出すことは何ですか?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365)


## <a name="phone-system-direct-routing-direct-routing"></a>システムの電話、直接ルーティング (「ダイレクト ルーティング」)

機能を組織内のユーザーに付与するのには電話システムの機能の直接のルーティング動作を行いサード パーティのサービス プロバイダーを使用して PSTN 接続を提供する場所、PSTN 上で、組織外の電話を受信します。

詳細については、[直接ルーティングを計画](direct-routing-plan.md)し、[直接ルーティングの構成](direct-routing-configure.md)を参照してください。

## <a name="practical-guidance-for-audio-conferencing-calling-plans-and-direct-routing-in-microsoft-teams"></a>オーディオ会議、計画を呼び出すこと、およびマイクロソフトのチームに直接ルーティングに関する実用的なガイダンス

Office 365 fasttrack というお客様の旅のフレームワークを使用してこの実用的なガイドの構成し、フェーズ 3 つ&mdash;ビジョン化トラック、オンボードとドライブの値です。 計画、配布、およびオーディオ会議、計画を呼び出すこと、または直接ルーティングの実装を成功させるに動作を支援するためのものが。

> [!div class="mx-tableFixed"]
> |構想  |参加  |価値の創出  |
> |---------|---------|---------|
> |[自分の成功を定義します。](1-envision-define-my-success-cloud-voice.md) <br> 意思決定、サービス <br>&nbsp;&nbsp;[オーディオ会議](2-envision-make-my-service-decisions-audio-conferencing.md)、<br>&nbsp;&nbsp;[計画を呼び出す](2-envision-make-my-service-decisions-phone-system.md)か、または[直接ルーティング](2-envision-make-my-service-decisions-direct-routing.md) <br> [自分の環境を評価します。](3-envision-evaluate-my-environment.md) <br> [[サービスの管理を計画します。](4-envision-plan-my-service-management.md) <br> [自分のユーザー エクスペリエンスを計画します。](5-envision-plan-my-users-experience.md) <br> [成功計画を文書化します。](6-envision-document-my-success-plan.md)    | [サービスを準備します。](1-onboard-prepare-my-service.md) <br> [自分のユーザーを準備します。](2-onboard-prepare-my-users.md) <br> [サービスを展開します。](3-onboard-deploy-my-service.md)  <br> <br> <br> <br>     | [自分のサービスを実施します。](1-drive-value-operate-my-service.md) <br> [サービスを強化します。](2-drive-value-enhance-my-service.md) <br> <br> <br> <br> <br>      |

内容は、順序付けられた方法で表示され、開始から終了まで、エンド ・ ツー ・ エンド展開の旅を見てするよう設計されています。 既に積極的に導入している場合もお勧め適切なコンテンツ領域を参照することです。


> [!TIP]
> この実用的なガイドでは、各アクティビティおよびキーの説明を出力する例を提供しています。 このドキュメントで説明する例がヒントの吹き出しの中に囲まれているし、再利用できるテンプレートとして機能します。 については、計画プロセスの一部として完了する必要がある (追加) するには、"TBA"が表示されます。
