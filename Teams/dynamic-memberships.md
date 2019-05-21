---
title: チームの動的なメンバーシップの概要
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
description: AAD に基づく動的なチームメンバーシップについて説明します。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45e9da5b5bc9c1bb5800634d727bd6c9218812ab
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245416"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>チームの動的なメンバーシップの概要

Microsoft Teams は、動的メンバーシップを使用して、Office 365 グループに関連付けられているチームをサポートします。 動的メンバーシップによって、Azure Active Directory (AAD) で特定のユーザー属性を確認する1つ以上のルールによって、チームのメンバーシップを定義できます。 ユーザー属性の変更またはユーザーの参加とテナントの脱退の際に、ユーザーは適切なチームに追加または削除されます。

動的なメンバーシップを使用して、組織内の特定の cohorts ユーザーに対して teams をセットアップすることができます。 次のようなシナリオが考えられます。
- 病院は、看護師、医師、surgeons のために個別のチームを作成して、コミュニケーションをブロードキャストすることができます。 これは、病院が temp 従業員に依存している場合に特に重要です。
- 大学では、adjunct 教職員など、特定の大学のすべての教職員のチームを作成できます。
- 航空会社は、各フライト (たとえば、シカゴからアトランタまでの火曜日の午後) のチームを作成し、必要に応じて、頻繁に変更されるフライトクルーが自動的に割り当てまたは削除されるようにしたいと考えています。

この機能を使用すると、メンバーシップを手動で管理する代わりに、特定の条件セットに基づいて、特定のチームメンバーが自動的に更新されます。 この操作を行うには、Azure AD Premium P1 ライセンスが必要です。また、テナント管理者がテナントと管理者のアカウントを持っているユーザーの AAD プロパティに、チームメンバーシップを[割り当てる](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)ことができます。 

Microsoft Teams では、チームの Office 365 グループに反映された時点で動的メンバーシップの変更が反映されるまでに、数分から最大2時間かかることがあります。 

> [!NOTE]
> - ルールでは、チームメンバーになっているユーザーを定義できますが、チーム所有者とは限りません。
> - チームおよびチャネルサイズの現在の制限については、「 [Microsoft Teams の制限と仕様](limits-specifications-teams.md)」を参照してください。
> - メンバーは動的なグループルールによって定義されるため、所有者は、ユーザーをチームのメンバーとして追加または削除することはできません。
> - メンバーは、動的グループによってバックアップされたチームを脱退することはできません。


## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a>動的メンバーシップを使用して Office 365 グループを作成して管理する
テナント管理者としてログインしているときに、「[動的グループを作成する」と「状態を確認](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)する」の手順に従います。 必要に応じて、「 [Azure Active Directory のグループの動的メンバーシップの規則」](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)を参照してください。

## <a name="create-a-new-team-with-your-o365-group"></a>O365 グループを使用して新しいチームを作成する

次に、「 [Microsoft Teams で既存の Office 365 グループを強化](enhance-office-365-groups.md)する」の説明に従って、メンバーシップの変更を有効にして新しいチームを作成します。

## <a name="apply-dynamic-membership-to-an-existing-team"></a>既存のチームに動的メンバーシップを適用する

「 [Azure Active Directory で静的グループメンバーシップを動的に変更](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)する」で説明されているように、既存のチームを取得して動的なメンバーシップを持つように変更することもできます。

## <a name="changes-in-client-behavior"></a>クライアントの動作の変更

チームの動的メンバーシップを有効にすると、チームクライアントはチームのメンバー管理を許可しなくなります。 メンバーの追加、メンバーの役割の編集、参加要求の送信と承認、チームの脱退はすべて非表示にするオプション。
