---
title: 'クイック スタート ガイド: Microsoft Teams での通話プランの設定'
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille, crowe
search.appverid: MET150
description: マイクロソフトのチームでの通話プランを構成するためのクイック スタート ガイドです。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fd1e9484b522a657a92916815c1ae8940dcc2117
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898524"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>クイック スタート ガイド: Microsoft Teams での通話プランの設定
==============================================================

一連のユーザーおよびチームの計画を呼び出すを参照できるように実行するを取得する際に役立ちます。

チームの計画を呼び出すの 2017 年 12 月 12日、お知らせを読む:[インテリジェント通信チームでの呼び出しには、次の手順を実行します。](https://aka.ms/ipyqus)

> [!NOTE]
> このクイック スタート ガイドとの併用とを参照する[計画を呼び出すと、電話システム](calling-plan-landing-page.md) [fasttrack という](https://aka.ms/cloudvoice)計画とドライブに展開の成功をお勧めします。

計画を Office 365 機能により、ビジネスの Skype の呼び出しを追加することによって土地の明細行および公衆交換電話網 (PSTN) 経由で携帯電話からの電話呼び出しを送受信するチームを使用できます。

![チームでの通話](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>チームでは、[**通話**] タブを有効にするための前提条件
チームでは、[**通話**] タブを有効にするには、ユーザーを呼び出すチームで有効になっていると、1 対 1 のチームを呼び出すことをサポートしているチームのクライアントを使用して 1:1 がある必要があります。 1 対 1 のチームで呼び出しを管理する方法については、[一連の CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)を参照してください。 通話をサポートするクライアントについては、[制限しマイクロソフトのチームの仕様](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)を参照してください。

> [!NOTE]
> 現在、ボイスメールするには、[通話] タブで使用可能な PSTN の呼び出しに対して、ユーザーが有効になっています。 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>チームでは、**ダイヤル パッド**を有効にするための前提条件
チームで、[**ダイヤル パッド**] タブを有効にして、ユーザーが PSTN 通話を送受信できるようにするのには、電話システムおよび計画を呼び出すユーザーをプロビジョニングする必要があります。 プランの呼び出しを設定する方法については、[計画を呼び出す設定](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)を参照してください。

> [!NOTE]
> 直接ルーティングを使用して、PSTN 通話を送受信するユーザーを許可することができますもします。 直接ルーティングを設定する方法については、[直接ルーティングの構成](https://docs.microsoft.com/microsoftteams/direct-routing-configure)を参照してください。

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>呼び出しの着陸場所のコントロールに TeamsUpgradePolicy を使用してください。
チームやビジネス用の Skype で着信呼び出し (およびチャット) が着陸するかどうかを制御するには、管理者は TeamsUpgradePolicy、いずれかの[マイクロソフトのチーム管理センター](https://aka.ms/teamsadmincenter)を使用するか、リモートの Windows PowerShell セッションを使用して、[ビジネスの Skype](https://docs.microsoft.com/powershell/module/skype)でを使用します。コマンドレットです。


TeamsUpgradePolicy の既定の構成は、諸島のモードは、その既存のビジネス ワークフローはチームに展開したときは中断されないことを確認するよう設計されています。 既定では、VoIP と PSTN、ユーザーにフェデレーションの呼び出しは引き続きチームへの着信通話を有効にするポリシーを更新するまでは、Skype のビジネスにルーティングされます。  受信者は、島のモードでは。

 - VOIP の着信呼び出しに由来する Skype ビジネスの常にビジネス クライアント用の受信者の Skype での着陸。
 - 着信 VOIP 電話の*送信者と受信者は、同じテナントのかどうかは*、チームのチームの土地に由来します。
 - 着信の連合 (クライアントに関係なく元の場所) の VOIP と PSTN では常に受信者の Skype の土地ビジネス クライアントです。
 
着信 VOIP と PSTN がように常にユーザーのチームのクライアントでの着陸をするには更新のユーザーの共存のモードを TeamsOnly (これは TeamsUpgradePolicy の"UpgradeToTeams"のインスタンスを割り当てることを意味します。  共存モードおよび TeamsUpgradePolicy の詳細については、「[チームとは、ビジネス用 Skype を使用する組織の移行と相互運用性](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)の使用」を参照してください。

**メモ**
 - ビジネス IP 電話の Skype ユーザーが TeamsOnly モードである場合でも、呼び出しが表示されます。  
 - (例: 割り当てられている OnlineVoiceRoutingPolicy の値)、ビジネス オンラインはチームで有効になっている [通話] タブがありからの発信の PSTN 通話を配置することができますは、Skype で使用するライセンスの電話システムとプランを呼び出すことでプロビジョニングされているユーザー管理者は、管理操作を実行する必要のないチームです。


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>チームでの呼び出しを受信したすべての VOIP と PSTN を受信するユーザーを構成する方法
ユーザー チームのすべての着信 VOIP と PSTN の呼び出しを受信することを確認するには、マイクロソフトのチーム管理センターで、ユーザーの共存モードを TeamsOnly に設定またはリモートの Windows PowerShell セッションをビジネス用の Skype を使用して、次のように TeamsUpgradePolicy を更新します。

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a>関連項目
[通話プランの設定](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[通話プランと電話システム](calling-plan-landing-page.md)

[Skype のビジネスの PowerShell コマンドレットのリファレンス](https://docs.microsoft.com/powershell/module/skype)

