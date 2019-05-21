---
title: Microsoft Teams でプライベート チームの検索を管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 4/25/2019
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: チームギャラリーと検索結果の提案を通じて、プライベートチームを Microsoft Teams ユーザーが検出できるかどうかを制御する方法について説明します。
ms.openlocfilehash: 55f127ff4dc9e5e0926e606c141b78f65c799de0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304403"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a>Microsoft Teams でプライベート チームの検索を管理する

> [!INCLUDE [preview feature](includes/preview-feature.md)] 

管理者とチーム所有者は、組織内の Microsoft Teams ユーザーがプライベートチームを検出できるかどうかを制御できます。 プライベートチームが検出可能になると、検索結果として表示され、チームギャラリーの候補には Teams の公開チームと共に含まれます。 これにより、ユーザーは参加するプライベートチームを簡単に検索して見つけることができます。 ユーザーは、チーム所有者が承認または拒否できるプライベートチームへの参加を要求できます。

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a>チーム内のパブリックチーム、プライベートチーム、および探索の概要

ほとんどの組織には、次のような種類のチームがあります。パブリックチーム、見つけやすいプライベートチーム、非検出可能なプライベートチームがあります。

![チームギャラリー](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a>パブリックチーム

パブリックチームは、組織内のすべてのユーザーが参加できるようにすることができます。 パブリックチームは teams ギャラリーの全員に表示され、ユーザーはチーム所有者から承認を得ることなくパブリックチームに参加することができます。 パブリックチームの例としては、技術について話し合うチーム、dogfood の製品のフィードバックを得るためのチーム、およびユーザーが使用するチームのチームが含まれます。

### <a name="discoverable-private-teams"></a>検出可能なプライベートチーム

検出可能なプライベートチームを参加できるのは、チーム所有者がそのメンバーにユーザーを追加した場合のみです。 プライベートチームを見つけられるようにすると、チームギャラリーのおすすめチームと検索結果のリストにチームが含まれます。 組織内のすべてのユーザーが知っている、またはチーム内のファイルへのアクセスを管理する必要があるという、組織内のプロジェクトとグループに、検出可能なプライベートチームを使用します。 例としては、人事部門のチーム、組織のすべての管理者のチーム、マネージャーと直属の部下のチームなどがあります。

### <a name="non-discoverable-private-teams"></a>非検出可能なプライベートチーム

非検出可能なプライベートチームは、チーム所有者がそのメンバーにユーザーを追加した場合にのみ参加することができます。 プライベートチームを見つけることができない場合は、おすすめチームの一覧に表示されず、teams ギャラリーの検索結果から削除されます。 検出不能なチームを使用して、機密性の高い機密のトピックで共同作業を行います。 例としては、組織の戦略的方向性の変化について話し合うために、今後の買収とチームに相談するチームが挙げられます。

## <a name="set-whether-new-private-teams-are-discoverable"></a>新しいプライベートチームが検出可能であるかどうかを設定する

チーム所有者は、チームの検出設定を構成することにより、チーム所有者がプライベートチームを作成して検出できるようにすることができます。 既定では、新しいプライベートチームは検索可能であり、見つけることができます。 チーム所有者が検索結果と候補にプライベートチームを表示しないようにする場合は、**このチーム**の隣にある [**設定の変更**] を選択して、この設定をオフにすることができます。

![新しいプライベートチームの検出設定](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a>既存のプライベートチームが検出可能であるかどうかを設定する

チーム所有者は、既存のプライベートチームの検出設定をチーム設定で直接設定できます。また、管理者は PowerShell を使用してこれを行うことができます。

### <a name="in-team-settings"></a>チームの設定

Teams で、プライベートチームに移動し、[**その他のオプション̇̇̇** > **管理チーム**] をクリックします。 [**設定**] タブで、[**チーム探索**] を展開し、[検出**を有効にする**] チェックボックスをオフまたはオンにします。

![既存のプライベートチームの検出設定](media/private-team-discovery-existing-team.png)

### <a name="using-powershell-coming-soon"></a>PowerShell を使用する (近日公開)

**Set-Team**コマンドレットを使用して、既存のプライベートチームの検出設定をオンまたはオフにします。 チームを検出できるようにする方法の例を次に示します。

    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInSearchAndSuggestions $true
スクリプトでこのコマンドレットを使用して、既存のプライベートチームの検出設定を一括で設定することができます。

## <a name="set-whether-users-can-discover-private-teams"></a>ユーザーがプライベートチームを検出できるようにするかどうかを設定する

管理者として、組織内のどのユーザーが検索結果やチームの候補でプライベートチームを見つけられるかを管理することもできます。 **新しい-CsTeamsChannelsPolicy**コマンドレットを使用してポリシーを作成し、ユーザーにポリシーを割り当てます。
 
ポリシーを割り当てられたユーザーが検索結果と提案で検出可能なプライベートチームを表示できるようにするには、 **Allowprivateteamdiscovery**パラメーターを**true**に設定します。 **Allowprivateteamdiscovery**パラメーターを**false**に設定すると、検索結果およびポリシーが割り当てられたユーザーの候補から、検出可能なプライベートチームがすべて削除されます。

既定では、組織内のすべてのユーザーに対して**Allowprivateteamdiscovery**が**true**に設定されます。

この例では、VendorPolicy という名前のポリシーを作成して、ユーザーが検出可能なプライベートチームを検出できないようにします。次に、vendoruser1 という名前のユーザーにポリシーを割り当てます。 
   
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy

> [!NOTE]
> 検出されないプライベートチームは、ポリシーの設定に関係なく、検索結果と候補には表示されません。 たとえば、プライベートチームの検出設定を無効にした場合、そのユーザーのポリシー設定で**Allowprivateteamdiscovery**パラメーターが**true**に設定されているにもかかわらず、ユーザーはチームを見つけることができません。

## <a name="related-topics"></a>関連トピック
- [Teams での PowerShell の概要](teams-powershell-overview.md)