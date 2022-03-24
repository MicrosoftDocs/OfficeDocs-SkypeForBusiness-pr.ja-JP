---
title: フロントTeamsに合わせてアプリをカスタマイズする
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: フロントエンド ワーカー向けにカスタマイズされたアプリ エクスペリエンスについて、Teams。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: b526733558570e4903d9dce43094c7ffa0f7de17
ms.sourcegitcommit: b91d83739a078b175770c797c17d602eb5c83a4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2022
ms.locfileid: "63774186"
---
# <a name="tailor-teams-apps-for-your-frontline-workers"></a>フロントTeamsに合わせてアプリをカスタマイズする

> [!NOTE]
> [!INCLUDE [new-feature-coming-soon-section](includes/new-feature-coming-soon-section.md)]

## <a name="overview"></a>概要

Teamsは、フロントライン ワーカー用にアプリをピン留めする簡単な方法を提供します。 この機能は、ライセンスに基づいてアプリをピン留めし、ニーズに合わせて調整された Teamsでフロントライン の作業員に手に入るエクスペリエンスを提供します。

カスタマイズされたフロントライン アプリエクスペリエンスにより、フロントラインワーカーは、管理者からアクションを必要とせずに、Teamsで最も関連性の高いアプリを取得します。

## <a name="tailored-frontline-app-experience"></a>カスタマイズされたフロントライン アプリエクスペリエンス

アプリはアプリ バーにピン留めされます。アプリ バーは、Teams モバイル クライアント (iOS と Android) の下部と Teams デスクトップ クライアントの側にあるバーです。 F ライセンスを持つユーザーには、次のアプリ [がピン留めされています](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)。

