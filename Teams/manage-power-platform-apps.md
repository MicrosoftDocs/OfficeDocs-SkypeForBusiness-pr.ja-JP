---
title: Microsoft Teams管理センターで Microsoft Power Platform アプリを管理する
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
description: Microsoft Teams管理センターで Microsoft Power Platform 上に構築されたカスタム アプリへのアクセスを管理する方法について説明します。
ms.openlocfilehash: 9f212cf52ec757fc4860f081fb67da2cb1b4fcd5
ms.sourcegitcommit: 836926a4914eb33fc3e0d8d6c84cee886cb1a5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2022
ms.locfileid: "65136998"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Microsoft Teams管理センターで Microsoft Power Platform アプリを管理する

## <a name="microsoft-power-platform-apps-in-teams"></a>Teamsの Microsoft Power Platform アプリ

この記事では、Microsoft Teams管理センターで [Microsoft Power Platform](https://powerplatform.microsoft.com/) アプリを管理する方法の概要について説明します。

> [!NOTE]
> この記事は、Power AppsまたはPower Virtual Agentsを使用して組織内の作成者によって作成されたカスタム アプリに適用されます。 これらのカスタム アプリは、Teamsに自動的に追加されます。 この記事は、[アプリ] ページからインストールされるか、アプリ設定ポリシーを使用してTeamsにピン留めされたPower Apps アプリやPower Virtual Agents アプリには適用されません。 アプリ[のアクセス許可ポリシー](teams-app-permission-policies.md)とアプリセットアップ ポリシーを使用して、[[アプリの管理](manage-apps.md)] ページの他のアプリと同様に、[これらのアプリを管理します](teams-app-setup-policies.md)。

[Power Apps](https://powerapps.microsoft.com)は、組織内の作成者がビジネス データに接続するカスタム アプリを構築するために使用できる、低コード/コードなしのアプリケーション開発環境です。 [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents)は、メーカーが強力なボットを作成するためのコードなしのボット構築環境です。 Microsoft Power Platform アプリをTeamsに統合することで、組織はビジネス プロセスを合理化し、変化するビジネス ニーズに迅速に対応してコラボレーションを促進し、カスタム ソリューションを作成して共有して生産性を高めることができます。  

組織内のメーカーによって作成された Microsoft Power Platform アプリは、Teamsに自動的に追加されます。 作成者は、[Power Appsの共有機能とPower Virtual Agentsの共有機能](/powerapps/maker/canvas-apps/share-app)を使用して、アプリにアクセスできるユーザー[を](/power-virtual-agents/admin-share-bots)制御できます。

Microsoft Power Platform アプリが作成または共有されると、ユーザーは[Built **for *Your Organization NameBuilt*]\(組織名** > 構築済 **み**\) に移動して、[アプリ] ページで表示およびインストールできます。 (アプリが作成または共有されてから、アプリがここに表示されるまで数分かかる場合があります)。

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="[アプリ] ページのスクリーンショット。":::

アプリが次のいずれかの条件を満たしている場合、ユーザーは **同僚によってビルド** されたアプリを表示します。

|Power Apps |Power Virtual Agents  |
|---------|---------|
|<ul><li>ユーザーがアプリを作成しました。</li><li>アプリはユーザーと直接共有されました。</li><li>ユーザーが最近アプリを使用しました。 </li></ul>| <ul><li>ユーザーがボットを作成しました。</li><li>ボットは、ユーザーがメンバーであるチームによって所有されます。 </li></ul>        |

ユーザーは、他のTeams アプリをインストールするのと同じ方法で Microsoft Power Platform アプリをインストールします。 ユーザーは、自分が所有するチーム、自分の一部であるチャット、個人のスコープなど、アクセス許可を持つコンテキストにのみアプリをインストールできることに注意してください。

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Microsoft Teams管理センターで Microsoft Power Platform アプリへのアクセスを管理する

管理者は、Microsoft Power Platform アプリが [Teams の [アプリ] ページの **[同僚によってビルド]** に表示されるかどうかを制御できます。 [アプリの管理] ページまたはアプリ[のアクセス許可ポリシー](teams-app-permission-policies.md)を使用して特定のユーザーに対して、Power Appsで作成されたすべてのアプリ、または組織レベルでPower Virtual Agentsで作成されたすべての[アプリ](manage-apps.md)をまとめてブロックまたは許可できます。

組織 **のアプリ ストアにある Shared Power Apps** アプリと **Shared Power Virtual Agent Apps** アプリは、その特定のプラットフォームで作成されたすべてのアプリを表します。 組織レベルまたは特定のユーザーに対してこれらのアプリの一方または両方をブロックした場合、それらのユーザーは、これらのプラットフォームのアプリ **を同僚がビルドで** 表示できず、Teamsにインストールすることはできません。  

Power AppsおよびPower Virtual Agentsで作成されたすべてのアプリへのアクセスを制御できますが、個々のアプリを許可またはブロックすることはできません。 作成者は、Power AppsとPower Virtual Agents内から共有機能を使用して作成したアプリにアクセスできるユーザーを決定します。 作成者がPower Virtual Agentsで作成したアプリをユーザーと共有し、そのユーザーの **Shared Power Virtual Agents Apps を** ブロックした場合、ユーザーはそのプラットフォームのアプリをTeamsで表示またはインストールできなくなります。

ユーザーがPower AppsまたはPower Virtual Agentsからアプリにアクセスすることを許可され、ユーザーがこれらのプラットフォームのいずれかまたは両方からアプリにアクセスできないようにブロックした場合でも、ユーザーはアプリまたはアプリをブロックする前に、インストールした Microsoft Power Platforms アプリにアクセスして使用できます。 ただし、ユーザーは、これらのプラットフォームのアプリを同僚 **がビルドで** 表示したりインストールしたりできなくなります。

> [!NOTE]
> [アプリの [管理](manage-apps.md)] ページの [**組織全体のカスタム アプリとの対話を許可** する] 設定は、組織内のすべてのユーザーに適用され、カスタム アプリと対話できるかどうかを制御します。 組織全体のアプリ設定は、すべてのユーザーの動作を管理し、ユーザーに割り当てられた他のアプリ権限ポリシーを上書きします。 既定では、この設定は[オン] に設定されています。 この設定がオフになっている場合、組織内のユーザーは、Microsoft Power Platform アプリを含むカスタム アプリを表示またはインストールできません。 詳細については、「 [組織全体のアプリ設定を管理](manage-apps.md#manage-org-wide-app-settings)する」を参照してください。

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>組織の Microsoft Power Platform アプリを許可またはブロックする

既定では、**組織内のすべてのTeams** ユーザーに対して共有Power Appsアプリと **Shared Power Virtual Agent Apps が** 許可されます。 Microsoft Teams管理センターの [[アプリの管理](manage-apps.md)] ページで、組織レベルでブロックまたは許可できます。  

1. Microsoft Teams管理センターの左側のウィンドウで、**Teams** **appsManage アプリ** > に移動します。 これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。
2. アプリの一覧で、次のいずれかの操作を行います。

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="共有された Microsoft Power Platform アプリを示す [アプリの管理] ページのスクリーンショット":::

    - 組織内のすべてのユーザーのPower AppsまたはPower Virtual Agentsで作成されたアプリをブロックするには、**共有Power Apps** または **Shared Power Virtual Agent Apps** を検索して選択し、[**ブロック**] をクリックします。
    - 組織内のすべてのユーザーに対してPower AppsまたはPower Virtual Agentsで作成されたアプリを許可するには、**共有Power Apps** または **Shared Power Virtual Agent Apps を** 検索して選択し、[**許可**] をクリックします。

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>特定のユーザーに対して Microsoft Power Platform アプリを許可またはブロックする

組織内の特定のユーザーがPower AppsまたはPower Virtual Agentsで作成されたアプリへのアクセスを許可またはブロックするには、1 つ以上のカスタム [アプリアクセス許可ポリシー](teams-app-permission-policies.md)を作成して割り当てます。

たとえば、特定のユーザーがPower Appsで作成されたアプリへのアクセスをブロックするには、**共有Power Apps** をブロックするカスタム アプリアクセス許可ポリシーを作成し、それらのユーザーにポリシーを割り当てます。

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Shared Power Appsがブロックされたカスタム アプリアクセス許可ポリシーの例のスクリーンショット。":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>監査ログを使用して Microsoft Power Platform のインストール アクティビティを調査する

Teamsの監査ログを使用すると、ユーザーがTeamsの [アプリ] ページの [**同僚によってビルド済み]** セクションから Microsoft Power Platform アプリをインストールしたイベントを調査できます。 これを行うには、(**AppInstalled** 操作の下で) **インストール済みアプリ** Teams イベントの [監査ログ](./audit-log-events.md)で、ユーザーまたは一連のユーザーを検索します。 **同僚によってビルドから** インストールされたアプリを見つけるには、特定のレコードの詳細で **AppDistributionMode** プロパティで **TemplatedInstance** 値を探します。

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="AppDistributionMode プロパティの TemplatedInstance 値のスクリーンショット。":::

> [!NOTE]
> フィルター処理を容易にするために、監査レコードを CSV 形式でエクスポートできます。

## <a name="related-topics"></a>関連項目

- [Power Appsでキャンバス アプリを共有する](/powerapps/maker/canvas-apps/share-app)
- [ボットを他のユーザーと共有する](/power-virtual-agents/admin-share-bots)
- [Microsoft Teams管理センターでアプリを管理する](manage-apps.md)
- [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
- [Teams アプリ申請 API を使用して送信されたカスタム アプリを発行する](submit-approve-custom-apps.md)
