---
title: チームの動的なメンバーシップの概要
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Microsoft Teams が動的メンバーシップを使用してMicrosoft 365 グループに関連付けられているチームをサポートする方法について説明します。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- seo-marvel-apr2020
- chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65c747fea2b33f2fd18b004e9a16a2302702ec59
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198729"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>チームの動的なメンバーシップの概要

Microsoft Teams は、*動的メンバーシップ* を使用して、Microsoft 365 グループに関連付けられているチームをサポートします。 動的メンバーシップを使用すると、Azure Active Directory (Azure AD) 内の特定のユーザー属性をチェックする 1 つ以上のルールによってチームのメンバーシップを定義できます。 ユーザー属性が変更されたり、ユーザーがテナントに参加してテナントから退出したりすると、ユーザーは自動的に正しいチームに追加または削除されます。

動的メンバーシップを使用すると、組織内の特定のユーザーのコーホートに対してチームを設定できます。 考えられるシナリオは次のとおりです。
- 病院では、看護師、医師、外科医が通信をブロードキャストするための個別のチームを作成できます。 これは、病院が一時従業員に依存している場合に特に重要です。
- 大学は、頻繁に変化する非常勤教員を含む、特定の大学内のすべての教員のためのチームを作成することができます。
- ある航空会社は、各フライトのチーム (シカゴからアトランタへの火曜日の午後のノンストップなど) を作成し、頻繁に変更されるフライト クルーが必要に応じて自動的に割り当てまたは削除されるようにしたいと考えています。

この機能を使用すると、特定のチームのメンバーは、メンバーシップを手動で管理するのではなく、特定の条件セットに基づいて自動的に更新されます。 そのためには、テナントと管理者アカウントがある場合、Azure AD Premium P1ライセンスとチーム メンバーシップをテナント管理者が任意のユーザーの Azure AD プロパティに[割り当て](/azure/active-directory/users-groups-roles/groups-dynamic-membership)ることができる必要があります。

Microsoft Teams は、チームの Microsoft 365 グループで有効になると、動的メンバーシップの変更を反映するために数分から最大 2 時間かかる場合があります。

動的グループでチームを使用する場合:

- ルールでは、チーム メンバーであるユーザーを定義できますが、チーム所有者は定義できません。
- メンバーは動的グループ ルールによって定義されるため、所有者はユーザーをチームのメンバーとして追加または削除できません。
- Teams クライアントは、チームのメンバー管理を許可しません。 メンバーの追加、メンバー ロールの編集、参加要求の送信と承認、チームの非表示のままにするためのオプション。

動的メンバーシップを使用するチームを作成するには、まず[動的Microsoft 365 グループを作成](/azure/active-directory/users-groups-roles/groups-create-rule)してから、[そのグループからチームを作成](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)します。

既存のチームを変更して、動的メンバーシップを持つことができます。 詳細については、「 [Azure Active Directory で静的グループ メンバーシップを動的に変更](/azure/active-directory/users-groups-roles/groups-change-type) する」を参照してください。

## <a name="related-topics"></a>関連項目

[Microsoft Teams の制限事項と仕様](limits-specifications-teams.md)

[Azure Active Directory のグループの動的メンバーシップ規則](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
