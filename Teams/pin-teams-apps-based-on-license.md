---
title: 現場のワーカーに合わせてTeams アプリを調整する
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Teamsの現場担当者向けにカスタマイズされたアプリ エクスペリエンスについて説明します。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: b526733558570e4903d9dce43094c7ffa0f7de17
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2022
ms.locfileid: "63774186"
---
# <a name="tailor-teams-apps-for-your-frontline-workers"></a>現場のワーカーに合わせてTeams アプリを調整する

> [!NOTE]
> [!INCLUDE [new-feature-coming-soon-section](includes/new-feature-coming-soon-section.md)]

## <a name="overview"></a>概要

Teamsは、フロントライン ワーカー用のアプリを簡単にピン留めする方法を提供します。 この機能は、ライセンスに基づいてアプリをピン留めし、現場のワーカーにニーズに合わせて調整されたTeamsですぐに使用できるエクスペリエンスを提供します。

カスタマイズされたフロントライン アプリ エクスペリエンスにより、フロントライン ワーカーは、管理者から必要なアクションなしで、Teamsで最も関連性の高いアプリを取得します。

## <a name="tailored-frontline-app-experience"></a>カスタマイズされたフロントライン アプリ エクスペリエンス

アプリはアプリ バーにピン留めされます。これは、Teams モバイル クライアント (iOS と Android) の下部にあるバーであり、Teams デスクトップ クライアントの側にあります。 次のアプリは、 [F ライセンス](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)を持つユーザーに対してピン留めされます。

