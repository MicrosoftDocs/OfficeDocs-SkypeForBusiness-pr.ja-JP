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
description: 動的メンバーシップMicrosoft Teams使用して、Microsoft 365 グループに関連付けられているチームをサポートする方法について説明します。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3a18e2cbe1a34fe78f5e84b4df4ae9a95c46fd9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613636"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>チームの動的なメンバーシップの概要

Microsoft Teamsは *、動的メンバーシップ* を使用して、Microsoft 365 グループに関連付けられているチームをサポートします。 動的メンバーシップを使用すると、Azure Active Directory (Azure AD) 内の特定のユーザー属性をチェックする 1 つ以上のルールによってチームのメンバーシップを定義できます。 ユーザー属性が変更されたり、ユーザーがテナントに参加して退出したりすると、ユーザーは自動的に適切なチームに追加または削除されます。

動的メンバーシップを使用すると、組織内の特定のユーザーのコーホートに対してチームを設定できます。 考えられるシナリオは次のとおりです。
- 病院は、看護師、医師、および医師が通信をブロードキャストするための個別のチームを作成できます。 これは、病院が派遣社員に依存している場合に特に重要です。
- 大学は、特定の大学内のすべての教職員のチームを作成できます。これには、頻繁に変更される非常勤の教員も含まれます。
- 航空会社は、(シカゴからアトランタへの火曜日の午後の非停止など) フライトごとにチームを作成し、必要に応じて頻繁に変更されるフライト のスタッフを自動的に割り当てたり削除したりしたいと考えています。

この機能を使用すると、特定のチームのメンバーは、メンバーシップを手動で管理するのではなく、特定の条件のセットに基づいて自動的に更新されます。 これを行うには、テナントと管理者アカウントを持っている場合、Azure AD Premium P1ライセンスとチーム メンバーシップをテナント管理者が任意のユーザーのAzure ADプロパティに[割り当て](/azure/active-directory/users-groups-roles/groups-dynamic-membership)ることができる必要があります。

Microsoft Teamsは、チームのMicrosoft 365 グループで動的メンバーシップの変更を反映するために、数分から最大 2 時間かかる場合があります。

動的グループでチームを使用する場合:

- ルールでは、チーム メンバーは誰か定義できますが、チームの所有者は定義できません。
- メンバーは動的グループ ルールによって定義されているため、所有者はチームのメンバーとしてユーザーを追加または削除できません。
- Teams クライアントは、チームのメンバー管理を許可しません。 メンバーの追加、メンバー ロールの編集、参加要求の送信と承認、チームからの退出を行うオプションはすべて非表示になります。

動的メンバーシップを使用するチームを作成するには、まず[動的なMicrosoft 365 グループを作成](/azure/active-directory/users-groups-roles/groups-create-rule)してから、[そのグループからチームを作成](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)します。

既存のチームを動的メンバーシップに変更できます。 詳細については、「[Azure Active Directoryの静的グループ メンバーシップを動的に変更](/azure/active-directory/users-groups-roles/groups-change-type)する」を参照してください。

## <a name="related-topics"></a>関連項目

[Microsoft Teams の制限事項と仕様](limits-specifications-teams.md)

[Azure Active Directory内のグループの動的メンバーシップ 規則](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
