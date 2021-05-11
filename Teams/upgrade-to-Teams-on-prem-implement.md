---
title: IT 管理者向けアップグレード戦略
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: この記事では、IT 管理者向けであり、アプリケーションからアプリケーションへのアップグレードを実装するためのSkype for Business説明Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e4bfb5594b64eb06041e7f761eb0d85cec8c3e5
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52306041"
---
# <a name="upgrade-strategies-for-it-administrators"></a>IT 管理者向けアップグレード戦略

![「展開と実装」段階が強調表示された、アップグレード行程の各段階](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")

この記事は、アプリケーションへのアップグレードを実装する IT 管理者向けTeamsをSkype for Business。

アップグレードを実装する前に、アップグレードの重要な概念と共存動作について説明する次の記事をお勧めします。

- [Microsoft Teams と Skype for Business の共存と相互運用性を理解する](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [共存モード - リファレンス](migration-interop-guidance-for-teams-with-skype.md)
- [Teams のクライアント エクスペリエンスおよび共存モードへの準拠](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>アップグレード方法

このセクションでは、次のいずれかのアップグレード オプションを使用してアップグレードを実装する方法について説明します。

- [重複する機能のアップグレード (諸島モードを使用)](#overlapping-capabilities-upgrade-using-islands-mode)
- [アプリケーションの使用をまだ開始していない組織の選択機能Teams](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [諸島モードで既にアカウントを使用している組織のTeamsアップグレード](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

オプションの詳細が必要な場合は、既に「Choose your upgrade [journey from](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)Skype for Business to Teams 」を参照してください。

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>重複する機能のアップグレード (諸島モードを使用)

重複する機能のアップグレード オプションの場合:

- 組織全体の迅速なアップグレードを行うことができる場合は、このオプションを検討します。  エンド ユーザーが両方のクライアントを実行すると混乱するリスクが生じる可能性があります。ユーザーが両方のクライアントを実行する必要がある期間を最小限に抑えるのが最善です。 管理者は、両方のクライアントを実行することをユーザーに周知する必要があります。

- このオプションは使用できないモデルであり、Microsoft 365 または Office 365 ライセンスを割り当てる以外は、Teams の使用を開始するために管理者の操作を必要とします。 ユーザーが既に Skype for Business Online を使用している場合は、このモデルを既に使用している可能性があります。

- 重複する機能モードから抜け出して TeamsOnly に移行するのも困難な場合があります。 アップグレード済みのユーザーは Teams でのみ通信するため、そのユーザーと通信する組織内の他のユーザーはすべて Teams を使用する必要があります。  Teams を使用し始めていないユーザーがいる場合、メッセージを受け取れない可能性が生じます。 さらに、そのようなユーザーには、オンラインの TeamsOnly ユーザーが Skype for Business に表示されません。 一部の組織では、これを回避するためにテナント 全体のグローバル ポリシーを使用してテナント全体のアップグレードを行います。ただし、これには、すべてのユーザーをアップグレードする準備が整うまで、先行計画と待機が必要です。


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>アプリケーションの使用をまだ開始していない組織の選択機能Teams

Teams のアクティブなユーザーが 1 人もいない組織の場合、最初のステップとして、テナント全体に対する TeamsUpgradePolicy の既定のポリシーを、Skype for Business のモードの 1 つ (SfbWithTeamsCollab など) に設定します。  Teams を使用し始めていないユーザーは、動作の違いに気付きません。 それでも、テナント レベルでこのポリシーを設定すると、TeamsOnly モードへのユーザーのアップグレードを開始でき、さらに、アップグレード済みユーザーはまだアップグレードしていないユーザーとの通信を行うことができます。  パイロット ユーザーを特定したら、それらのユーザーを TeamsOnly にアップグレードできます。  そのユーザーがオンプレミスの場合は、Move-CsUser を使用します。 オンラインの場合は、Grant-CsTeamsUpgradePolicy を使用して TeamsOnly モードを割り当てるだけで完了です。 既定で、これらのユーザーによってスケジュールされている Skype for Business 会議は、Teams に移行されます。

主なコマンドを次に示します。

1. 次のようにして、テナント全体の既定値をモードの SfbWithTeamsCollab に設定します。

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. 次のように、パイロット ユーザーを TeamsOnly にアップグレードします。

   - オンラインのユーザーの場合:

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - オンプレミスのユーザーの場合:

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

メモ
 
- テナント全体のポリシーを SfbWithTeamsCollab に設定する代わりに、SfbWithTeamsCollabAndMeetings に設定することもできます。 そのようにすると、すべてのユーザーが新しい会議すべてを Teams でスケジュールするようになります。
- `Move-CsUser` は、オンプレミスのツールのコマンドレットです。 この `MoveToTeams` スイッチには、CU8 以降Skype for Business Server 2019 Skype for Business Server 2015 以降が必要です。 以前のバージョンを使用している場合は、最初にユーザーを Skype for Business Online に移行してから、そのユーザーに TeamsOnly モードを付与できます。
- 既定で、TeamsOnly モードへのアップグレードや SfbWithTeamsCollabAndMeetings モードの割り当てを実行すると、Skype for Business 会議は Teams に移行されます。  

> [!NOTE]
> Skype for Business Online の提供が近日提供される予定で、Microsoft は近い将来、組織が Teamsに移行する方法を簡略化する予定です。 ユーザーをオンプレミスから Teams に移行する場合、ユーザーをオンプレミスから `-MoveToTeams` TeamsOnly に直接移動する切り替えの指定は間もなく `Move-CsUser` 不要になります。 現在、このスイッチが指定されていない場合、ユーザーはオンプレミスの Skype for Business Server にホームから Skype for Business Online に移行し、モードは変更されません。 提供終了後に、 を使用してユーザーをオンプレミスからクラウドに移動すると、ユーザーには TeamsOnly モードが自動的に割り当てられます。また、スイッチが実際に指定されているかどうかに関係なく、オンプレミスからの会議は Teams 会議に自動的に変換されます。 `Move-CsUser` `-MoveToTeams switch had been specified` この機能は、2021 年 7 月 31 日の実際の提供が解除される前にリリースされる予定です。


次の図は、組織の選択機能のアップグレードの概念的なフェーズを示しています。以前に使用Teams。 バーの高さは、ユーザー数を表します。 アップグレードのどのフェーズでも、すべてのユーザーが相互に通信できます。  Skype for Business ユーザーは TeamsOnly ユーザーと相互運用を使用して通信します。逆の場合も同様です。 Islands モードのユーザーは、両方のクライアントを実行する必要があります。

![選択機能のアップグレードを、事前に使用してアップグレードTeams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>諸島モードで既にアカウントを使用している組織のTeamsアップグレード

組織内の一部のユーザーが Teams をアイランド モードでアクティブに使用している場合、既存のユーザーから機能を削除することは望ましくない場合があります。 その場合、テナント全体のポリシーを変更する前に、もう 1 つステップが必要になります。 この問題の解決策は、テナント全体のポリシーを SfbWithTeamsCollab に設定する前に、既存のアクティブな Teams ユーザーをアイランド モードで grandfather 化することです。  これが完了したら、上述のように展開を実行できます。ただし、TeamsOnly に移行する 2 グループのユーザーが存在することになります。つまり、Teams でアクティブだったユーザーはアイランド モードになり、残りのユーザーは SfbWithTeamsCollab モードになります。 管理者は、これらのユーザーを TeamsOnly モードに段階的に移行できます。

1. Teams でアクティブなユーザーを見つけるには、次のようにします。

   1. 管理センター Microsoft 365左側のナビゲーションで、[レポート] に移動し、[使用状況] に移動します。 
   2. [レポートの選択] ドロップダウンで、[Microsoft Teams]、[ユーザー アクティビティ] の順に選択します。 このようにすると、Teams でアクティブになっているユーザーのエクスポート可能なテーブルが提供されます。 
   3. [エクスポート] をクリックして、Excel を開き、フィルタリングして、Teams でアクティブなユーザーのみを表示します。

2. ステップ 1 で見つかったアクティブな Teams ユーザーそれぞれに対して、リモート PowerShell でアイランド モードを割り当てます。 これで次のステップに進むことができます。ユーザー エクスペリエンスは変更されません。  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. テナント全体のポリシーを SfbWithTeamsCollab に設定します。

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. 選択したユーザーを TeamsOnly モードにアップグレードします。 ユーザーがアイランド モードの場合に生じる可能性のある混乱を最小限に抑えるため、アイランド モードのユーザーを優先的にまずアップグレードすることが望ましい場合もありますが、アイランド モードのユーザーと SfbWithTeamsCollab モードのユーザーのどちらをアップグレードするかは管理者が選択できます。   

   Skype for Business Online に所属しているユーザーの場合:  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   Skype for Business Server オンプレミスに所属しているユーザーの場合:  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

次の図は、選択機能の移行の概念的なフェーズを示しています。この移行では、最初にアクティブな諸島のユーザーがいます。 バーの高さは、ユーザー数を表します。 アップグレードのどのフェーズでも、すべてのユーザーが相互に通信できます。  Skype for Business ユーザーは TeamsOnly ユーザーと相互運用を使用して通信します。逆の場合も同様です。 


![諸島モードのアクティブ ユーザーによる選択機能のアップグレードを示す図](media/teams-upgrade-2.png)

   



## <a name="related-links"></a>関連リンク

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md) 

[Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を構成する](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[オンプレミスとクラウドの間でユーザーを移動する](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[会議移行サービス (MMS) を使用する](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
