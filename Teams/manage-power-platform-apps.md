---
title: Microsoft Teams 管理センターで Microsoft Power Platform アプリを管理する
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/27/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Teams 管理センターで Microsoft Power Platform を使用して構築されたカスタム アプリへのアクセスを管理する方法について説明します。
ms.openlocfilehash: 3a81d1db3de7cf4fa82b80526ffdb206bfbe8da6
ms.sourcegitcommit: 1161cddd077056a9c1e2da99a84e35be0380b1b1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2022
ms.locfileid: "68656039"
---
# <a name="manage-microsoft-power-platform-apps-in-the-teams-admin-center"></a>Teams 管理センターで Microsoft Power Platform アプリを管理する

## <a name="manage-custom-apps-created-using-microsoft-power-platform-apps"></a>Microsoft Power Platform アプリを使用して作成されたカスタム アプリを管理する

この記事では、Microsoft Teams 管理センターで [Microsoft Power Platform](https://powerplatform.microsoft.com/) アプリを使用して作成されたカスタム アプリを管理する方法の概要について説明します。 カスタム アプリは、組織内の開発者によって内部ユーザー用に作成されます。

> [!NOTE]
> この記事は、アプリ ページからインストールされた、またはアプリ セットアップ ポリシーを通じて Teams に固定された Power Apps アプリまたは Power Virtual Agents アプリには適用されません。 [アプリのアクセス許可ポリシー](teams-app-permission-policies.md)と[アプリのセットアップ ポリシー](teams-app-setup-policies.md)を使用してストア アプリを管理できます。

[Power Apps](https://powerapps.microsoft.com) は、組織内のアプリ作成者がビジネス データに接続するカスタム アプリを構築するために使用できる、低コードまたはコードなしのアプリケーション開発環境です。 [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) は、アプリ開発者が強力なボットを作成するためのコードなしのボット構築環境です。 Microsoft Power Platform アプリを Teams に統合すると、組織はビジネス プロセスを効率化し、ビジネス ニーズの変化により迅速に対応してコラボレーションを促進し、カスタム ソリューションを作成および共有して生産性を高めることができます。  

組織内の開発者によって作成された Microsoft Power Platform アプリは、Teams に自動的に追加されます。 開発者は、 [Power Apps の共有機能](/powerapps/maker/canvas-apps/share-app) と [Power Virtual Agent の共有機能](/power-virtual-agents/admin-share-bots)を使用して、アプリにアクセスできるユーザーを制御できます。

Microsoft Power Platform アプリが作成または共有されると、ユーザーは **[Power Platform で構築]** に移動して [アプリ] ページで表示およびインストールできます。 (アプリが作成または共有されてから、アプリがここに表示されるまで数分かかる場合があります。)

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Build with Power Platform に一覧表示されている Microsoft Power Platform アプリを示すアプリ ページのスクリーンショット。":::

アプリが次のいずれかの条件を満たしている場合、エンド ユーザーには **[Power Platform で構築]** にアプリが表示されます。

|Power Apps |Power Virtual Agents  |
|---------|---------|
|<ul><li>ユーザーがアプリを作成しました。</li><li>アプリはユーザーと直接共有されています。</li><li>ユーザーが最近アプリを使用しました。 </li></ul>| <ul><li>ユーザーがボットを作成しました。</li><li>ボットは、ユーザーがメンバーであるチームによって所有されます。 </li></ul>        |

ユーザーは、他の Teams アプリをインストールするのと同じ方法で Microsoft Power Platform アプリをインストールします。 ユーザーは、アクセス許可を持っているコンテキストにのみアプリをインストールできることに注意してください。 たとえば、ユーザーが所有するチーム、ユーザーが参加しているチャット、または個人のスコープなどです。

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-teams-admin-center"></a>Teams 管理センターで Microsoft Power Platform アプリへのアクセスを管理する

管理者は、Microsoft Power Platform アプリが Teams のアプリ ページの **[Power Platform で構築]** に表示されるかどうかを制御できます。 [[アプリの管理]](manage-apps.md) ページを使用して、Power Apps で作成されたすべてのアプリ、または Power Virtual Agent で作成されたすべてのアプリを組織レベルでまとめてブロックまたは許可できます。[アプリのアクセス許可ポリシー](teams-app-permission-policies.md)を使用して特定のユーザーに対してブロックまたは許可することもできます。

組織のアプリストアにある **Shared Power Apps** および **共有 Power Virtual Agent Apps** のアプリは、その特定のプラットフォームで作成されたすべてのアプリを表します。 組織全体または特定のユーザーに対してこれらのアプリの一方または両方をブロックした場合、ユーザーは Teams にアプリをインストールできません。 ユーザーは、アプリを許可する管理者の承認を要求できません。

Power Apps および Power Virtual Agents で作成されたすべてのアプリへのアクセスを制御できますが、個々のアプリを許可またはブロックすることはできないことに注意してください。 アプリの作成者は、Power Apps および Power Virtual Agents 内から共有機能を使用して、作成したアプリにアクセスできるユーザーを決定します。 作成者が Power Virtual Agents で作成したアプリをユーザーと共有し、そのユーザーの **[共有 Power Virtual Agents アプリ]** をブロックした場合、ユーザーは Teams でそのプラットフォームのアプリを表示またはインストールできなくなります。

ユーザーが Power Apps または Power Virtual Agents からのアプリへのアクセスを許可されている場合、ユーザーがこれらのプラットフォームの一方または両方からアプリにアクセスすることをブロックすると、ユーザーは、アプリをブロックする前にインストールした Microsoft Power Platforms アプリに引き続きアクセスして使用できます。 ただし、ユーザーは **[Power Platform で構築]** のこれらのプラットフォームからアプリをインストールできなくなりました。

> [!NOTE]
> [[アプリの管理]](manage-apps.md) ページの **[組織全体でカスタム アプリとの対話を許可する]** 設定は、組織内のすべてのユーザーに適用され、カスタム アプリを操作できるかどうかを管理します。 組織全体のアプリ設定は、すべてのユーザーの動作を管理し、ユーザーに割り当てられた他のアプリ権限ポリシーを上書きします。 この設定がオフになっている場合、組織内のユーザーは、Microsoft Power Platform アプリを含むカスタム アプリをインストールできません。 詳細については、「[組織全体のアプリ設定を管理する](manage-apps.md#manage-org-wide-app-settings)」を参照してください。

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>組織の Microsoft Power Platform アプリを許可またはブロックする

既定では、**[共有 PowerApps]** と **[共有 Power Virtual Agent Apps]** は、組織内のすべての Teams ユーザーに許可されています。 Microsoft Teams 管理センターの [[アプリの管理]](manage-apps.md) ページで、組織レベルでそれらをブロックまたは許可できます。  

1. Teams 管理センターにサインインし、**Teams アプリ** > にアクセス **[アプリを管理](https://admin.teams.microsoft.com/policies/manage-apps)** する ページにアクセスするには、グローバル管理者または Teams サービス管理者である必要があります。
1. アプリ リストで、次のいずれかを実行します。

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="共有された Microsoft Power Platform アプリを示す [アプリの管理] ページのスクリーンショット。":::

    * 組織内のすべてのユーザーの Power Apps または Power Virtual Agent で作成されたアプリをブロックするには、 **共有 Power Apps** または **共有 Power Virtual Agent Apps** を検索し、それを選択して **[ブロック]** を選択します。
    * 組織内のすべてのユーザーに対して Power Apps または Power Virtual Agent で作成されたアプリを許可するには、 **[共有 Power Apps]** または **[共有 Power Virtual Agent Apps]** を検索して選択し、**[許可]** を選択します。

### <a name="allow-microsoft-power-platform-apps-for-specific-users"></a>特定のユーザーに対して Microsoft Power Platform アプリを許可する

組織内の特定のユーザーが Power Apps または Power Virtual Agent で作成されたアプリへのアクセスを許可またはブロックするには、1 つ以上のカスタム [[アプリ アクセス許可ポリシー]](teams-app-permission-policies.md) を作成して割り当てます。

たとえば、特定のユーザーが Power Apps で作成したアプリへのアクセスをブロックするには、アプリのアクセス許可のカスタム ポリシーを作成して **Shared Power Apps** をブロックし、それらのユーザーにポリシーを割り当てます。

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Shared Power Apps がブロックされているアプリのアクセス許可のカスタム ポリシーの例のスクリーンショット。":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>監査ログを使用して Microsoft Power Platform のインストール アクティビティを調査する

Teams の監査ログを使用して、ユーザーが Teams の [アプリ] ページの **[Power Platform で構築]** セクションから Microsoft Power Platform アプリをインストールしたイベントを調査できます。 これを行うには、[[監査ログを検索]](./audit-log-events.md) して、ユーザーまたはユーザー セットの **[インストールされたアプリ]** Teams イベント (**AppInstalled** 操作の下) を探します。 **[Power Platform でビルド済み]** からインストールされているアプリを見つけるには、特定のレコードの詳細で **AppDistributionMode** プロパティで **TemplatedInstance** 値を探します。

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="AppDistributionMode プロパティの TemplatedInstance 値のスクリーンショット。" lightbox="media/manage-power-platform-apps-audit.png":::

> [!NOTE]
> フィルター処理を容易にするために、監査レコードを CSV 形式でエクスポートできます。

## <a name="related-articles"></a>関連記事

* [Power Apps でキャンバス アプリを共有する](/powerapps/maker/canvas-apps/share-app)
* [ボットを他のユーザーと共有する](/power-virtual-agents/admin-share-bots)
* [Microsoft Teams 管理センターでアプリを管理する](manage-apps.md)
* [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
* [Teams アプリ 申請 API を使用して送信されたカスタム アプリを発行する](submit-approve-custom-apps.md)
