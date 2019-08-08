---
title: Cloud Voice の展開
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: Rowille
description: Microsoft Teams でクラウド音声機能を展開するための実用的なガイダンス。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 476d65ee927fedf285cf66377c58c9f09698b046
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236767"
---
# <a name="cloud-voice-deployment"></a>Cloud Voice の展開

Microsoft Teams、Office 365 でのチームワークとコミュニケーションのハブでは、電話会議、通話プランを使った電話システム、およびチーム会議を拡張してビジネス要件を満たすための電話システムのダイレクトルーティング機能を利用できるようになりました。公衆交換電話網 (PSTN) 経由で接続されている外部関係者を対象とした通話エクスペリエンス。


> [!Tip] 
> 電話システムの概要については、次のセッションをご覧ください。 [Microsoft Teams での電話システムの概要](https://aka.ms/teams-phone-system)
 
このページは、Teams 用のクラウド音声の追加機能が時間の経過と共にリリースされるように更新されます。



## <a name="audio-conferencing-in-microsoft-teams"></a>Microsoft Teams での電話会議


Office 365 の電話会議では、参加者はどの電話端末からでも Teams 会議に参加できます。

Office 365 の[電話会議](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365)で利用できる機能は次のとおりです。


## <a name="phone-system-with-calling-plans-calling-plans-in-microsoft-teams"></a>Microsoft Teams の通話プラン ("通話プラン") を搭載した電話システム

電話システムは、通話ルーティング、ポリシー、ユーザープロビジョニングを管理する機能を提供する Office 365 の機能です。 これには、電話の通話管理システム、通話ルーティング、通話制御が含まれます。

通話プランは、電話システム機能のアドオンサービスであり、Teams と Skype for Business Online を通じて提供されます。 通話プランを使用するには、Skype for Business Online のユーザーが Microsoft Teams で作業する必要があります。 通話プランを使用すると、ビジネスの相手に主要な電話番号が提供され、組織外で PSTN 経由で電話をかけたり受けたりすることができます。

詳細については、「 [Office 365 の電話システムで利用できる機能](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system)」および「[電話システムと通話プラン](calling-plan-landing-page.md)」を参照してください。


## <a name="phone-system-direct-routing-direct-routing"></a>電話システム直結ルーティング (「ダイレクトルーティング」)

直接ルーティングは、電話システムの機能と連携することで、組織内のユーザーに PSTN 経由での電話の発信と受信を許可します。 pstn 接続は、サードパーティのサービスプロバイダーによって提供されます。

詳細については、「[プランダイレクトルーティング](direct-routing-plan.md)と[ダイレクトルーティングの構成](direct-routing-configure.md)」を参照してください。

## <a name="practical-guidance-for-audio-conferencing-calling-plans-and-direct-routing-in-microsoft-teams"></a>Microsoft Teams での電話会議、通話プラン、直接ルーティングに関する実用的なガイダンス

この実用的なガイダンスは、Office 365 FastTrack 顧客の旅フレームワークと、3つ&mdash;のフェーズのビジョン、オンボード、およびドライブ値を使って開催されています。 これは、電話会議、通話プラン、またはダイレクトルーティングの実装の計画、納品、操作を支援することを目的としています。

> [!div class="mx-tableFixed"]
> |構想  |参加  |価値の創出  |
> |---------|---------|---------|
> |[成功を定義する](1-envision-define-my-success-cloud-voice.md) <br> サービスの決定を行う <br>&nbsp;&nbsp;[電話会議](2-envision-make-my-service-decisions-audio-conferencing.md)<br>&nbsp;&nbsp;[通話プラン](2-envision-make-my-service-decisions-phone-system.md)または[ダイレクトルーティング](2-envision-make-my-service-decisions-direct-routing.md) <br> [環境を評価する](3-envision-evaluate-my-environment.md) <br> [サービス管理を計画する](4-envision-plan-my-service-management.md) <br> [ユーザーエクスペリエンスを計画する](5-envision-plan-my-users-experience.md) <br> [成功計画を文書化する](6-envision-document-my-success-plan.md)    | [サービスを準備する](1-onboard-prepare-my-service.md) <br> [ユーザーを準備する](2-onboard-prepare-my-users.md) <br> [サービスを展開する](3-onboard-deploy-my-service.md)  <br> <br> <br> <br>     | [サービスを運用する](1-drive-value-operate-my-service.md) <br> [サービスを強化する](2-drive-value-enhance-my-service.md) <br> <br> <br> <br> <br>      |

コンテンツは順序に従って提示されます。また、開始から終了までの間に、エンドツーエンドの展開が利用できるように設計されています。 既に展開している場合は、適用可能なコンテンツ領域を参照することをお勧めします。


> [!TIP]
> この実際的なガイダンスでは、各アクティビティとキーディスカッションの出力例を提供します。 このドキュメント全体の例は、ヒントの吹き出し内に含まれており、テンプレートとして提供されているため、再利用することができます。 計画プロセスの一部として実行する必要がある情報については、"TBA" (追加) が表示されます。
