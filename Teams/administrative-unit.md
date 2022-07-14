---
title: 管理単位を使用してデバイスを管理する
author: CarolynRowe
ms.author: crowe
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams で管理単位を使用する方法について説明します
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5afbc4acd33acf7e950218e7cf2e30383b3b1d12
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790432"
---
# <a name="manage-devices-in-the-teams-admin-center-with-administrative-units"></a>管理単位を使用して Teams 管理センターでデバイスを管理する

Teams 管理センターの管理単位では、Teams デバイスを管理するためのロールベースの詳細なアクセス権が提供されます。 管理ユニットは、Teams に特定のリソースへのアクセス権を付与しますが、その管理者の他のリソースへのアクセスを制限します。 これは、異なる国または地域にローカル Teams 管理者がいる場合に特に役立ちます。

たとえば、Contoso は世界中で操作を行っています。 Alice はロンドンに拠点を置くグローバル IT 管理者であり、Prashant はインドのバンガロールに拠点を置くローカルの IT 管理者です。 現在、Prashant がデバイス管理者として Teams 管理センターにサインインすると、世界中の Teams デバイスを確認できます。 Alice は、プラシャネットの Teams デバイスへのアクセスを、バンガルールでのみ制限したいと考えています。 管理単位では、これを行うことができます。 詳細については、「 [Azure Active Directory の管理単位」を](/azure/active-directory/roles/administrative-units)参照してください。

> [!NOTE]
> 管理ユニットは現在、Teams デバイス管理者ロールでのみ Teams 管理センターで使用できます。

## <a name="add-administrative-units"></a>管理単位を追加する

管理単位を追加するには、グローバル管理者である必要があります。 方法については、「 [管理単位の追加」を](/azure/active-directory/roles/admin-units-manage#add-an-administrative-unit)参照してください。

## <a name="assign-admins-to-administrative-units"></a>管理者を管理単位に割り当てる

また、管理単位を割り当てるには、グローバル管理者である必要があります。 管理単位は、Azure portal、PowerShell、または Microsoft Graph APIを使用して割り当てることができます。 詳細については、「 [管理ユニット スコープを使用して Azure AD ロールを割り当てる](/azure/active-directory/roles/admin-units-assign-roles)」を参照してください。

## <a name="select-administrative-units"></a>管理単位を選択する

Teams デバイス管理者の場合は、グローバル管理者が管理者ユニットに割り当てた後、Teams 管理センターにサインインしてデバイスを管理できます。 1 つの管理ユニットにのみ割り当てられている場合は、その管理ユニットに割り当てられているデバイスのみが表示されます。 複数の管理単位に割り当てられている場合は、Teams 管理センターからサインアウトすることなく、それらの管理単位を切り替えることができます。 

1. [Teams 管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)にサインインします。

2. [ **管理単位** ] ダイアログ ボックスで、次のいずれかの手順に従います。
    - 管理する管理単位を選択するか、または 
    - 組織 **のすべてのデバイス** を管理するアクセス許可がある場合は、[すべてのデバイス] を選択します。

3. **[保存]** を選択します。

## <a name="switch-administrative-units"></a>管理単位を切り替える

Teams デバイス管理者の場合は、Teams 管理センターにサインインしている場合は、管理単位を切り替えることができます。 別の管理単位に切り替えるには、

1. [Teams 管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)にサインインします。

2. 左側のナビゲーションで、[ **Teams デバイス**] を選択します。

3. 右側のウィンドウの左上で、表示されている管理単位を選択します。

4. [ **管理単位** ] ダイアログ ボックスで、次のいずれかの手順に従います。
    - 管理する管理単位を選択するか、または 
    - 組織 **のすべてのデバイス** を管理するアクセス許可がある場合は、[すべてのデバイス] を選択します。

5. **[保存]** を選択します。

## <a name="related-topics"></a>関連項目

- [管理単位にユーザーまたはグループを追加する](/azure/active-directory/roles/admin-units-members-add)
