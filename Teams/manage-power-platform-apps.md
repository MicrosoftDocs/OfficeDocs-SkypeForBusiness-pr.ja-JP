---
title: Microsoft Teams 管理センターで Microsoft Power Platform アプリを管理する
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: joglocke
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Teams 管理センターで Microsoft Power Platform を使用して構築されたカスタム アプリへのアクセスを管理する方法について説明します。
ms.openlocfilehash: 85aa9904b22dd03e1056b353bf91904909c11f59
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880261"
---
# <a name="manage-microsoft-power-platform-apps-in-the-teams-admin-center"></a>Teams 管理センターで Microsoft Power Platform アプリを管理する

## <a name="microsoft-power-platform-apps-in-teams"></a>Teams の Microsoft Power Platform アプリ

この記事では、Microsoft Teams 管理センターで [Microsoft Power Platform](https://powerplatform.microsoft.com/) アプリを管理する方法の概要について説明します。

> [!NOTE]
> この記事は、Power Apps または Power Virtual Agent を使用して組織内の開発者によって作成されたカスタム アプリに適用されます。 この記事は、[アプリ] ページからインストールされている Power Apps アプリまたは Power Virtual Agents アプリには適用されません。また、アプリのセットアップ ポリシーを使用して Teams にピン留めされる場合もあります。 ストア アプリは、[アプリのアクセス許可ポリシーとアプリセットアップ ポリシー](teams-app-permission-policies.md)[を](teams-app-setup-policies.md)使用して管理できます。

[Power Apps](https://powerapps.microsoft.com) は、組織内のアプリ作成者がビジネス データに接続するカスタム アプリを構築するために使用できる、低コードまたはコードなしのアプリケーション開発環境です。 [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) は、アプリ作成者が強力なボットを作成するためのコードなしのボット構築環境です。 Microsoft Power Platform アプリを Teams に統合することで、組織はビジネス プロセスを合理化し、変化するビジネス ニーズに迅速に対応してコラボレーションを促進し、生産性を高めるためにカスタム ソリューションを作成して共有することができます。  

組織内の開発者によって作成された Microsoft Power Platform アプリは、Teams に自動的に追加されます。 開発者は、 [Power Apps の共有機能](/powerapps/maker/canvas-apps/share-app) と [Power Virtual Agent](/power-virtual-agents/admin-share-bots) の共有機能を使用して、アプリにアクセスできるユーザーを制御できます。

Microsoft Power Platform アプリが作成または共有されると、ユーザーは Power Platform を使用してビルドに移動することで、[アプリ] ページでアプリを表示 **して** インストールできます。 (アプリが作成または共有されてから、アプリがここに表示されるまで数分かかる場合があります)。

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="[アプリ] ページのスクリーンショット。":::

エンド ユーザーは、アプリが次のいずれかの条件を満たしている場合、 **Power Platform を使用してビルド** されたアプリを表示します。

|Power Apps |Power Virtual Agent  |
|---------|---------|
|<ul><li>ユーザーがアプリを作成しました。</li><li>アプリはユーザーと直接共有されました。</li><li>ユーザーが最近アプリを使用しました。 </li></ul>| <ul><li>ユーザーがボットを作成しました。</li><li>ボットは、ユーザーがメンバーであるチームによって所有されます。 </li></ul>        |

ユーザーは、他の Teams アプリをインストールするのと同じ方法で Microsoft Power Platform アプリをインストールします。 ユーザーは、アクセス許可を持つコンテキストにのみアプリをインストールできることに注意してください。 たとえば、ユーザーが所有するチーム、ユーザーが参加しているチャット、または個人のスコープなどです。

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-teams-admin-center"></a>Teams 管理センターで Microsoft Power Platform アプリへのアクセスを管理する

管理者は、Microsoft Power Platform アプリが Teams の [アプリ] ページの [ **Power Platform を使用してビルド]** に表示されるかどうかを制御できます。 Power Apps で作成されたすべてのアプリ、または Power Virtual Agent で作成されたすべてのアプリを、組織レベルの [ [アプリの管理](manage-apps.md) ] ページまたは [アプリのアクセス許可ポリシー](teams-app-permission-policies.md)を使用して特定のユーザーに対してまとめてブロックまたは許可できます。

組織のアプリ ストアにある **Shared Power Apps** アプリと **Shared Power Virtual Agent Apps** アプリは、その特定のプラットフォームで作成されたすべてのアプリを表します。 組織全体または特定のユーザーに対してこれらのアプリの一方または両方をブロックした場合、ユーザーはブロックされたアプリなどのアプリを表示できますが、Teams にはインストールできません。 ユーザーは管理者 [の承認を要求してアプリのブロックを解除](manage-apps.md#manage-user-requests-to-unblock-apps)できます。

Power Apps と Power Virtual Agent で作成されたすべてのアプリへのアクセスを制御できますが、個々のアプリを許可またはブロックすることはできません。 アプリ作成者は、Power Apps と Power Virtual Agents 内から共有機能を使用して作成したアプリにアクセスできるユーザーを決定します。 作成者が Power Virtual Agents で作成したアプリをユーザーと共有し、そのユーザーの **共有 Power Virtual Agents Apps を** ブロックした場合、ユーザーはそのプラットフォームのアプリを Teams で表示またはインストールできなくなります。

ユーザーが Power Apps または Power Virtual Agent からアプリへのアクセスを許可され、ユーザーがこれらのプラットフォームのいずれかまたは両方からアプリにアクセスできないようにブロックした場合でも、ユーザーはアプリまたはアプリをブロックする前に、インストールした Microsoft Power Platforms アプリにアクセスして使用できます。 ただし、ユーザーは Built **with Power Platform** でこれらのプラットフォームからアプリをインストールできなくなりました。

> [!NOTE]
> [アプリの [管理](manage-apps.md)] ページの [**組織全体のカスタム アプリとの対話を許可** する] 設定は、組織内のすべてのユーザーに適用され、カスタム アプリと対話できるかどうかを制御します。 組織全体のアプリ設定は、すべてのユーザーの動作を管理し、ユーザーに割り当てられた他のアプリ権限ポリシーを上書きします。 この設定がオフになっている場合、組織内のユーザーは、Microsoft Power Platform アプリを含むカスタム アプリをインストールできません。 詳細については、「 [組織全体のアプリ設定を管理](manage-apps.md#manage-org-wide-app-settings)する」を参照してください。

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>組織の Microsoft Power Platform アプリを許可またはブロックする

既定では、 **組織内** のすべての Teams ユーザーに対して **、共有 Power Apps と Shared Power Virtual Agent Apps** が許可されます。 Microsoft Teams 管理センターの [ [アプリの管理](manage-apps.md) ] ページで、組織レベルでブロックまたは許可できます。  

1. Microsoft Teams 管理センターの左側のウィンドウで、**[Teams アプリ]** > **[アプリの管理]** の順に移動します。 これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。
2. アプリの一覧で、次のいずれかの操作を行います。

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="共有された Microsoft Power Platform アプリを示す [アプリの管理] ページのスクリーンショット。":::

    * 組織内のすべてのユーザーの Power Apps または Power Virtual Agent で作成されたアプリをブロックするには、 **共有 Power Apps** または **Shared Power Virtual Agent Apps** を検索し、それを選択して[ **ブロック**] を選択します。
    * 組織内のすべてのユーザーに対して Power Apps または Power Virtual Agent で作成されたアプリを許可するには、 **Shared Power Apps** または **Shared Power Virtual Agent Apps** を検索して選択し、 **許可** を選択します。

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>特定のユーザーに対して Microsoft Power Platform アプリを許可またはブロックする

組織内の特定のユーザーが Power Apps または Power Virtual Agent で作成されたアプリへのアクセスを許可またはブロックするには、1 つ以上のカスタム [アプリアクセス許可ポリシー](teams-app-permission-policies.md)を作成して割り当てます。

たとえば、特定のユーザーが Power Apps で作成されたアプリにアクセスできないようにするには、カスタム アプリアクセス許可ポリシーを作成して **Shared Power Apps** をブロックし、そのユーザーにポリシーを割り当てます。

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Shared Power Apps がブロックされたカスタム アプリのアクセス許可ポリシーの例のスクリーンショット。":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>監査ログを使用して Microsoft Power Platform のインストール アクティビティを調査する

Teams の監査ログを使用すると、Teams の [アプリ] ページの [ **ビルド済み Power** Platform] セクションから、ユーザーが Microsoft Power Platform アプリをインストールしたイベントを調査できます。 これを行うには、(**AppInstalled** 操作の下で) **インストール済みアプリ** Teams イベントの [監査ログ](./audit-log-events.md)で、ユーザーまたは一連のユーザーを検索します。 **Power Platform でビルド済み** からインストールされているアプリを見つけるには、特定のレコードの詳細で **AppDistributionMode** プロパティで **TemplatedInstance** 値を探します。

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="AppDistributionMode プロパティの TemplatedInstance 値のスクリーンショット。" lightbox="media/manage-power-platform-apps-audit.png":::

> [!NOTE]
> フィルター処理を容易にするために、監査レコードを CSV 形式でエクスポートできます。

## <a name="related-articles"></a>関連記事

* [Power Apps でキャンバス アプリを共有する](/powerapps/maker/canvas-apps/share-app)
* [ボットを他のユーザーと共有する](/power-virtual-agents/admin-share-bots)
* [Microsoft Teams 管理センターでアプリを管理する](manage-apps.md)
* [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
* [Teams アプリ申請 API を使用して送信されたカスタム アプリを発行する](submit-approve-custom-apps.md)
