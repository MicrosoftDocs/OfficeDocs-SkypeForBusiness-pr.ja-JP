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
ms.openlocfilehash: a76600e8ca0a92b2d46e99bc26a857c969bd07e7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120769"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>チームの動的なメンバーシップの概要

Microsoft Teamsは、動的メンバーシップ を使用してMicrosoft 365グループに関連付けられている *チームをサポートします*。 動的メンバーシップを使用すると、チームのメンバーシップを 1 つ以上のルールで定義し、チーム内の特定のユーザー属性を確認Azure Active Directory (Azure AD)。 ユーザー属性が変わるか、ユーザーがテナントに参加して退出すると、ユーザーは自動的に正しいチームに追加または削除されます。

動的メンバーシップを使用すると、組織内のユーザーの特定のコーホートに対してチームを設定できます。 考えられるシナリオは次のとおりです。
- 病院では、通信をブロードキャストするために、看護師、医師、および病院用の個別のチームを作成できます。 これは、病院が一時従業員に依存している場合に特に重要です。
- 大学は、頻繁に変更される非常勤教員を含め、特定の大学内のすべての教職員のチームを作成できます。
- 航空会社は、各フライト (シカゴからアトランタへの火曜日の午後の非停止など) のチームを作成し、必要に応じて頻繁に変更されるフライト の乗務員を自動的に割り当てたり削除したりしたいと考える場合があります。

この機能を使用すると、特定のチームのメンバーは、メンバーシップを手動で管理するのではなく、特定の条件セットに基づいて自動的に更新されます。 これを行うには、Azure AD プレミアム P1 ライセンスとチーム メンバーシップ[](/azure/active-directory/users-groups-roles/groups-dynamic-membership)をテナント管理者が、テナントと管理者アカウントを持っている場合は、任意のユーザーの Azure AD プロパティに割り当てることができます。

Microsoft Teamsチームの Microsoft 365 グループで有効にした動的メンバーシップの変更を反映するには、数分から最大 2 時間かかる場合があります。

> [!NOTE]
> - ルールでは、チーム メンバーのユーザーを定義できますが、チーム所有者は定義することはできません。
> - チーム[サイズとチャネル サイズの現在の制限についてはMicrosoft Teams](limits-specifications-teams.md)の制限と仕様に関するページを参照してください。
> - メンバーは動的グループ ルールによって定義されるので、所有者はチームのメンバーとしてユーザーを追加または削除できない。
> -    メンバーは、動的グループの支援を受けたチームを退出することはできません。

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a>動的メンバーシップを持つMicrosoft 365グループの作成と管理

テナント管理者としてログインしている間は、「動的グループを作成して状態を確認する」の [手順に従います](/azure/active-directory/users-groups-roles/groups-create-rule)。 必要に応じて、「グループの[動的メンバーシップ](/azure/active-directory/users-groups-roles/groups-dynamic-membership)ルール」を参照Azure Active Directory。

## <a name="create-a-new-team-with-your-microsoft-365-group"></a>グループを使用して新しいチームをMicrosoft 365する

次に、「既存のグループからチームを作成する」の説明に従って、メンバーシップの変更を有効にし、新しいチーム [を作成します](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)。

## <a name="apply-dynamic-membership-to-an-existing-team"></a>既存のチームに動的メンバーシップを適用する

既存のチームを引き受け、動的メンバーシップに変更[する](/azure/active-directory/users-groups-roles/groups-change-type)方法については、「静的グループ メンバーシップを動的に変更する」の説明に従Azure Active Directory。

## <a name="changes-in-client-behavior"></a>クライアントの動作の変更

チームに対して動的メンバーシップが有効になると、Teamsクライアントはチームのメンバー管理を許可しなくなりました。 メンバーの追加、メンバー ロールの編集、参加要求の送信と承認、チームからの退出を行うオプションはすべて非表示になります。