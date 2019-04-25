---
title: マイクロソフトのチームでの秘密のチームの検索を管理します。
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 4/25/2019
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: プライベート チームをチームのギャラリーおよび検索結果内の提案をマイクロソフトのチームのユーザーが検出できるかどうかを制御する方法について説明します。
ms.openlocfilehash: 70d5b81bba719a9e6cc6a51d38d58fd309e07a3b
ms.sourcegitcommit: 9329d740a2060f9c055c5c0c03107a9268c0df5b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "33262763"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a>マイクロソフトのチームでの秘密のチームの検索を管理します。

管理者とチームの所有者は、マイクロソフトのチームのユーザーが組織内でプライベート チームを検出できるかどうかを制御できます。 プライベート チームが検出すると、検索結果に表示し、チーム内のパブリックのチームと共にチームのギャラリーで提案に含まれています。 これによりのプライベート チームに参加するを検索するを容易にします。 チームの所有者を承認または拒否できますし、プライベート チームに参加するユーザーを要求できます。

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a>チームのパブリック、プライベート チームは、チーム内の探索の概要

組織には、次のようなチームのチームの公開、検出可能なプライベート チーム、および検出可能ではないプライベート チームがあります。

![チーム ギャラリー](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a>パブリック チーム

パブリックのチームは、参加するのには、組織内のすべてのユーザーに使用できます。 パブリックのチームは、チームのギャラリー内のすべてのユーザーに表示し、チームの所有者の承認を得ることがなくユーザーがパブリックのチームに参加できます。 パブリック チームの例には、テクノロジー、製品、ドッグフードのフィードバックを取得するためのチームとチームの作業をユーザー設定することでニュースを説明するためのチームが含まれます。

### <a name="discoverable-private-teams"></a>検出可能なプライベート ・ チーム

検出可能なプライベート チームは、チーム所有者がそれらにユーザーを追加するときのみ結合できます。 プライベート チームを検出可能にすると、候補のチームとチームのギャラリーでの検索結果の一覧で、チームが含まれます。 プロジェクトとチーム内のファイルを制御する必要があります、すべてのユーザーを認識しており、会話へのアクセスを組織内のグループの検出可能なプライベート チームを使用します。 など、人事部のチーム、組織のマネージャーにすべてのチームとチームのマネージャーと、直属の部下。

### <a name="non-discoverable-private-teams"></a>非検出が可能なプライベート ・ チーム

非検出のプライベート チームを結合するにはチームの所有者にするユーザーを追加するときです。 プライベート チームをしない検出可能にすると、提案されたチームのリストから非表示になってので、チームのギャラリーでの検索結果から削除ください。 機密および機密度の高いトピックを共有するには、検出可能ではないチームを使用します。 例としては、今後取得を説明するためのチームや組織の戦略的方向性の変更を説明するためのチームです。

## <a name="set-whether-new-private-teams-are-discoverable"></a>新しいプライベート チームが検出可能であるかどうかを設定します。

チームの所有者は、プライベート チームを作成するときは、チームの検出設定を構成することで見つけやすいように選択できます。 既定では、新しいプライベート チームは、検索で見つけやすいです。 チームの所有者に、検索結果と推奨事項表示するのにはプライベート チームが希望しない場合は場合、は、**このチームは検索で見つけやすい**の横にある **[設定の変更**を選択して設定を無効にできます。

![新しいプライベート チームの探索の設定](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a>既存のプライベート チームが検出可能であるかどうかを設定します。

PowerShell を使用して行うことができます管理者とチームの所有者は、チームの設定で直接既存のプライベート チームの探索の設定を設定できます。

### <a name="in-team-settings"></a>チームの設定で

プライベート チームにはチームで、**複数のオプションの ˙˙˙**をクリックして > **チームを管理**します。 [**設定**] タブで、展開**チームの探索**とし、オンまたはオフ**の検出を有効にする**] チェック ボックスをオンします。

![既存のプライベート チームの探索の設定](media/private-team-discovery-existing-team.png)

### <a name="using-powershell"></a>PowerShell を使用します。

**セット チーム**コマンドレットを使用して、オフにするか、既存のプライベート チームの探索の設定をオンにします。 チームを検出可能にする方法の例を以下に示します。

    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInSearchAndSuggestions $true
大量の既存のプライベート チームの検出設定を設定するのには、スクリプト内でこのコマンドレットを使用できます。

## <a name="set-whether-users-can-discover-private-teams"></a>プライベート チームを見つけることができるかどうかを設定します。

管理者として、組織内のどのユーザーが検索結果にプライベート チームとチームの候補を検出できるを制御することもできます。 **新規 CsTeamsChannelsPolicy**コマンドレットを使用してポリシーを作成し、ユーザーにポリシーを割り当てます。
 
に**true を指定**して、検索結果と推奨事項のプライベート チームで検出可能なポリシーが割り当てられているユーザーを許可するには、 **AllowPrivateTeamDiscovery**パラメーターを設定します。 検索結果と、ポリシーが割り当てられているユーザーの意見から検出可能なすべてのプライベート チームを削除する**AllowPrivateTeamDiscovery**パラメーターを**false**に設定します。

既定では、 **AllowPrivateTeamDiscovery**は**true**組織内のすべてのユーザーに設定します。

この例では、発見可能な状態で行われるすべてのプライベート チームを検出できないようにする VendorPolicy をという名前のポリシーを作成し、vendoruser1 をという名前のユーザーにポリシーを割り当てることです。 
   
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy

> [!NOTE]
> 検索結果やご提案、ポリシーの設定で、検出可能ではないプライベート チームを表示しません。 たとえば、プライベート チームの探索の設定をオフにする場合ユーザーは、チームを発見することに**は true**これらのユーザー ポリシーの設定で、 **AllowPrivateTeamDiscovery**パラメーターが設定されていても。

## <a name="related-topics"></a>関連トピック
- [Teams での PowerShell の概要](teams-powershell-overview.md)