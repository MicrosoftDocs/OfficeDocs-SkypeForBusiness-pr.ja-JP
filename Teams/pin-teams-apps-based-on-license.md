---
title: ライセンスに基Teamsアプリを調整する
author: guptaashish
ms.author: guptaashish
ms.reviewer: aaglick
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: ライセンスに基づいて組織内Teamsアプリをピン留めする方法について学習します。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97da80a0bb02c18c3270d547dd0c0753a207dc8c
ms.sourcegitcommit: de6eb0478a79e178c5d02cdab8cca44a88beb853
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2022
ms.locfileid: "63070736"
---
# <a name="tailor-your-teams-apps-based-on-license"></a>ライセンスに基Teamsアプリを調整する

> [!NOTE]
> [!INCLUDE [new-feature-coming-soon-section](includes/new-feature-coming-soon-section.md)]

> [!NOTE]
> 現在、この機能は F ライセンスに適用されます。 そのため、この記事では、フロントライン worker エクスペリエンスに焦点を当ててしています。 その他のライセンスの種類は、今後サポートされる予定です。

## <a name="overview"></a>概要

Teamsは、ライセンスに基づいてアプリをピン留めする方法を提供します。 ユーザーがカスタマイズされたアプリ エクスペリエンスを有効Teamsにサインインすると、ユーザーはライセンスに基づいて調整されたアプリ エクスペリエンスを取得します。

この機能を使用すると、管理者からの操作を必要とせずに、Teams最も関連性の高いアプリがユーザーに提供されます。

## <a name="tailored-app-experience"></a>カスタマイズされたアプリ エクスペリエンス

アプリは、Teams デスクトップ クライアントの側と Teams モバイル クライアント (iOS および Android) の下部にあるアプリ バーにピン留めされます。

F ライセンスを持つユーザー用にピン留めされたアプリ:

- [アクティビティ](https://support.microsoft.com/office/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)
- [チャット](https://support.microsoft.com/office/get-started-with-chat-0b506ce2-eb6d-4fca-9668-e56980ba755e)
- [Teams](https://support.microsoft.com/office/teams-and-channels-in-microsoft-teams-c6d0e61d-a61e-44a6-a972-04f2a8fa4155)
- [トランシーバー](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [タスク](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)
- [Shifts](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
- [承認](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)

## <a name="admin-controls"></a>管理者コントロール

> [!NOTE]
> この機能を有効にするには、グローバル (組織全体の [既定) アプリ](teams-app-setup-policies.md) セットアップ ポリシーでユーザーのピン留めを有効にする必要があります。

カスタマイズされたアプリ エクスペリエンス機能は、Teams 管理センターの  [アプリの管理] ページの [ライセンスに基づいてカスタマイズされた[](manage-apps.md#manage-org-wide-app-settings)アプリを表示する] 設定によって制御されます。 この機能が有効な場合は、F ライセンスを持つ組織内のすべてのユーザーが、カスタマイズされたアプリ エクスペリエンスを取得します。

ユーザーに割り当てられているカスタム アプリセットアップ ポリシーが優先されます。 つまり、ユーザーにカスタム アプリ セットアップ ポリシーが既に割り当てられている場合、ユーザーはカスタム アプリセットアップ ポリシーで定義されている構成を取得します。 組織で適用した既存のアプリ セットアップ ポリシーでこの機能がどのように機能するかの詳細については、この記事の「シナリオ」セクション[](#scenarios)を参照してください。

この機能は既定で有効になっています。 ただし、Microsoft が提供するカスタマイズされたアプリ エクスペリエンスが必要ない場合は、この機能をオフにできます。 機能をオフまたはオンにする方法:

1. 管理センターの左側のナビゲーションMicrosoft Teamsアプリの管理Teams **に** > 移動し、[組織全体のアプリ設定] **を選択します**。
2. [ **カスタマイズされたアプリ] で**、[ライセンスに基 **づいてカスタマイズされた** アプリを表示する] トグルを [ **オフ] または [オン] に切り** 替 **えます**。

## <a name="scenarios"></a>シナリオ

この表の情報を使用して、既存のアプリ セットアップ ポリシーを適用した場合など、さまざまなシナリオでカスタマイズされたアプリ エクスペリエンスがどのように機能するかについて説明します。

|条件...  |そうしたら。。。 |
|---------|---------|
|ユーザーはグローバル アプリセットアップ ポリシーを持ち、機能はオンです。     | ユーザーは、カスタマイズされたアプリ エクスペリエンスを取得します。 グローバル アプリ セットアップ ポリシーで定義されているアプリはピン留めされた後も、ピン留めされたアプリの一覧の下に表示されます。      |
|ユーザーがカスタム アプリ セットアップ ポリシーを持ち、機能が有効です。    |ユーザーは、カスタム アプリセットアップ ポリシーで定義されている構成を取得します。          |
|この機能はオンであり、グローバル アプリセットアップ ポリシーを更新します。     |ユーザーは、ライセンスに基づいてカスタマイズされたアプリ エクスペリエンスを取得します。 グローバル アプリ セットアップ ポリシーで定義されているアプリはピン留めされた後も、ピン留めされたアプリの一覧の下に表示されます。          |
|この機能はオフです。   | ユーザーは、割り当てられているグローバル アプリ セットアップ ポリシーまたはカスタム アプリセットアップ ポリシーで定義されているエクスペリエンスを取得します。          |
|ユーザーは E、A、または G のライセンスを持ち、この機能はオンです。   | ユーザーは、カスタマイズされたアプリ エクスペリエンスを取得しない。 現在、カスタマイズされたアプリ エクスペリエンスは、F ライセンスを持つユーザーにのみ適用されます。        |
|カスタマイズされたアプリ エクスペリエンスのアプリは、ユーザーまたは組織に対してブロックされます。      |カスタマイズされたアプリ エクスペリエンスでは、アプリのアクセス許可ポリシーが適用されます。 アプリがブロックされている場合、ブロックされたアプリはユーザーに表示されません。           |
|カスタマイズされたアプリ エクスペリエンスのアプリは、アプリセットアップ ポリシーで既に定義されています。この機能はオンです。 |アプリは、カスタマイズされたアプリ エクスペリエンスによって定義された順序に基づいてピン留めされます。        |

> [!NOTE]
> カスタマイズされたアプリ エクスペリエンスでは、アプリやアプリの順序を変更できない。 今のところ、変更を加える場合は、独自のカスタム エクスペリエンスを設定できます。 これを行うには、まず機能をオフにします。 次に [、カスタム アプリ セットアップ ポリシーを作成](teams-app-setup-policies.md)し、ユーザーまたは [グループに割り当てる必要があります](assign-policies-users-and-groups.md)。

## <a name="related-articles"></a>関連記事

- [アプリで Walkie Talkie アプリを管理Teams](walkie-talkie.md)
- [タスク アプリを管理Teams](manage-tasks-app.md)
- [Shifts アプリを管理Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
- [アプリで承認アプリを管理Teams](approval-admin.md)
- [Teams のアプリのセットアップ ポリシーを管理する](teams-app-setup-policies.md)
- [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
