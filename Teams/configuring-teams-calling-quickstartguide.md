---
title: クイック スタート ガイド - 通話プランの構成
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: 一連のユーザーを起動して実行できるよう、Microsoft Teams で通話プランを構成するためのクイック スタート ガイド。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6420fdff102533c44bdd3ccb2ab503a646c354b8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101183"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>クイック スタート ガイド: Microsoft Teams での通話プランの設定
==============================================================

このガイドでは、ユーザーが Teams で通話プランを利用できるように設定する手順について説明します。

Teams の通話プランに関する 2017 年 12 月 12 日付けの発表「[Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)」(英語) をお読みください。

> [!NOTE]
> 展開を成功させるため、このクイック スタート ガイドとともに、「[通話プランが設定された電話システム](calling-plan-landing-page.md)」と「[FastTrack](https://aka.ms/cloudvoice)」をご覧になることをお勧めします。

Skype for Business を利用した Microsoft 365 および Office 365 の機能である通話プランを追加すると、Teams を使用して、公衆交換電話網 (PSTN) を介して、固定電話と携帯電話の間で通話を発信および受信できます。

![Teams の [連絡先] ページを示すスクリーンショット](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Teams の [**通話**] タブを有効にするための前提条件
Teams の [**通話**] を有効にするには、Teams で 1:1 の通話を有効にする必要があります。また、Teams の 1:1 の通話をサポートする Teams クライアントを使用する必要があります。 Teams で 1:1 の通話を管理する方法の詳細については、「[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)」を参照してください。 通話をサポートしているクライアントの詳細については、「[Microsoft Teams の制限事項と仕様](./limits-specifications-teams.md)」を参照してください。

> [!NOTE]
> 現在、ボイスメールは、ユーザーが PSTN 通話を有効にしていない限り、[通話] タブには表示されません。 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Teams の [**ダイヤル パッド**] タブを有効にするための前提条件
Teams の [**ダイヤル パッド**] タブを有効にして、ユーザーが PSTN 通話の発信と受信を行えるようにするには、電話システムと通話プランの利用に向けてユーザーをプロビジョニングする必要があります。 通話プランの設定方法については、「[通話プランの設定](./set-up-calling-plans.md)」をご覧ください。
また、Teams のみのユーザーについては、Teams 通話ポリシーで「プライベート通話を許可します」が有効になっていることを確認する必要があります。 詳細については、「[新しい Microsoft Teams 管理センターへの移行中に Teams を管理する](./manage-teams-skypeforbusiness-admin-center.md)」をご覧ください。
> [!NOTE]
> また、ダイレクト ルーティングを使用して、ユーザーが PSTN 通話を発信および受信できるようにすることもできます。 ダイレクト ルーティングの設定方法については、「[ダイレクト ルーティングを構成する](./direct-routing-configure.md)」をご覧ください。

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>TeamsUpgradePolicy を使用した通話の着信先の制御
着信先 （およびチャット） が Teams または Skype for Business になるように制御するには、管理者は [MicrosoftTeams 管理センター](https://aka.ms/teamsadmincenter)を使用するか、[Skype for Business](/powershell/module/skype) コマンドレットでリモート Windows PowerShell セッションを使用して TeamsUpgradePolicy を使用します。


TeamsUpgradePolicy の既定の構成は、アイランド モードです。これは Teams の展開時に既存のビジネス ワークフローが中断されることがないように構成されています。 既定では、ユーザーへの VoIP 通話、PSTN 通話、フェデレーション通話は、ポリシーを更新して Teams への着信通話を有効にするまで、Skype for Business にルーティングされます。  受信者がアイランド モードの場合の動作は、次のようになります。

 - Skype for Business で発信された着信 VOIP 通話は、常に受信者の Skype for Business クライアントに着信します。
 - *送信者と受信者が同じテナント内にある場合は*、Teams 内で発信された着信 VOIP 通話は Teams に着信します。
 - 着信フェデレーション VOIP (クライアントの発信元に関係なく) および PSTN 通話は、常に受信者の Skype for Business クライアントに着信します。
 
着信 VOIP 通話と PSTN 通話が常にユーザーの Teams クライアントに着信できるようにするには、ユーザーの共存モードを TeamsOnly に更新します (つまり、TeamsUpgradePolicy の「UpgradeToTeams」インスタンスを割り当てます)。  共存モードと TeamsUpgradePolicy の詳細については、「[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](./migration-interop-guidance-for-teams-with-skype.md)」を参照してください。

**注**
 - ユーザーが TeamsOnly モードを使用している場合でも、Skype for Business IP 電話は通話を受信します。  
 - Skype for Business Online で使用する電話システムと通話プランのライセンスでプロビジョニングされた (たとえば、OnlineVoiceRoutingPolicy の値が割り当てられている) ユーザーには、Teams で [通話] タブが有効化されているため、管理者による管理操作なしで Teams から PSTN 通話の発信を行うことができます。


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Teams 内のすべての着信 VOIP および PSTN 通話を受信するようにユーザを設定する方法
ユーザーがすべての着信 VOIP と PSTN 通話を Teams で確実に受信できるようにするには、Microsoft Teams 管理センターでユーザーの共存モードを TeamsOnly に設定するか、Skype for Business のリモート Windows PowerShell セッションを使用して、次のように TeamsUpgradePolicy を更新します。

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>関連項目
[通話プランの設定](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](./migration-interop-guidance-for-teams-with-skype.md)

[通話プランが設定された電話システム](calling-plan-landing-page.md)

[Skype for Business PowerShell のコマンドレット リファレンス](/powershell/module/skype)