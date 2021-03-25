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
description: 動的メンバーシップを使用して、Microsoft Teams が Microsoft 365 グループに関連付けられているチームをサポートする方法について説明します。
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

Microsoft Teams は、動的メンバーシップを使用して Microsoft 365 グループに関連付けられている *チームをサポートします*。 動的メンバーシップを使用すると、Azure Active Directory (Azure AD) で特定のユーザー属性をチェックする 1 つ以上のルールによってチームのメンバーシップを定義AD。 ユーザーの属性が変わるか、ユーザーがテナントに参加したり退出したりすると、ユーザーは正しいチームに自動的に追加または削除されます。

動的メンバーシップを使用すると、組織内の特定のユーザーのチームを設定できます。 考えられるシナリオは次のとおりです。
- 病院では、通信をブロードキャストするために、看護師、医師、および医師のための個別のチームを作成できます。 これは、病院が一時従業員に依存している場合に特に重要です。
- 大学は、特定の大学内のすべての教職員のチームを作成できます。たとえば、頻繁に変更される非常勤教員も含めてです。
- 航空会社は、各フライトのチームを作成し (たとえば、火曜日の午後はシカゴからアトランタまで)、必要に応じて頻繁に変更するフライト のスタッフを自動的に割り当てたり削除したりします。

この機能を使用すると、特定のチームのメンバーは、メンバーシップを手動で管理する代わりに、特定の条件セットに基づいて自動的に更新されます。 この操作を行うには、テナントと管理者アカウントがある場合、テナント管理者が[](/azure/active-directory/users-groups-roles/groups-dynamic-membership)Azure AD Premium P1 ライセンスとチーム メンバーシップをユーザーの Azure AD プロパティに割り当てる必要があります。

Microsoft Teams は、チームの Microsoft 365 グループに反映された動的なメンバーシップの変更を反映するために、数分から最大 2 時間かかる場合があります。

> [!NOTE]
> - ルールでは、チーム メンバーのユーザーを定義できますが、チーム所有者は定義することはできません。
> - チーム [とチャネルのサイズに関する現在の制限については、「Microsoft Teams](limits-specifications-teams.md) の制限と仕様」を参照してください。
> - メンバーは動的グループ ルールによって定義されるので、所有者はチームのメンバーとしてユーザーを追加または削除することができます。
> -    メンバーは、動的なグループの支援を受けたチームから退出することはできません。

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a>動的メンバーシップを使用した Microsoft 365 グループの作成と管理

テナント管理者としてログインしている間は、「動的グループを作成して状態を確認する」の [手順に従います](/azure/active-directory/users-groups-roles/groups-create-rule)。 必要に応じて [、Azure Active Directory のグループの動的メンバーシップ ルールを参照してください](/azure/active-directory/users-groups-roles/groups-dynamic-membership)。

## <a name="create-a-new-team-with-your-microsoft-365-group"></a>Microsoft 365 グループで新しいチームを作成する

メンバーシップの変更を有効にできる時間を許可し、「既存のグループからチームを作成する」の説明に従って新しい [チームを作成します](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)。

## <a name="apply-dynamic-membership-to-an-existing-team"></a>既存のチームに動的メンバーシップを適用する

「Azure Active Directory で動的に静的グループ メンバーシップを変更する」の説明に従って、既存のチームを受け取り、動的メンバーシップに [変更することができます](/azure/active-directory/users-groups-roles/groups-change-type)。

## <a name="changes-in-client-behavior"></a>クライアントの動作の変更

チームに対して動的メンバーシップが有効になると、Teams クライアントはチームのメンバー管理を許可しなくなりました。 メンバーの追加、メンバーロールの編集、参加依頼の送信と承認、チームからの退出を行うオプションはすべて非表示になります。