---
title: チームの動的なメンバーシップの概要
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: 動的メンバーシップを使用して、microsoft Teams が Microsoft 365 グループに関連付けられているチームをサポートする方法について説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75bd058d79b1f54a40ad0e42207178c9c29d08cd
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583926"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>チームの動的なメンバーシップの概要

Microsoft Teams では、*動的メンバーシップ*を使用して、microsoft 365 グループに関連付けられているチームをサポートしています。 動的メンバーシップによって、Azure Active Directory (Azure AD) で特定のユーザー属性を確認する1つ以上のルールによって、チームのメンバーシップを定義できます。 ユーザー属性の変更またはユーザーの参加とテナントの脱退の際に、ユーザーは適切なチームに追加または削除されます。

動的メンバーシップを使用して、組織内の特定のユーザーの cohorts に対して teams を設定することができます。 次のようなシナリオが考えられます。
- 病院は、看護師、医師、surgeons のために個別のチームを作成して、コミュニケーションをブロードキャストすることができます。 これは、病院が temp 従業員に依存している場合に特に重要です。
- 大学では、adjunct 教職員など、特定の大学のすべての教職員のチームを作成できます。
- 航空会社は、各フライト (たとえば、シカゴからアトランタまでの火曜日の午後) のチームを作成し、必要に応じて、頻繁に変更されるフライトクルーが自動的に割り当てまたは削除されるようにしたいと考えています。

この機能を使用すると、メンバーシップを手動で管理する代わりに、特定の条件セットに基づいて、特定のチームメンバーが自動的に更新されます。 この操作を行うには、Azure AD Premium P1 ライセンスが必要です。また、テナント管理者がテナントと管理者のアカウントを持っている場合は、[テナント管理者](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)がそのユーザーの Azure ad プロパティにチームメンバーシップを割り当てることができます。

Microsoft Teams では、チームの Microsoft 365 グループに対して有効にした後、動的メンバーシップの変更が反映されるまでに数分から最大2時間かかることがあります。

> [!NOTE]
> - ルールでは、チームメンバーになっているユーザーを定義できますが、チーム所有者とは限りません。
> - チームおよびチャネルサイズの現在の制限については、「 [Microsoft Teams の制限と仕様](limits-specifications-teams.md)」を参照してください。
> - メンバーは動的なグループルールによって定義されるため、所有者は、ユーザーをチームのメンバーとして追加または削除することはできません。
> -    メンバーは、動的グループによってバックアップされたチームを脱退することはできません。

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a>動的メンバーシップを使用した Microsoft 365 グループの作成と管理

テナント管理者としてログインしているときに、「[動的グループを作成する」と「状態を確認](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)する」の手順に従います。 必要に応じて、「 [Azure Active Directory のグループの動的メンバーシップの規則」](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)を参照してください。

## <a name="create-a-new-team-with-your-microsoft-365-group"></a>Microsoft 365 グループを使用して新しいチームを作成する

次に、「[既存のグループからチームを作成](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)する」の説明に従って、メンバーシップの変更を有効にして新しいチームを作成します。

## <a name="apply-dynamic-membership-to-an-existing-team"></a>既存のチームに動的メンバーシップを適用する

「 [Azure Active Directory で静的グループメンバーシップを動的に変更](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)する」で説明されているように、既存のチームを取得して動的なメンバーシップを持つように変更することもできます。

## <a name="changes-in-client-behavior"></a>クライアントの動作の変更

チームの動的メンバーシップを有効にすると、チームクライアントはチームのメンバー管理を許可しなくなります。 メンバーの追加、メンバーの役割の編集、参加要求の送信と承認、チームの脱退はすべて非表示にするオプション。
