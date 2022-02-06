---
title: 管理単位でデバイスを管理する
author: mahoffman
ms.author: serdars
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 管理単位を使用する方法については、Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
  - NOCSH
ms.collection:
  - M365-collaboration
appliesto:
  - Microsoft Teams
---

# <a name="manage-devices-in-the-teams-admin-center-with-administrative-units"></a>管理ユニットを使用Teams管理センターでデバイスを管理する

管理センターの管理Teams、デバイスを管理するための詳細なロールベースのアクセスTeamsされます。 管理単位は、Teamsリソースへのアクセス権を付与しますが、その管理者のアクセス権を他のリソースに制限します。 これは、さまざまな国または地域のローカル管理者Teams場合に特に役立ちます。

たとえば、Contoso は世界中で業務を行っています。 Alice はロンドンに拠点を置くグローバル IT 管理者ですが、Prashant はインドのラビレに拠点を置くローカル IT 管理者です。 現在、Prashant はデバイス管理者として Teams 管理センターにサインインすると、世界中のTeamsデバイスを確認できます。 Alice は、Prashant のデバイスへのアクセスを、Teamsでのみ制限したいと思っています。 管理単位を使用すると、この操作を実行できます。 詳細については、「管理単位」[を参照Azure Active Directory](/azure/active-directory/roles/administrative-units)。

> [!NOTE]
> 現在、管理ユニットは、Teamsデバイス管理者ロールに対Teams管理センターで使用できます。

## <a name="add-administrative-units"></a>管理単位を追加する

管理単位を追加するには、グローバル管理者である必要があります。 方法については、「管理単位を [追加する」を参照してください](/azure/active-directory/roles/admin-units-manage#add-an-administrative-unit)。

## <a name="assign-admins-to-administrative-units"></a>管理者を管理単位に割り当てる

管理単位を割り当てるには、グローバル管理者である必要があります。 管理単位は、Azure portal、PowerShell、または Microsoft Graph API を使用して割り当てできます。 詳細については、「管理単位スコープを[持つAzure ADロールを割り当てる」を参照してください](/azure/active-directory/roles/admin-units-assign-roles)。

## <a name="select-administrative-units"></a>管理単位の選択

Teams デバイス管理者の場合は、グローバル管理者が管理単位に割り当て後、Teams 管理センターにサインインしてデバイスを管理できます。 1 つの管理単位にのみ割り当てられている場合は、その管理単位に割り当てられているデバイスだけが表示されます。 複数の管理単位に割り当てられている場合は、管理センターからサインアウトすることなく、それらの管理単位Teamsできます。 

1. 管理センターに[Teamsします](https://go.microsoft.com/fwlink/p/?linkid=2024339)。

2. [管理 **単位] ダイアログ ボックス** で、次のいずれかの手順に従います。
    - 管理する管理単位を選択するか、 
    - 組織 **のすべてのデバイスを** 管理する権限がある場合は、[すべてのデバイス] を選択します。

3. **[保存]** を選択します。

## <a name="switch-administrative-units"></a>管理単位の切り替え

デバイス管理者Teams、管理センターにサインインしている場合は、管理単位Teamsできます。 別の管理単位に切り替える場合:

1. 管理センターに[Teamsします](https://go.microsoft.com/fwlink/p/?linkid=2024339)。

2. 左側のナビゲーションで、[デバイスのTeams **選択します**。

3. 右側のウィンドウの左上で、表示される管理単位を選択します。

4. [管理 **単位] ダイアログ ボックス** で、次のいずれかの手順に従います。
    - 管理する管理単位を選択するか、 
    - 組織 **のすべてのデバイスを** 管理する権限がある場合は、[すべてのデバイス] を選択します。

5. **[保存]** を選択します。
