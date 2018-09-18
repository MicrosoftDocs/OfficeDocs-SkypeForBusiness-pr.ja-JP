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
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9bf4d920ba8ce8e25d663a9bab1769f80d693a77
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23892367"
---
# <a name="cloud-voice-deployment"></a>Cloud Voice の展開

Office 365 でのチームワークおよび通信のためのハブである Microsoft Teams は、公衆交換電話網 (PSTN) を経由して接続される外部パーティを含めるように Teams の会議および通話のエクスペリエンスを拡大することによって追加のビジネス要件にも適合する、電話会議と通話プランが設定された電話システムの機能を提供するようになりました。
 
このページの内容は、Teams の Cloud Voice の追加機能がリリースされるたびに更新されます。



## <a name="audio-conferencing-in-microsoft-teams"></a>Microsoft Teams での電話会議


Office 365 の電話会議では、参加者はどの電話端末からでも Teams 会議に参加できます。

Office 365 の[電話会議](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365)で利用できる機能を以下に示します。


## <a name="phone-system-with-calling-plans-calling-plans-in-microsoft-teams"></a>Microsoft Teams の通話プラン (「通話プラン」) が設定された電話システム

電話システムは通話のルーティング、ポリシー、ユーザー プロビジョニングを管理するための Office 365 の機能です。 この機能には、通話管理システム、通話のルーティング、通話コントロールが含まれます。

通話プランは、Teams と Skype for Business Online を介して提供される電話システム機能用のアドオン サービスです。 通話プランでは、対象ユーザーは Microsoft Teams で機能するために Skype for Business Online に所属している必要があります。 通話プランを利用することで、ビジネス ユーザーは代表電話番号を入手でき、公衆交換電話網 (PSTN) を介して組織外での通話の受信と発信を行うことができます。

詳細については、「[Office 365 での電話システムで利用できる機能](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system)」と「[Office 365 の通話プランについて](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365)」をご覧ください。


## <a name="phone-system-direct-routing-direct-routing"></a>電話システムのダイレクト ルーティング (「ダイレクト ルーティング」)

ダイレクト ルーティングは、電話システムの機能と連動して、組織内のユーザーが PSTN を介して組織外での通話を発信および受信できる機能を提供します。この場合、PSTN 接続はサード パーティのサービス プロバイダーを介して提供されます。

詳細については、「[ダイレクト ルーティングを計画する](direct-routing-plan.md)」と「[ダイレクト ルーティングを構成する](direct-routing-configure.md)」をご覧ください。

## <a name="practical-guidance-for-audio-conferencing-calling-plans-and-direct-routing-in-microsoft-teams"></a>Microsoft Teams での電話会議、通話プラン、ダイレクト ルーティングの実践的なガイダンス

この実践的なガイダンスは、Office 365 FastTrack カスタマーの移行フレームワークと、&mdash;構想、参加、価値の創出という 3 つのフェーズを使用して編成されています。 電話会議、通話プラン、またはダイレクト ルーティングの実装を正常に行うための計画、提供、運営を支援することを意図した内容になっています。

> [!div class="mx-tableFixed"]
> |構想  |参加  |価値の創出  |
> |---------|---------|---------|
> |[成功を定義する](1-envision-define-my-success-cloud-voice.md) <br> サービスの決定を行う対象 <br>&nbsp;&nbsp;[電話会議](2-envision-make-my-service-decisions-audio-conferencing.md)、<br>&nbsp;&nbsp;[通話プラン](2-envision-make-my-service-decisions-phone-system.md)、または[ダイレクト ルーティング](2-envision-make-my-service-decisions-direct-routing.md) <br> [環境を評価する](3-envision-evaluate-my-environment.md) <br> [サービス管理を計画する](4-envision-plan-my-service-management.md) <br> [ユーザーのエクスぺリエンスを計画する](5-envision-plan-my-users-experience.md) <br> [成功計画を文書化する](6-envision-document-my-success-plan.md)    | [サービスを準備する](1-onboard-prepare-my-service.md) <br> [ユーザーを準備する](2-onboard-prepare-my-users.md) <br> [サービスを展開する](3-onboard-deploy-my-service.md)  <br> <br> <br> <br>     | [サービスを運用する](1-drive-value-operate-my-service.md) <br> [サービスを強化する](2-drive-value-enhance-my-service.md) <br> <br> <br> <br> <br>      |

コンテンツは整然とした形式で提示され、エンドツーエンドの展開の手順を最初から最後まで説明するように作成されています。 既に積極的に展開を行っている場合でも、該当するコンテンツの領域を参照することを推奨します。


> [!TIP]
> この実践的なガイダンスには、各アクティビティおよび重要なディスカッションの例が記載されています。 このドキュメントでは、これらの例はヒントの吹き出し内に含まれていいて、テンプレートとして再利用することができます。 「TBA」(今後追加予定) と記載されている場所には、計画プロセスの一部として完了する必要がある情報が入ります。
