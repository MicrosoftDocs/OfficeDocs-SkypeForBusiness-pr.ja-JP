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
description: 動的メンバーシップを使用Microsoft Teamsグループに関連付けられているチームMicrosoft 365サポートする方法について学習します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 74974f7b94a5d1bcadb340e132dae9e3b39a7704
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856326"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>チームの動的なメンバーシップの概要

Microsoft Teamsは、動的メンバーシップ を使用してMicrosoft 365グループに関連付けられている *チームをサポートします*。 動的メンバーシップを使用すると、チームのメンバーシップを 1 つ以上のルールで定義し、チーム内の特定のユーザー属性を確認Azure Active Directory (Azure AD)。 ユーザー属性が変わるか、ユーザーがテナントに参加して退出すると、ユーザーは自動的に正しいチームに追加または削除されます。

動的メンバーシップを使用すると、組織内のユーザーの特定のコーホートに対してチームを設定できます。 考えられるシナリオは次のとおりです。
- 病院では、通信をブロードキャストするために、看護師、医師、および病院用の個別のチームを作成できます。 これは、病院が一時従業員に依存している場合に特に重要です。
- 大学は、頻繁に変更される非常勤教員を含め、特定の大学内のすべての教職員のチームを作成できます。
- 航空会社は、各フライト (シカゴからアトランタへの火曜日の午後の非停止など) のチームを作成し、必要に応じて頻繁に変更されるフライト の乗務員を自動的に割り当てたり削除したりしたいと考える場合があります。

この機能を使用すると、特定のチームのメンバーは、メンバーシップを手動で管理するのではなく、特定の条件セットに基づいて自動的に更新されます。 これを行うには、Azure AD プレミアム P1 ライセンスとチーム メンバーシップ[](/azure/active-directory/users-groups-roles/groups-dynamic-membership)をテナント管理者が、テナントと管理者アカウントを持っている場合は、任意のユーザーの Azure AD プロパティに割り当てることができます。

Microsoft Teamsチームの Microsoft 365 グループで有効にした動的メンバーシップの変更を反映するには、数分から最大 2 時間かかる場合があります。

動的グループでチームを使用する場合:

- ルールでは、チーム メンバーのユーザーを定義できますが、チーム所有者は定義することはできません。
- メンバーは動的グループ ルールによって定義されるので、所有者はチームのメンバーとしてユーザーを追加または削除できない。
- Teamsは、チームのメンバー管理を許可しません。 メンバーの追加、メンバー ロールの編集、参加要求の送信と承認、チームからの退出を行うオプションはすべて非表示になります。

動的メンバーシップを使用するチームを作成するには、まず動的グループを作成[Microsoft 365、](/azure/active-directory/users-groups-roles/groups-create-rule)そのグループからチーム[を作成します](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)。

既存のチームを動的メンバーシップに変更できます。 詳細については[、「静的グループ メンバーシップを動的グループに変更する」Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type)参照してください。

## <a name="related-topics"></a>関連項目

[Microsoft Teams の制限事項と仕様](limits-specifications-teams.md)

[グループ内のグループの動的メンバーシップ Azure Active Directory](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
