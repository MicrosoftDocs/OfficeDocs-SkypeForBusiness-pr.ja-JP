---
title: 管理単位を使用してデバイスを管理する
author: mahoffman
ms.author: serdars
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teamsで管理単位を使用する方法について説明します
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63579e7e9b6b2f7a7456349c489d4f544eb67cc1
ms.sourcegitcommit: 9e868a155bcd20dd5dafdedcff091ff77ca7398b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64584312"
---
# <a name="manage-devices-in-the-teams-admin-center-with-administrative-units"></a>管理単位を使用してTeams管理センターでデバイスを管理する

Teams管理センターの管理単位は、Teams デバイスを管理するための詳細なロールベースのアクセスを提供します。 管理単位はTeams特定のリソースへの管理者アクセスを許可しますが、その管理者の他のリソースへのアクセスを制限します。 これは、さまざまな国または地域にローカル Teams管理者がいる場合に特に役立ちます。

たとえば、Contoso は世界中で操作を行っています。 Alice はロンドンに拠点を置くグローバル IT 管理者であり、Prashant はインドのバンガロールに拠点を置くローカルの IT 管理者です。 現在、Prashant がデバイス管理者としてTeams管理センターにサインインすると、世界中のデバイスTeams表示できます。 Alice は、プラシャネットのTeamsデバイスへのアクセスを、バンガルールでのみ制限したいと考えています。 管理単位では、これを行うことができます。 詳細については、「[Azure Active Directoryの管理単位](/azure/active-directory/roles/administrative-units)」を参照してください。

> [!NOTE]
> 現在、管理ユニットは、Teams デバイス管理者ロールでのみTeams管理センターで使用できます。

## <a name="add-administrative-units"></a>管理単位を追加する

管理単位を追加するには、グローバル管理者である必要があります。 方法については、「 [管理単位の追加」を](/azure/active-directory/roles/admin-units-manage#add-an-administrative-unit)参照してください。

## <a name="assign-admins-to-administrative-units"></a>管理者を管理単位に割り当てる

また、管理単位を割り当てるには、グローバル管理者である必要があります。 管理単位は、Azure portal、PowerShell、または Microsoft Graph APIを使用して割り当てることができます。 詳細については、「[管理単位スコープを使用してAzure ADロールを割り当てる](/azure/active-directory/roles/admin-units-assign-roles)」を参照してください。

## <a name="select-administrative-units"></a>管理単位を選択する

Teams デバイス管理者の場合は、グローバル管理者が管理者ユニットに割り当てた後、Teams管理センターにサインインしてデバイスを管理できます。 1 つの管理ユニットにのみ割り当てられている場合は、その管理ユニットに割り当てられているデバイスのみが表示されます。 複数の管理単位に割り当てられている場合は、Teams管理センターからサインアウトすることなく、それらの管理単位を切り替えることができます。 

1. [Teams管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)にサインインします。

2. [ **管理単位** ] ダイアログ ボックスで、次のいずれかの手順に従います。
    - 管理する管理単位を選択するか、または 
    - 組織 **のすべてのデバイス** を管理するアクセス許可がある場合は、[すべてのデバイス] を選択します。

3. **[保存]** を選択します。

## <a name="switch-administrative-units"></a>管理単位を切り替える

Teams デバイス管理者の場合は、Teams管理センターにサインインしている場合は、管理単位を切り替えることができます。 別の管理単位に切り替えるには、

1. [Teams管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)にサインインします。

2. 左側のナビゲーションで、**Teamsデバイス** を選択します。

3. 右側のウィンドウの左上で、表示されている管理単位を選択します。

4. [ **管理単位** ] ダイアログ ボックスで、次のいずれかの手順に従います。
    - 管理する管理単位を選択するか、または 
    - 組織 **のすべてのデバイス** を管理するアクセス許可がある場合は、[すべてのデバイス] を選択します。

5. **[保存]** を選択します。

## <a name="related-topics"></a>関連項目

- [管理単位にユーザーまたはグループを追加する](/azure/active-directory/roles/admin-units-members-add)
