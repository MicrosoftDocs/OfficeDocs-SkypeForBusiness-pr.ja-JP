---
title: Skype for Business オンプレミス展開から Teams へのアップグレード - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Skype for Business から Teams へのアップグレード-アップグレード用のツール
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3b910a93435cedfc1dcc83c34b766d9121f93eea
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955954"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>IT 管理者の Teams にアップグレードするためのツール &mdash;

この記事では、Teams にアップグレードするためのツールについて説明します。 この記事では、IT 管理者向けのアップグレードの概念と実装について説明します。  

- [概要](upgrade-to-teams-on-prem-overview.md)
- [アップグレード方法](upgrade-to-teams-on-prem-upgrade-methods.md)
- **アップグレードを管理するためのツール**   (この記事)
- [Skype for Business オンプレミスの組織に関するその他の考慮事項](upgrade-to-teams-on-prem-considerations.md)
- [アップグレードを実装する](upgrade-to-teams-on-prem-implement.md)
- [公衆交換電話網 (PSTN) に関する考慮事項](upgrade-to-teams-on-prem-pstn-considerations.md)

さらに、次の記事では、アップグレードの重要な概念と共存の動作について説明します。

- [Teams と Skype for Business の共存](upgrade-to-teams-on-prem-coexistence.md)
- [共存モード-参照](migration-interop-guidance-for-teams-with-skype.md)
- [Teams のクライアント エクスペリエンスおよび共存モードへの準拠](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a>アップグレードの管理ツール

どちらのアップグレード方法を選んだ場合でも、 [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)を使って、ユーザーの共存モードを制御する、チームへの切り替えを管理できます。 各モードの詳細については、「[共存モード](migration-interop-guidance-for-teams-with-skype.md)」を参照してください。

[Skype for Business] モードを使って select 機能切り替えを実行するか、または既定の孤島構成から teams Sonly モードにアップグレードするか、TeamsUpgradePolicy はプライマリツールになります。 Teams の他のポリシーと同じように、TeamsUpgradePolicy をユーザーに直接割り当てることができます。 また、ポリシーをテナント全体の既定値として設定することもできます。 ユーザーへの割り当ては、テナントの既定の設定よりも優先されます。  ポリシーは、Teams の管理コンソールと PowerShell で管理できます。

ユーザーが Skype for Business Online またはオンプレミスのどちらを使用している場合でも、TeamsUpgradePolicy の任意のモードをユーザーに割り当てることができます。 **ただし、TeamsOnly モードは、既に skype For Business online に所属しているユーザーにのみ割り当てる**ことができます。 これは、Skype for Business ユーザーとフェデレーションと Microsoft 365 電話システム機能の相互運用機能は、ユーザーが Skype for Business Online を使用している場合にのみ可能であるためです。

オンプレミスに所属する Skype for Business アカウントを持つユーザーは、Skype for Business オンプレミスのツールセットに含まれる Move-CsUser を使用して、Skype for Business Online か直接 Teams のどちらかの[オンラインに移行する必要があります](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)。 これらのユーザーは、1 つか 2 つのステップで TeamsOnly に移行できます。

-   1 ステップ: Move-CsUser で  -MoveToTeams スイッチを指定します。 これには、CU8 以降の Skype for Business Server 2019 または Skype for Business Server 2015 が必要です。

-   2 ステップ: Move-CsUser を実行した後で、TeamsUpgradePolicy を使用して、そのユーザーに TeamsOnly モードを付与します。

他のポリシーとは異なり、Microsoft 365 または Office 365 では、TeamsUpgradePolicy の新しいインスタンスを作成することはできません。 既存のインスタンスはすべて、このサービスに組み込まれています。  (モードは、TeamsUpgradePolicy 内のプロパティであり、ポリシー インスタンスの名前ではありません)。ポリシー インスタンスの名前がモードと同一である場合もありますが、必ず一致するわけではありません。 特に、ユーザーに TeamsOnly モードを割り当てる場合は、TeamsUpgradePolicy の UpgradeToTeams インスタンスをそのユーザーに付与します。 すべてのインスタンスの一覧を表示するには、次のコマンドを実行します。

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

オンライン ユーザーを TeamsOnly モードにアップグレードするには、次のようにして UpgradeToTeams インスタンスを割り当てます。 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

オンプレミスの Skype for Business ユーザーを TeamsOnly モードにアップグレードするには、次のようにしてオンプレミス ツールセットに含まれる Move-CsUser を使用します。

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

ユーザーごとに明示的に付与されているユーザー (その設定が優先される) を除くテナント内のすべてのユーザーのモードを変更するには、次のコマンドを実行します。

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Skype for Business アカウントを使用しているユーザーがいる場合は、オンプレミスの Skype for Business アカウントを持つすべてのユーザーに、他のモードを明示的に割り当てない限り、チームのテナントレベルで teams Sonly モードを割り当てないでください。


## <a name="using-notifications-in-skype-for-business-clients"></a>Skype for Business クライアントで通知を使用する

管理者は、Skype for Business クライアントでエンド ユーザー通知を提供して、ユーザーがまもなく Teams にアップグレードされることを通知できます。次の図にサンプルを示します。 たとえば、管理者は、ユーザーのグループを TeamsOnly モードにアップグレードしようと考えている日の 1 週間前に、そのグループのユーザーに対する通知をオンにできます。 これらの通知は、TeamsUpgradePolicy のインスタンスを使用し、NotifySfbUsers=true に設定して有効にできます。  TeamsOnly 以外のすべてのモードでは、実際には、NotifySfbUsers の 2 つの値に対応する 2 つのインスタンスがモードごとに存在します。  TeamsOnly 以外のすべてのモードでは、実際には、NotifySfbUsers の 2 つの値に対応する 2 つのインスタンスがモードごとに存在します。 

![通知を示す図](media/teams-upgrade-sfb-with-notifications.png)

ユーザーが Skype for Business Online に所属している場合は、そのユーザーと同じモードを持つポリシー インスタンスを割り当てるだけです。ただし、NotifySfbUsers=true に設定します。 

ユーザーが Skype for Business Server オンプレミスに所属している場合は、オンプレミスのツールセットを使用する必要があります。Skype for Business Server 2019 か、または Skype for Business Server 2015 用の CU8 が必要になります。 オンプレミスの Skype for Business Server を使用しているユーザーの場合、TeamsUpgradePolicy のオンラインインスタンスの mode プロパティは有効ですが、NotifySfbUsers プロパティは無視されます。 通知が必要な場合は、クライアントの動作を制御するために、オンプレミスの TeamsUpgradePolicy のインスタンスを作成する必要があります。 

オンプレミスの PowerShell ウィンドウで、TeamsUpgradePolicy の新しいインスタンスを作成し、次のようにして NotifySfbUsers=true に設定します。

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

次に、同じオンプレミスの PowerShell ウィンドウを使用して、その新しいポリシーを目的のユーザーに割り当てます。

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>会議の移行

ユーザーが TeamsOnly に移行されると、既定では、そのユーザーによって開催された既存の Skype for Business 会議は Teams に変換されます。 この規定の動作は、ユーザーに TeamsOnly モードを割り当てる際に必要に応じて無効にできます。 ユーザーをオンプレミスから移行する場合、そのオンライン ユーザー アカウントで機能するように会議をクラウドに移行する必要がありますが、-MoveToTeams を指定していない場合、その会議は Skype for Business 会議として移行され、Teams には変換されません。 

TeamsOnly モードをテナント レベルで割り当てる場合は、どのユーザーに対しても会議の移行はトリガーされません。 テナント レベルで TeamsOnly モードを割り当てて会議を移行する場合は、PowerShell を使用してテナント内のユーザーのリストを取得し (必要なフィルターを指定して Get-CsOnlineUser を使用するなど)、その後に、それらのユーザーそれぞれにループ処理を実行して、Start-CsExMeetingMigration を使用して会議の移行をトリガーできます。 詳細については、「[Meeting Migration Service (MMS) の使用](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)」を参照してください。



## <a name="related-links"></a>関連リンク

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md) 

[Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を構成する](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[オンプレミスとクラウドの間でユーザーを移動する](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[会議移行サービス (MMS) を使用する](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

