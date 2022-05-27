---
title: IT 管​​理者向けのアップグレード戦略
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: この記事では、IT 管理者向けであり、Skype for BusinessからTeamsへのアップグレードを実装するための戦略について説明します。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f403b12ffc8cabbfebe8a30268eb3e6dad468f32
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681738"
---
# <a name="upgrade-strategies-for-it-administrators"></a>IT 管​​理者向けのアップグレード戦略

![「展開と実装」段階が強調表示された、アップグレード行程の各段階。](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")

この記事は、Skype for Business から Teams へのアップグレードを実装する IT 管理者向けです。

アップグレードを実装する前に、アップグレードの重要なコンセプトや共存動作について説明した以下の記事をお勧めします。

- [Microsoft Teams と Skype for Business の共存と相互運用性を理解する](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [共存モード - リファレンス](migration-interop-guidance-for-teams-with-skype.md)
- [Teams のクライアント エクスペリエンスおよび共存モードへの準拠](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>アップグレード方法

このセクションでは、以下のアップグレード方法の 1 つを利用したアップグレードの実装方法について説明します。

- [重複機能アップグレード (アイランド モードを使用)](#overlapping-capabilities-upgrade-using-islands-mode)
- [Teams をまだ使用し始めていない組織の選択的な機能アップグレード](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [Teams をアイランド モードで既に使用している組織の選択的な機能アップグレード](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

アップグレード方法に関する詳細情報が必要な場合は、「[Skype for Business から Teams へのアップグレード手順を選択する](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)」を既に読んでいることを確認してください。

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>重複機能アップグレード (アイランド モードを使用)

重複する機能のアップグレード方法については、以下のとおりです。

- 組織全体の迅速なアップグレードを行うことができる場合は、このオプションを検討します。  両方のクライアントを実行しているエンド ユーザーに混乱を招く可能性があるため、ユーザーが両方のクライアントを実行する必要がある期間を最小限に抑えることができる場合に最適です。 管理者は、両方のクライアントを実行することをユーザーに周知する必要があります。

- このオプションは既定のモデルであり、Microsoft 365またはOffice 365ライセンスを割り当てる以外は、Teamsを開始するための管理者の操作は必要ありません。 ユーザーが既に Skype for Business Online を使用している場合は、このモデルを既に使用している可能性があります。

- 重複機能モードから TeamsOnly に移行するのが困難な場合があります。 アップグレード済みのユーザーは Teams でのみ通信するため、そのユーザーと通信する組織内の他のユーザーはすべて Teams を使用する必要があります。  Teams を使用し始めていないユーザーがいる場合、メッセージを受け取れない可能性が生じます。 さらに、TeamsOnly ユーザーがオンラインでSkype for Businessに表示されることはありません。 これを回避するために、テナントのグローバル ポリシーを使用してテナント全体のアップグレードを実行する組織もありますが、これには事前に計画を立て、すべてのユーザーのアップグレード準備が整うまで待つ必要があります。

## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Teams をまだ使用し始めていない組織の選択的な機能アップグレード

Teams のアクティブなユーザーが 1 人もいない組織の場合、最初のステップとして、テナント全体に対する TeamsUpgradePolicy の既定のポリシーを、Skype for Business のモードの 1 つ (SfbWithTeamsCollab など) に設定します。  Teamsの使用を開始していないユーザーは、動作の違いに気付きません。 それでも、テナント レベルでこのポリシーを設定すると、TeamsOnly モードへのユーザーのアップグレードを開始でき、さらに、アップグレード済みユーザーはまだアップグレードしていないユーザーとの通信を行うことができます。  パイロット ユーザーを特定したら、それらのユーザーを TeamsOnly にアップグレードできます。  そのユーザーがオンプレミスの場合は、Move-CsUser を使用します。 そのユーザーがオンラインの場合は、Grant-CsTeamsUpgradePolicy を使用して、 TeamsOnly モードを割り当てます。 既定で、これらのユーザーによってスケジュールされている Skype for Business 会議は、Teams に移行されます。

主なコマンドを次に示します。

1. 次のようにして、テナント全体の既定値をモードの SfbWithTeamsCollab に設定します。

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. 次のようにして、パイロット ユーザーを TeamsOnly にアップグレードします。

   - オンラインのユーザーを TeamsOnly にアップグレードする場合は、以下のとおりです。

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username
     ```

   - オンプレミスのユーザーを TeamsOnly にアップグレードする場合は、以下のとおりです。

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
     ```

**注**:

- テナント全体のポリシーを SfbWithTeamsCollab に設定する代わりに、SfbWithTeamsCollabAndMeetings に設定することもできます。 そのようにすると、すべてのユーザーが新しい会議すべてを Teams でスケジュールするようになります。
- 既定で、TeamsOnly モードへのアップグレードや SfbWithTeamsCollabAndMeetings モードの割り当てを実行すると、Skype for Business 会議は Teams に移行されます。

> [!NOTE]
> Skype for Business Online が近日中に廃止されることに備えて、Microsoft は組織が Teams に移行する方法を簡素化しました。 オンプレミスから直接 TeamsOnly にユーザーを移動させるために、`Move-CsUser` に `-MoveToTeams` スイッチを指定する必要はなくなりました。 これまでは、このスイッチが指定されていない場合、ユーザーは Skype for Business Server オンプレミスのホームから Skype for Business Online に移行し、そのモードは変更されないままでした。 `Move-CsUser` でオンプレミスからクラウドにユーザーが移動すると、実際にスイッチが指定されているかどうかにかかわらず、`-MoveToTeams switch had been specified` の場合と同様に、ユーザーに TeamsOnly モードが自動的に割り当てられ、オンプレミスからの会議が Teams 会議に自動的に変換されるようになりました。 この動作は、すべてのバージョンの Skype For Business Server および Lync Server 2013 (`-MoveToTeams` をサポートしていませんでした) で利用できます。

次の図に、Teams をこれまでに使用していない組織の選択的な機能アップグレードの概念フェーズを示します。 バーの高さは、ユーザー数を表します。 アップグレードのどのフェーズでも、すべてのユーザーが相互に通信できます。  Skype for Business ユーザーは TeamsOnly ユーザーと相互運用を使用して通信します。逆の場合も同様です。 アイランド モードのユーザーは、必ず両方のクライアントを実行する必要があります。

![Teams を以前に使用していない場合の選択的な機能アップグレードを示す図。](media/teams-upgrade-1.png)

## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Teams をアイランド モードで既に使用している組織の選択的な機能アップグレード

組織内の一部のユーザーが Teams をアイランド モードでアクティブに使用している場合、既存のユーザーから機能を削除することは望ましくない場合があります。 その場合、テナント全体のポリシーを変更する前に、もう 1 つステップが必要になります。 解決策は、テナント全体のポリシーを SfbWithTeamsCollab に設定する前に、これらの既存のアクティブなTeams ユーザーをアイランド モードに "祖父" することです。  これを行うと、上記のように展開を続行できます。ただし、TeamsOnly に移行するユーザーのグループは 2 つあります。Teamsでアクティブだったユーザーはアイランド モードになり、残りのユーザーは SfbWithTeamsCollab モードになります。 管理者は、これらのユーザーを TeamsOnly モードに段階的に移行できます。

1. Teams でアクティブなユーザーを見つけるには、次のようにします。

   1. Microsoft 365 管理センターの左側のナビゲーションで、[レポート]、[使用状況] の順に移動します。
   2. [レポートの選択] ドロップダウンで、[Microsoft Teams]、[ユーザー アクティビティ] の順に選択します。 このようにすると、Teams でアクティブになっているユーザーのエクスポート可能なテーブルが提供されます。
   3. [エクスポート] をクリックして、Excel を開き、フィルタリングして、Teams でアクティブなユーザーのみを表示します。

2. ステップ 1 で見つかったアクティブな Teams ユーザーそれぞれに対して、リモート PowerShell でアイランド モードを割り当てます。 これにより、次の手順に進み、ユーザー エクスペリエンスを変更しないようにすることができます。

   ```PowerShell
   $users=get-content "C:\MyPath\users.txt"
    foreach ($user in $users){
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands}
   ```

3. テナント全体のポリシーを SfbWithTeamsCollab に設定します。

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab
   ```

4. 選択したユーザーを TeamsOnly モードにアップグレードします。ユーザーがアイランド モードの場合に生じる可能性のある混乱を最小限に抑えるため、アイランド モードのユーザーを優先的にまずアップグレードすることが望ましい場合もありますが、アイランド モードのユーザーと SfbWithTeamsCollab モードのユーザーのどちらをアップグレードするかは管理者が選択できます。

   Skype for Business Online に所属しているユーザーの場合:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams
   ```

   Skype for Business Server オンプレミスに所属しているユーザーの場合:

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
   ```

次の図に、アクティブなアイランド ユーザーが既に存在する場合の選択的な機能移行の概念フェーズを示します。 バーの高さは、ユーザー数を表します。 アップグレードのどのフェーズでも、すべてのユーザーが相互に通信できます。  Skype for Business ユーザーは TeamsOnly ユーザーと相互運用を使用して通信します。逆の場合も同様です。

![アイランド モードのアクティブなユーザーが存在する場合の選択的な機能アップグレードを示す図。](media/teams-upgrade-2.png)

## <a name="related-links"></a>関連リンク

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md)

[Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を構成する](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[オンプレミスとクラウドの間でユーザーを移動する](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[会議移行サービス (MMS) を使用する](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
