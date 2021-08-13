---
title: オンプレミスのデプロイからTeamsアップグレードSkype for Businessツール
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 新しいバージョンからアップグレードSkype for BusinessツールTeams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5465267309966ccaa4806db094e70eb02f8c5aebd9e72e4ea9de00610bac1417
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319650"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>IT 管理者向け Teams &mdash; アップグレードするためのツール

この記事では、アプリケーションからアプリケーションにアップグレードするためのTeamsについてSkype for Business。 

アップグレードを開始する前に、アップグレードの重要な概念と共存動作について説明する次の記事をお勧めします。

- [Teams と Skype for Business の共存](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [共存モード - リファレンス](migration-interop-guidance-for-teams-with-skype.md)
- [Teams のクライアント エクスペリエンスおよび共存モードへの準拠](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a>アップグレードの管理ツール

どのアップグレード方法を選択する場合でも、Skype for Business Online を既に持っているユーザーの場合は[、TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)を使用して TeamsOnly への移行を管理し、ユーザーの共存モードを制御します。 Skype for Business Server にオンプレミス アカウントを持つユーザーの場合は、 を使用してクラウド `Move-CsUser` [に移動することもできます](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)。  各モードの詳細については、「[共存モード](migration-interop-guidance-for-teams-with-skype.md)」を参照してください。

> [!NOTE]
> 現在、Skype for Business Online Connector を使用してサービスを管理している場合は、Teams PowerShell モジュールに移動し、既存の PowerShell スクリプトを更新する必要があります。 詳細[については、「Skype for Business Online Connector から powerShell モジュールTeamsに移動する」](teams-powershell-move-from-sfbo.md)を参照してください。

Skype for Business モードを使用して選択機能の切り替えを実行する場合でも、既定の Islands 構成から TeamsOnly モードにアップグレードする場合でも、TeamsUpgradePolicy が主なツールです。他のポリシーと同様Teams TeamsUpgradePolicy をユーザーに直接割り当てできます。 また、テナント全体の既定値としてポリシーを設定できます。 ユーザーへの割り当ては、テナントの既定の設定よりも優先されます。  ポリシーは、Teams PowerShell で管理できます。

TeamsOnly モードを除く、TeamsUpgradePolicy の任意のモードを、オンプレミスの Skype for Businessに割り当てできます。 逆に、クラウドにホームされているユーザーには、TeamsOnly モードのみを割り当てることができます。 **TeamsOnly** モードは、クラウドに既にホームされているユーザーにのみ割り当てることができます。これは、Skype for Business ユーザーおよび Microsoft 365 電話システム 機能との相互運用とフェデレーションは、ユーザーが Skype for Business Online にホームされている場合にのみ可能です。  さらに、Skype for Business オンプレミスデプロイ (Office 365 以外の場所を示す lyncdiscover DNS レコードの存在によって検出される) がある場合は、テナント全体の既定値として **TeamsOnly** モードを割り当てできません。 詳細については、「ハイブリッド構成[を無効にする」を参照して、](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid)移行のみをTeamsしてください。

オンプレミスにSkype for Businessアカウントを持つユーザーは、Teams[](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)オンプレミス ツールセットの Move-CsUser を使用して、Skype for Business モードにオンラインで移動する必要があります。 

他のポリシーとは異なり、TeamsUpgradePolicy の新しいインスタンスを Microsoft 365 または Office 365。 既存のインスタンスはすべて、このサービスに組み込まれています。  (モードは、TeamsUpgradePolicy 内のプロパティであり、ポリシー インスタンスの名前ではありません)。ポリシー インスタンスの名前がモードと同一である場合もありますが、必ず一致するわけではありません。 特に、ユーザーに TeamsOnly モードを割り当てる場合は、TeamsUpgradePolicy の UpgradeToTeams インスタンスをそのユーザーに付与します。 すべてのインスタンスの一覧を表示するには、次のコマンドを実行します。

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

オンライン ユーザーを TeamsOnly モードにアップグレードするには、次のようにして UpgradeToTeams インスタンスを割り当てます。 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

オンプレミスの Skype for Business ユーザーを TeamsOnly モードにアップグレードするには、次のようにしてオンプレミス ツールセットに含まれる Move-CsUser を使用します。

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -credential $cred
```

ユーザーごとに明示的に付与されているユーザー (その設定が優先される) を除くテナント内のすべてのユーザーのモードを変更するには、次のコマンドを実行します。

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>オンプレミスのアカウントを持つユーザー Skype for Business、テナント レベルで TeamsOnly モードを割り当てすることはできません。 Move-CsUser を使用して、これらのユーザー Teamsモードに個別に移動する必要があります。


## <a name="using-notifications-in-skype-for-business-clients"></a>Skype for Business クライアントで通知を使用する

管理者は、Skype for Business クライアントでエンド ユーザー通知を提供して、ユーザーがまもなく Teams にアップグレードされることを通知できます。次の図にサンプルを示します。 たとえば、管理者は、ユーザーのグループを TeamsOnly モードにアップグレードしようと考えている日の 1 週間前に、そのグループのユーザーに対する通知をオンにできます。 これらの通知は、TeamsUpgradePolicy のインスタンスを使用し、NotifySfbUsers=true に設定して有効にできます。  TeamsOnly 以外のすべてのモードでは、実際には、NotifySfbUsers の 2 つの値に対応する 2 つのインスタンスがモードごとに存在します。  TeamsOnly 以外のすべてのモードでは、実際には、NotifySfbUsers の 2 つの値に対応する 2 つのインスタンスがモードごとに存在します。 

![通知を示す図](media/teams-upgrade-sfb-with-notifications.png)

ユーザーが Skype for Business Online に所属している場合は、そのユーザーと同じモードを持つポリシー インスタンスを割り当てるだけです。ただし、NotifySfbUsers=true に設定します。 

ユーザーが Skype for Business Server オンプレミスに所属している場合は、オンプレミスのツールセットを使用する必要があります。Skype for Business Server 2019 か、または Skype for Business Server 2015 用の CU8 が必要になります。 Skype for Business Server オンプレミスにホームされているユーザーの場合、TeamsUpgradePolicy のオンライン インスタンスの mode プロパティが使用されますが、NotifySfbUsers プロパティは適用されません。 通知が必要な場合は、クライアントの動作を制御するために、TeamsUpgradePolicy のオンプレミス インスタンスを作成する必要があります。 

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

TeamsOnly モードをテナント レベルで割り当てる場合は、どのユーザーに対しても会議の移行はトリガーされません。 テナント レベルで TeamsOnly モードを割り当てて会議を移行する場合は、PowerShell を使用してテナント内のユーザーのリストを取得し (必要なフィルターを指定して Get-CsOnlineUser を使用するなど)、その後に、それらのユーザーそれぞれにループ処理を実行して、Start-CsExMeetingMigration を使用して会議の移行をトリガーできます。 詳細については、「[Meeting Migration Service (MMS) の使用](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)」を参照してください。



## <a name="related-links"></a>関連リンク

[共存モード - リファレンス](migration-interop-guidance-for-teams-with-skype.md) 

[Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を構成する](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[オンプレミスとクラウドの間でユーザーを移動する](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[会議移行サービス (MMS) を使用する](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
