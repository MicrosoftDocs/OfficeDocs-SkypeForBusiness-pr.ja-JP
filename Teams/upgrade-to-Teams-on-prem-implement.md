---
title: Skype for Business オンプレミス展開から Teams へのアップグレード - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Skype for Business から Teams へのアップグレード
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bec5c2b10dc2e09092cd7c26284c04868982e287
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533604"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Skype for Business から &mdash; IT 管理者向けの Teams にアップグレードを実装する

この記事では、アップグレードを実装する方法について説明します。 この記事では、IT 管理者向けのアップグレードの概念と実装について説明します。  

- [概要](upgrade-to-teams-on-prem-overview.md)
- [アップグレード方法](upgrade-to-teams-on-prem-upgrade-methods.md)
- [アップグレードを管理するためのツール](upgrade-to-teams-on-prem-tools.md)
- [Skype for Business オンプレミスの組織に関するその他の考慮事項](upgrade-to-teams-on-prem-considerations.md)
- **アップグレードを実装する** (この記事)
- [公衆交換電話網 (PSTN) に関する考慮事項](upgrade-to-teams-on-prem-pstn-considerations.md)

さらに、次の記事では、アップグレードの重要な概念と共存の動作について説明します。

- [Teams と Skype for Business の共存](upgrade-to-teams-on-prem-coexistence.md)
- [共存モード-参照](migration-interop-guidance-for-teams-with-skype.md)
- [Teams のクライアント エクスペリエンスおよび共存モードへの準拠](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>アップグレード方法

このセクションでは、次のアップグレードオプションのいずれかを使用してアップグレードを実装する方法について説明します。

- [機能のアップグレード (孤島モードを使用)](#overlapping-capabilities-upgrade-using-islands-mode)
- [Teams の使用を開始していない組織の select 機能アップグレード](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [既に孤島モードで Teams を使用している組織の select 機能アップグレード](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

オプションに関する詳細情報が必要な場合は、 [アップグレード方法](upgrade-to-teams-on-prem-upgrade-methods.md)が既読であることを確認してください。

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>機能のアップグレード (孤島モードを使用)

重複機能のアップグレードオプションの場合:

- 組織全体の迅速なアップグレードを行うことができる場合は、このオプションを検討します。  エンドユーザーが両方のクライアントを実行しても混乱する可能性があるため、ユーザーが両方のクライアントを実行するために必要な時間を最小限に抑えることをお勧めします。 管理者は、両方のクライアントを実行することをユーザーに周知する必要があります。

- このオプションは、既定のモデルであり、Microsoft 365 または Office 365 ライセンスを割り当てることを除いて、管理者による操作を必要としません。 ユーザーが既に Skype for Business Online を使用している場合は、このモデルを既に使用している可能性があります。

- 機能のオーバーラップモードの使用を終了して、TeamsOnly に移動することは難しい場合があります。 アップグレード済みのユーザーは Teams でのみ通信するため、そのユーザーと通信する組織内の他のユーザーはすべて Teams を使用する必要があります。  Teams を使用し始めていないユーザーがいる場合、メッセージを受け取れない可能性が生じます。 さらに、そのようなユーザーには、オンラインの TeamsOnly ユーザーが Skype for Business に表示されません。 一部の組織では、テナントのグローバルポリシーを使用してテナント全体のアップグレードを実行します。ただし、これを回避するには、事前の計画と、すべてのユーザーがアップグレードの準備ができているまで待機する必要があります。


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Teams の使用を開始していない組織の select 機能アップグレード

Teams のアクティブなユーザーが 1 人もいない組織の場合、最初のステップとして、テナント全体に対する TeamsUpgradePolicy の既定のポリシーを、Skype for Business のモードの 1 つ (SfbWithTeamsCollab など) に設定します。  Teams を使用し始めていないユーザーは、動作の違いに気付きません。 それでも、テナント レベルでこのポリシーを設定すると、TeamsOnly モードへのユーザーのアップグレードを開始でき、さらに、アップグレード済みユーザーはまだアップグレードしていないユーザーとの通信を行うことができます。  パイロット ユーザーを特定したら、それらのユーザーを TeamsOnly にアップグレードできます。  そのユーザーがオンプレミスの場合は、Move-CsUser を使用します。 オンラインになっている場合は、CsTeamsUpgradePolicy を使用してチームメンバーのみを割り当てることができます。 既定で、これらのユーザーによってスケジュールされている Skype for Business 会議は、Teams に移行されます。

主なコマンドを次に示します。

1. 次のようにして、テナント全体の既定値をモードの SfbWithTeamsCollab に設定します。

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. パイロットユーザーを teams にアップグレードするには、次の手順を実行します。

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
- `Move-CsUser` は、オンプレミスツールのコマンドレットです。 このスイッチを使用するには、 `MoveToTeams` CU8 以降の skype For Business server 2019 または skype For Business server 2015 が必要です。 以前のバージョンを使用している場合は、最初にユーザーを Skype for Business Online に移行してから、そのユーザーに TeamsOnly モードを付与できます。
- 既定で、TeamsOnly モードへのアップグレードや SfbWithTeamsCollabAndMeetings モードの割り当てを実行すると、Skype for Business 会議は Teams に移行されます。  

次の図は、Teams の使用を前に使用していない組織の選択機能アップグレードの概念フェーズを示しています。 バーの高さは、ユーザー数を表します。 アップグレードのどのフェーズでも、すべてのユーザーが相互に通信できます。  Skype for Business ユーザーは TeamsOnly ユーザーと相互運用を使用して通信します。逆の場合も同様です。 島々モードのユーザーは、両方のクライアントを確実に実行する必要があります。

![チームを以前に使用していない、選択された機能アップグレードを示す図](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>既に孤島モードで Teams を使用している組織の select 機能アップグレード

組織内の一部のユーザーが Teams をアイランド モードでアクティブに使用している場合、既存のユーザーから機能を削除することは望ましくない場合があります。 その場合、テナント全体のポリシーを変更する前に、もう 1 つステップが必要になります。 この問題の解決策は、テナント全体のポリシーを SfbWithTeamsCollab に設定する前に、既存のアクティブな Teams ユーザーをアイランド モードで grandfather 化することです。  これが完了したら、上述のように展開を実行できます。ただし、TeamsOnly に移行する 2 グループのユーザーが存在することになります。つまり、Teams でアクティブだったユーザーはアイランド モードになり、残りのユーザーは SfbWithTeamsCollab モードになります。 管理者は、これらのユーザーを TeamsOnly モードに段階的に移行できます。

1. Teams でアクティブなユーザーを見つけるには、次のようにします。

   1. Microsoft 365 管理センターの左側のナビゲーションで、[レポート]、[使用状況] の順に移動します。 
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

次の図は、アクティブな孤島ユーザーが開始時にある select 機能移行の概念フェーズを示しています。 バーの高さは、ユーザー数を表します。 アップグレードのどのフェーズでも、すべてのユーザーが相互に通信できます。  Skype for Business ユーザーは TeamsOnly ユーザーと相互運用を使用して通信します。逆の場合も同様です。 


![島々モードでアクティブなユーザーとの選択機能のアップグレードを示す図](media/teams-upgrade-2.png)

   



## <a name="related-links"></a>関連リンク

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md) 

[Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を構成する](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[オンプレミスとクラウドの間でユーザーを移動する](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[会議移行サービス (MMS) を使用する](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

