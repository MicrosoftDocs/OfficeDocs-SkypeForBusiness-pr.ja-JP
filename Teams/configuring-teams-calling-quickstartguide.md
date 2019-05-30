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
description: Microsoft Teams で通話プランを構成するためのクイックスタートガイドです。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6600513cf4491aed05598439987cff8d8e7232a1
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548105"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>クイック スタート ガイド: Microsoft Teams での通話プランの設定
==============================================================

このガイドは、チームの通話プランを調査できるように、一連のユーザーを準備し、実行するのに役立ちます。

2017年12月12日、Teams での通話プランのお知らせ:[インテリジェントコミュニケーションは、teams での通話の次の手順を実行し](https://aka.ms/ipyqus)ます。

> [!NOTE]
> このクイックスタートガイドと並行して、[通話プランを使って電話システム](calling-plan-landing-page.md)を読み、ロールアウトを計画して成功させるために[fasttrack](https://aka.ms/cloudvoice)を使用することをお勧めします。

通話プランを追加することにより、Skype for Business を使用した Office 365 機能を利用できるようになりました。これで、チームを使って、市内電話網 (PSTN) 経由で、職場や携帯電話との通話を発信および受信することができます。

![Teams の [連絡先] ページを示すスクリーンショット](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Teams で「**通話**」タブを有効にするための前提条件
Teams ユーザーの [**通話**] タブを有効にするには、teams で1:1 通話を有効にし、1:1 teams の通話をサポートするチームクライアントを使用する必要があります。 Teams で1:1 通話を管理する方法については、「 [Set-Csteamのポリシー](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)」を参照してください。 通話をサポートしているクライアントの詳細については、 [Microsoft Teams の制限事項と仕様](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)を参照してください。

> [!NOTE]
> 現時点では、ユーザーが PSTN 通話を有効にしていない限り、[通話] タブでボイスメールを利用することはできません。 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Teams で**ダイヤルパッド**を有効にするための前提条件
Teams で [**ダイヤルパッド**] タブを有効にして、ユーザーが PSTN 通話を発信および受信できるようにするには、電話システムと通話プランのユーザーをプロビジョニングする必要があります。 通話プランの設定方法については、「[通話プラン](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)をセットアップする」を参照してください。

> [!NOTE]
> また、直接ルーティングを使用して、ユーザーが PSTN 通話を発信および受信できるようにすることもできます。 ダイレクトルーティングを設定する方法については、「 [Direct ルーティングを構成](https://docs.microsoft.com/microsoftteams/direct-routing-configure)する」を参照してください。

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>TeamsUpgradePolicy を使用して、通話の陸地を制御する
チームまたは Skype for business で着信通話 (およびチャット) が着陸するかどうかを制御するには、 [Microsoft Teams 管理センター](https://aka.ms/teamsadmincenter)を使用するか、または[skype for Business](https://docs.microsoft.com/powershell/module/skype)でリモート Windows PowerShell セッションを使用して、管理者が TeamsUpgradePolicy を使用します。cmdlet.


TeamsUpgradePolicy の既定の構成は諸島モードであり、チームの展開時に既存のビジネスワークフローが中断されないように設計されています。 既定では、ユーザーへの VoIP、PSTN、およびフェデレーションされた通話は、ポリシーを更新してチームへの着信通話を有効にするまで、引き続き Skype for Business にルーティングされます。  受信者が諸島モードの場合:

 - Skype for Business で発生した着信 VOIP 通話は、常に受信者の Skype for business クライアントに着陸します。
 - *送信者と受信者が同じテナントにある場合*、teams で発生した着信 VOIP 通話。
 - 受信したフェデレーション VOIP (クライアントの種類に関係なく) と PSTN 通話は、常に受信者の Skype for Business クライアントにあります。
 
受信した VOIP と PSTN の通話が常にユーザーのチームクライアントに確実に含まれるようにするには、ユーザーの共存モードを [チームのみ] に更新します (つまり、TeamsUpgradePolicy の "UpgradeToTeams" インスタンスを割り当てます)。  共存モードと TeamsUpgradePolicy の詳細については、「[チームと Skype For business を併用する組織向けの移行と相互運用性に関するガイダンス](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)」を参照してください。

**記録**
 - Skype for Business の IP 電話では、ユーザーが teams モードのみを使用している場合でも、通話が受信されます。  
 - Skype for Business Online で使用するために、電話システムと通話プランを使ってプロビジョニングされたユーザー (OnlineVoiceRoutingPolicy の値が割り当てられている場合) は、Teams で [通話] タブが有効になり、送信 PSTN 通話を発信できます。管理者がいないチームで、管理者の操作を行う必要があります。


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Teams でのすべての受信 VOIP および PSTN 通話を受信するようにユーザーを構成する方法
ユーザーが受信した VOIP および PSTN 通話をすべて Teams で確実に受信できるようにするには、Microsoft Teams 管理センターでユーザーの共存モードを Teams に設定するか、Skype for Business リモート Windows PowerShell セッションを使用して、次のように TeamsUpgradePolicy を更新します。

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a>関連項目
[通話プランの設定](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[通話プランを使用した電話システム](calling-plan-landing-page.md)

[Skype for Business PowerShell コマンドレットリファレンス](https://docs.microsoft.com/powershell/module/skype)