- [アクティビティ](https://support.microsoft.com/office/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)
- [チャット](https://support.microsoft.com/office/get-started-with-chat-0b506ce2-eb6d-4fca-9668-e56980ba755e)
- [Teams](https://support.microsoft.com/office/teams-and-channels-in-microsoft-teams-c6d0e61d-a61e-44a6-a972-04f2a8fa4155)
- [トランシーバー](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [タスク](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)
- [Shifts](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
- [承認](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)

**モバイルTeams**

:::image type="content" source="media/tailored-teams-apps-mobile.png" alt-text="Teams モバイルでのカスタマイズされたフロントライン アプリ エクスペリエンス" lightbox="media/tailored-teams-apps-mobile.png"::: 

**デスクトップTeams**

:::image type="content" source="media/tailored-teams-apps-desktop.png" alt-text="Teams デスクトップ上のカスタマイズされたフロントライン アプリ エクスペリエンス" lightbox="media/tailored-teams-apps-desktop.png"::: 

## <a name="admin-controls"></a>管理者コントロール

> [!NOTE]
> この機能を有効にするには、グローバル (組織全体の既定) [アプリ設定ポリシー](teams-app-setup-policies.md)で **ユーザーピン留め** 設定を有効にする必要があります。

カスタマイズされたフロントライン アプリ エクスペリエンスは、Teams管理センターの [アプリの管理] ページの [**カスタマイズされたアプリ** を組織全体に表示する []](manage-apps.md#manage-org-wide-app-settings) 設定によって制御されます。 機能がオンの場合、F ライセンスを持つ組織内のすべてのユーザーが、カスタマイズされたアプリ エクスペリエンスを取得します。

ユーザーに割り当てられているカスタム [アプリ設定ポリシー](teams-app-setup-policies.md) が優先されます。 つまり、ユーザーに既にカスタム アプリセットアップ ポリシーが割り当てられている場合、ユーザーはカスタム アプリセットアップ ポリシーで定義されている構成を取得します。 グローバル アプリ設定ポリシーを含む、Teams アプリ ポリシーでの機能の動作の詳細については、この記事の後半の[「シナリオ」](#scenarios)セクションを参照してください。

この機能は既定で有効になっています。 ただし、Microsoft が提供するカスタマイズされたフロントライン アプリ エクスペリエンスが必要ない場合は、この機能を無効にできます。 機能をオフまたはオンにするには:

1. Microsoft Teams管理センターの左側のナビゲーションで、**Teams** **appsManage** >  アプリに移動し、**組織全体のアプリ設定** を選択します。
2. [ **カスタマイズされたアプリ**] で、[ **カスタマイズしたアプリを表示** ] トグルを **[オフ]** または **[オン]** に切り替えます。

    :::image type="content" source="media/tailored-teams-apps-admin-center.png" alt-text="Teams管理センターの [アプリの管理] ページの [カスタマイズされたアプリの表示] 設定のスクリーンショット" lightbox="media/tailored-teams-apps-admin-center.png":::

## <a name="scenarios"></a>シナリオ

### <a name="how-does-the-tailored-frontline-app-experience-affect-my-global-app-setup-policy"></a>カスタマイズされたフロントライン アプリ エクスペリエンスは、グローバル アプリのセットアップ ポリシーにどのような影響を与えるのでしょうか?

カスタマイズされたフロントライン アプリ エクスペリエンスとグローバル アプリセットアップ ポリシーの連携方法について説明します。 この表のシナリオは、F ライセンスとグローバル アプリ設定ポリシーを持つフロントライン ワーカーに適用され、 **ユーザーピン留め** が有効になっています。

|条件... |そうしたら。。。 |
|---------|---------|
|フロントライン ワーカーにはグローバル アプリセットアップ ポリシーがあり、機能はオフです。 |フロントライン ワーカーは、グローバル アプリセットアップ ポリシーで定義されたアプリを取得します。|
|フロントライン ワーカーにはグローバル アプリのセットアップ ポリシーがあり、この機能はオンになっています。     | フロントライン ワーカーは、カスタマイズされたフロントライン アプリ エクスペリエンスを取得します。 グローバル アプリセットアップ ポリシーで定義されているアプリは、カスタマイズされたアプリの下にピン留めされます。      |
|グローバル アプリのセットアップ ポリシーを更新すると、機能がオンになります。     |フロントライン ワーカーは、カスタマイズされたフロントライン アプリ エクスペリエンスを取得し、グローバル アプリセットアップ ポリシーで定義されているアプリは、カスタマイズされたアプリの下にピン留めされます。         |
|フロントライン ワーカーにはグローバル アプリセットアップ ポリシーがあり、 **ユーザーピン留め** はオフになっています。 |フロントライン ワーカーは、グローバル アプリセットアップ ポリシーで定義されたアプリを取得します。|
|フロントライン ワーカーにはグローバル アプリ設定ポリシーがあり、グローバル アプリのセットアップ ポリシーが変更され、アプリの一覧の 2 番目の位置に基幹業務 (LOB) アプリが含まれます。 |LOB アプリは、カスタマイズされたアプリの下にピン留めされます。 **ユーザーピン留め** がオンの場合、フロントライン ワーカーはアプリの順序を変更できます。         |
|フロントライン ワーカーにはグローバルセットアップ ポリシーがあり、グローバル アプリのセットアップ ポリシーは、最初の位置に Shifts を含めるために変更されます。  |シフトは、カスタマイズされたフロントライン アプリ エクスペリエンスで定義されているように、6 番目の位置にピン留めされます。 **ユーザーピン留め** がオンの場合、フロントライン ワーカーはアプリの順序を変更できます。          |

### <a name="how-does-the-tailored-frontline-app-experience-work-with-other-teams-app-policies"></a>カスタマイズされたフロントライン アプリ エクスペリエンスは、他のTeamsアプリ ポリシーとどのように連携しますか?

カスタマイズされたフロントライン アプリ エクスペリエンスが他のTeamsアプリ ポリシーとどのように連携するかを説明します。

|条件...  |そうしたら。。。 |
|---------|---------|
この機能はオフです。   | フロントライン ワーカーは、グローバル アプリセットアップ ポリシーまたはそれらに割り当てられたカスタム アプリ設定ポリシーで定義されているアプリを取得します。          |
|フロントライン ワーカーにはカスタム アプリセットアップ ポリシーがあり、機能はオンになっています。    |フロントライン ワーカーは、カスタム アプリセットアップ ポリシーで定義されたアプリを取得します。          |
|カスタマイズされたフロントライン アプリ エクスペリエンスのアプリは、ユーザーまたは組織に対してブロックされます。      |カスタマイズされたフロントライン アプリ エクスペリエンスは、アプリの [アクセス許可ポリシー](teams-app-permission-policies.md)に従います。 アプリがブロックされている場合、フロントライン ワーカーにはブロックされたアプリは表示されません。           |
|カスタマイズされたフロントライン アプリ エクスペリエンスのアプリは、アプリセットアップ ポリシーで既に定義されており、機能はオンになっています。 |アプリは、カスタマイズされたアプリの一覧で定義された順序に基づいてピン留めされます。        |
|ユーザーが E、A、または G のライセンスを持ち、機能がオンになっている。   | ユーザーは、カスタマイズされたフロントライン アプリ エクスペリエンスを得られません。 現在、このエクスペリエンスは、F ライセンスを持つユーザーにのみ適用されます。        |

> [!NOTE]
> カスタマイズされたフロントライン アプリ エクスペリエンスでは、アプリやアプリの順序を変更することはできません。 現時点では、変更を加える場合は、独自のカスタム エクスペリエンスを設定できます。 これを行うには、まず機能をオフにします。 次に、 [カスタム アプリセットアップ ポリシーを作成](teams-app-setup-policies.md)し、 [ユーザーまたはグループに割り当てます](assign-policies-users-and-groups.md)。

## <a name="related-articles"></a>関連記事

- [Teamsで Walkie Talkie アプリを管理する](walkie-talkie.md)
- [Teamsでタスク アプリを管理する](manage-tasks-app.md)
- [Teamsで Shifts アプリを管理する](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teamsで承認 アプリを管理する](approval-admin.md)
- [Teams のアプリのセットアップ ポリシーを管理する](teams-app-setup-policies.md)
- [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