- [アクティビティ](https://support.microsoft.com/office/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)
- [チャット](https://support.microsoft.com/office/get-started-with-chat-0b506ce2-eb6d-4fca-9668-e56980ba755e)
- [Teams](https://support.microsoft.com/office/teams-and-channels-in-microsoft-teams-c6d0e61d-a61e-44a6-a972-04f2a8fa4155)
- [トランシーバー](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [タスク](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)
- [Shifts](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
- [承認](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)

**Teams モバイル**

:::image type="content" source="media/tailored-teams-apps-mobile.png" alt-text="モバイルでのカスタマイズされたフロントライン Teamsエクスペリエンス" lightbox="media/tailored-teams-apps-mobile.png"::: 

**Teams デスクトップ**

:::image type="content" source="media/tailored-teams-apps-desktop.png" alt-text="デスクトップ上のカスタマイズされたフロントライン Teamsエクスペリエンス" lightbox="media/tailored-teams-apps-desktop.png"::: 

## <a name="admin-controls"></a>管理者コントロール

> [!NOTE]
> この **機能を有効に** するには、グローバル (組織全体の [既定) アプリ](teams-app-setup-policies.md) セットアップ ポリシーでユーザー固定設定を有効にする必要があります。

カスタマイズされたフロントライン アプリエクスペリエンスは、管理センターの [アプリの管理] ページにある [カスタマイズされたアプリを[](manage-apps.md#manage-org-wide-app-settings)組織全体で表示する] 設定Teams制御されます。 この機能が有効な場合は、F ライセンスを持つ組織内のすべてのユーザーが、カスタマイズされたアプリ エクスペリエンスを取得します。

ユーザーに割り当てられている [カスタム アプリセットアップ ポリシー](teams-app-setup-policies.md) が優先されます。 つまり、ユーザーにカスタム アプリ セットアップ ポリシーが既に割り当てられている場合、ユーザーはカスタム アプリセットアップ ポリシーで定義されている構成を取得します。 グローバル アプリ セットアップ ポリシーを含む Teams アプリ ポリシーでの機能の詳細については、この記事の後半の「シナリオ」セクションを[](#scenarios)参照してください。

この機能は既定で有効になっています。 ただし、Microsoft が提供するカスタマイズされたフロントライン アプリエクスペリエンスが必要ない場合は、この機能をオフにできます。 機能をオフまたはオンにする方法:

1. 管理センターの左側のナビゲーションMicrosoft Teamsアプリの管理Teams **に** > 移動し、[組織全体のアプリ設定] **を選択します**。
2. [**カスタマイズされたアプリ] で**、[カスタマイズされたアプリの **表示] トグルを** [**オフ] または [オン] に切り****替えます**。

    :::image type="content" source="media/tailored-teams-apps-admin-center.png" alt-text="管理センターの [アプリの管理] ページの [カスタマイズされたアプリの表示Teamsスクリーンショット" lightbox="media/tailored-teams-apps-admin-center.png":::

## <a name="scenarios"></a>シナリオ

### <a name="how-does-the-tailored-frontline-app-experience-affect-my-global-app-setup-policy"></a>カスタマイズされたフロントライン アプリエクスペリエンスは、グローバル アプリのセットアップ ポリシーにどのような影響を与えるのでしょうか。

カスタマイズされたフロントライン アプリ エクスペリエンスとグローバル アプリ セットアップ ポリシーの組み合わせて使用する方法について説明します。 この表のシナリオは、F ライセンスとグローバル アプリ セットアップ ポリシーを持ち、ユーザーのピン留めが有効になっているフロントライン ワーカー **に** 適用されます。

|条件... |そうしたら。。。 |
|---------|---------|
|フロントライン ワーカーにはグローバル アプリ セットアップ ポリシーが設定され、この機能はオフです。 |フロントライン ワーカーは、グローバル アプリセットアップ ポリシーで定義されているアプリを取得します。|
|フロントライン ワーカーはグローバル アプリ セットアップ ポリシーを持ち、機能はオンです。     | フロントライン ワーカーは、カスタマイズされたフロントライン アプリ エクスペリエンスを取得します。 グローバル アプリ セットアップ ポリシーで定義されたアプリは、カスタマイズされたアプリの下にピン留めされます。      |
|グローバル アプリセットアップ ポリシーを更新すると、この機能が有効です。     |フロントライン ワーカーは、カスタマイズされたフロントライン アプリ エクスペリエンスを取得し、グローバル アプリ セットアップ ポリシーで定義されているアプリは、カスタマイズされたアプリの下にピン留めされます。         |
|フロントライン ワーカーにはグローバル アプリセットアップ ポリシーが適用され、 **ユーザーのピン留めは** オフになります。 |フロントライン ワーカーは、グローバル アプリセットアップ ポリシーで定義されているアプリを取得します。|
|フロントライン ワーカーにはグローバル アプリ セットアップ ポリシーが設定され、グローバル アプリセットアップ ポリシーが変更され、アプリ一覧の 2 番目の位置に企業 (LOB) アプリが含まれます。 |LOB アプリは、カスタマイズされたアプリの下にピン留めされます。 ユーザー固定がオンの場合、フロントライン ワーカーはアプリ **の順序を** 変更できます。         |
|フロントライン ワーカーはグローバル セットアップ ポリシーを持ち、グローバル アプリセットアップ ポリシーは最初の位置に Shifts を含めるに変更されます。  |シフトは、カスタマイズされたフロントライン アプリ エクスペリエンスによって定義された 6 番目の位置に固定されます。 ユーザー固定がオンの場合、フロントライン ワーカーはアプリ **の順序を** 変更できます。          |

### <a name="how-does-the-tailored-frontline-app-experience-work-with-other-teams-app-policies"></a>カスタマイズされたフロントライン アプリ エクスペリエンスは、他のアプリ ポリシーとどのようにTeamsしますか?

カスタマイズされたフロントライン アプリ エクスペリエンスが、他のアプリ ポリシーとどのようにTeamsについて説明します。

|条件...  |そうしたら。。。 |
|---------|---------|
この機能はオフです。   | フロントライン ワーカーは、グローバル アプリ セットアップ ポリシーまたはカスタム アプリ セットアップ ポリシーで定義されているアプリを割り当てられます。          |
|フロントライン ワーカーにはカスタム アプリ セットアップ ポリシーが設定され、この機能はオンです。    |フロントライン ワーカーは、カスタム アプリ セットアップ ポリシーで定義されているアプリを取得します。          |
|カスタマイズされたフロントライン アプリ エクスペリエンスのアプリは、ユーザーまたは組織に対してブロックされます。      |カスタマイズされたフロントライン アプリ エクスペリエンスは、アプリのアクセス許可 [ポリシーを尊重します](teams-app-permission-policies.md)。 アプリがブロックされている場合、フロントライン ワーカーにはブロックされたアプリは表示されません。           |
|カスタマイズされたフロントライン アプリ エクスペリエンスのアプリは、アプリセットアップ ポリシーで既に定義されています。この機能はオンです。 |アプリは、カスタマイズされたアプリの一覧で定義された順序に基づいてピン留めされます。        |
|ユーザーは E、A、または G のライセンスを持ち、この機能はオンです。   | ユーザーは、カスタマイズされたフロントライン アプリ エクスペリエンスを取得しない。 現時点では、このエクスペリエンスは F ライセンスを持つユーザーにのみ適用されます。        |

> [!NOTE]
> カスタマイズされたフロントライン アプリ エクスペリエンスでは、アプリやアプリの順序を変更できない。 今のところ、変更を加える場合は、独自のカスタム エクスペリエンスを設定できます。 これを行うには、まず機能をオフにします。 次に [、カスタム アプリ セットアップ ポリシーを作成](teams-app-setup-policies.md)し、ユーザーまたは [グループに割り当てる必要があります](assign-policies-users-and-groups.md)。

## <a name="related-articles"></a>関連記事

- [アプリで Walkie Talkie アプリを管理Teams](walkie-talkie.md)
- [タスク アプリを管理Teams](manage-tasks-app.md)
- [Shifts アプリを管理Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
- [アプリで承認アプリを管理Teams](approval-admin.md)
- [Teams のアプリのセットアップ ポリシーを管理する](teams-app-setup-policies.md)
- [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
