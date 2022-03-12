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
description: Microsoft Power Platform 上に構築されたカスタム アプリへのアクセスを管理する方法については、Microsoft Teamsしてください。
ms.openlocfilehash: c093d432faa8d4977f4d931ac948a35dc6fe6509
ms.sourcegitcommit: c7b95254dec4420ba0a697fd49d11b448364c919
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2022
ms.locfileid: "63442673"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターで Microsoft Power Platform アプリを管理する

## <a name="microsoft-power-platform-apps-in-teams"></a>Microsoft Power Platform アプリ (Teams

この記事では、管理センターで [Microsoft Power Platform](https://powerplatform.microsoft.com/) アプリを管理する方法のMicrosoft Teams説明します。

> [!NOTE]
> この記事は、組織の作成者が作成したカスタム アプリに適用され、Power AppsまたはPower Virtual Agents。 これらのカスタム アプリは、アプリに自動的Teams。 この記事は、[アプリ] ページからインストールされている Power Apps アプリまたは Power Virtual Agents アプリには適用されません。アプリセットアップ ポリシーを使用して Teams にピン留めされています。 これらのアプリは、[アプリの管理] ページの他のアプリ[](manage-apps.md)と同様に、アプリ[](teams-app-permission-policies.md)のアクセス許可ポリシーとアプリ設定ポリシーを[使用して管理します](teams-app-setup-policies.md)。

[Power Apps](https://powerapps.microsoft.com)は、組織内のメーカーがビジネス データに接続するカスタム アプリを構築するために使用できる、低コード/コードなしアプリケーションの開発環境です。 [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents)は、メーカーが強力なボットを作成するコードなしボット構築環境です。 microsoft Power Platform アプリを Teams に統合すると、組織はビジネス プロセスを合理化し、変化するビジネス ニーズに迅速に対応してコラボレーションを強化し、より生産的なカスタム ソリューションを作成して共有することができます。  

組織内のメーカーによって作成された Microsoft Power Platform アプリは、自動的にアプリにTeams。 作成者は、Power Apps の共有機能とアプリの共有[](/powerapps/maker/canvas-apps/share-app)機能を使用して、アプリにアクセスできるユーザー[をPower Virtual Agents](/power-virtual-agents/admin-share-bots)。

Microsoft Power Platform **** >  アプリが作成または共有されると、ユーザーは[組織名のビルド]に移動して[アプリ] ページで表示およびインストールできます。同僚が作成 **します**。 (アプリが作成または共有された後、アプリがここに表示されるには数分かかる場合があります)。

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="同僚が作成した Microsoft Power Platform アプリを示す [アプリ] ページのスクリーンショット":::

アプリが次のいずれかの条件を満たしている場合、ユーザーには [ **Built by your colleagues** ] にアプリが表示されます。

|Power Apps |Power Virtual Agents  |
|---------|---------|
|<ul><li>ユーザーがアプリを作成しました。</li><li>アプリはユーザーと直接共有されています。</li><li>ユーザーが最近アプリを使用しました。 </li></ul>| <ul><li>ユーザーがボットを作成しました。</li><li>ボットは、ユーザーがメンバーであるチームによって所有されます。 </li></ul>        |

ユーザーは、他のアプリと同じ方法で Microsoft Power Platform アプリをTeamsします。 ユーザーは、自分が所有するチーム、自分が参加しているチャット、個人スコープなど、アクセス許可を持つコンテキストにのみアプリをインストールできます。

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターで Microsoft Power Platform アプリへのアクセスを管理する

管理者は、Microsoft Power Platform アプリが[Built **by your** colleagues] (同僚が作成したアプリ) にリストされるかどうかを、Teams の [アプリ] ページで制御できます。 Power Apps で作成されたアプリまたは Power Virtual Agents で作成されたアプリはすべて、[アプリの管理] ページの組織レベルで、またはアプリのアクセス許可[](manage-apps.md)ポリシーを使用して特定のユーザーに対して、まとめてブロックまたは許可[できます。](teams-app-permission-policies.md)

組織 **のPower Apps** アプリ ストアの **Shared Power Virtual Agent Apps アプリと Shared Power Virtual Agent Apps** アプリは、その特定のプラットフォームで作成されたアプリを表します。 組織レベルまたは特定のユーザーに対してこれらのアプリの一方または両方をブロックした場合、それらのユーザーは、同僚によって構築されたこれらのプラットフォームのアプリを表示できないので、Teams にアプリをインストールできません。  

Power Apps と Power Virtual Agents で作成されたアプリへのアクセスはすべて制御できますが、個々のアプリを許可またはブロックすることはできません。 作成者は、共有機能を使用して作成したアプリにアクセスできるユーザーを、Power AppsおよびPower Virtual Agents。 メーカーが Power Virtual Agents で作成したアプリをユーザーと共有し、そのユーザーの **共有 Power Virtual Agents アプリ** をブロックした場合、ユーザーは Teams のそのプラットフォームからアプリを表示またはインストールすることはできません。

ユーザーが Power Apps または Power Virtual Agents からアプリへのアクセスを許可され、ユーザーがこれらのプラットフォームの一方または両方からアプリにアクセスするのをブロックした場合、ユーザーはアプリまたはアプリをブロックする前に、インストールした Microsoft Power Platforms アプリに引き続きアクセスして使用できます。 ただし、ユーザーは[Built by your colleagues]を使用してこれらのプラットフォームからアプリを表示または **インストールできなくなりました**。

> [!NOTE]
> [**アプリの管理]** ページの [カスタム アプリとの対話を [](manage-apps.md)許可する] 設定は、組織内のすべてのユーザーに適用され、カスタム アプリを操作できるかどうかを制御します。 組織全体のアプリ設定は、すべてのユーザーの動作を管理し、ユーザーに割り当てられた他のアプリ権限ポリシーを上書きします。 既定では、この設定は[オン] に設定されています。 この設定がオフになっている場合、組織内のユーザーは、Microsoft Power Platform アプリを含むカスタム アプリを表示またはインストールできます。 詳細については、「組織全体のアプリ [設定を管理する」を参照してください](manage-apps.md#manage-org-wide-app-settings)。

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>組織で Microsoft Power Platform アプリを許可またはブロックする

既定では、**組織内Power Apps** のすべてのユーザーに対して、Shared **Power Virtual Agent Apps と Shared Power Virtual Agent Apps** Teams許可されます。 管理センターの [アプリの管理] ページで、組織[](manage-apps.md)レベルでブロックMicrosoft Teamsできます。  

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。 ページにアクセスするには、グローバル管理者Teamsサービス管理者である必要があります。
2. アプリの一覧で、次のいずれかの操作を行います。

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="共有 Microsoft Power Platform アプリを表示した [アプリの管理] ページのスクリーンショット":::

    - 組織内のすべてのユーザーについて Power Apps または Power Virtual Agents で作成されたアプリをブロックするには、[共有 **Power Apps**] または [**共有 Power Virtual Agent アプリ**] を検索して選択し、[ブロック] **をクリックします**。
    - 組織内のすべてのユーザーに対して Power Apps または Power Virtual Agents で作成されたアプリを許可するには、[共有 **Power Apps**] または [**共有 Power Virtual Agent アプリ**] を検索して選択し、[許可] をクリックします。

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>特定のユーザーに対して Microsoft Power Platform アプリを許可またはブロックする

組織内の特定のユーザーが Power Apps または Power Virtual Agents で作成されたアプリへのアクセスを許可またはブロックするには、1 つ以上のカスタム アプリアクセス許可ポリシーを作成して割り[当てる必要があります](teams-app-permission-policies.md)。

たとえば、特定のユーザーが Power Apps で作成したアプリへのアクセスをブロックするには、カスタム アプリのアクセス許可ポリシーを作成して共有 **Power Apps** をブロックし、そのユーザーにポリシーを割り当てる必要があります。

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="共有アプリがブロックされているカスタム アプリのアクセス許可ポリシー Power Appsスクリーンショット。":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>監査ログを使用して Microsoft Power Platform のインストール アクティビティを調査する

Teams の監査ログを使用すると、ユーザーが Microsoft Power Platform アプリをインストールしたイベントを調査できます。このイベントは、Teams の [アプリ] ページの [Built **by your colleagues**] セクションから行います。 これを行 [うには、(](./audit-log-events.md)**AppInstalled** 操作の下にある) インストール済み **アプリ Teams イベント** の監査ログで、ユーザーまたは一連のユーザーを検索します。 同僚によってビルドされたアプリを見つけるには、特定のレコードの詳細で **AppDistributionMode** プロパティの **TemplatedInstance** 値を探します。

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="AppDistributionMode プロパティの TemplatedInstance 値のスクリーンショット。":::

> [!NOTE]
> フィルター処理を容易にするために、監査レコードを CSV 形式でエクスポートできます。

## <a name="related-topics"></a>関連項目

- [Power Apps でキャンバス アプリを共有する](/powerapps/maker/canvas-apps/share-app)
- [ボットを他のユーザーと共有する](/power-virtual-agents/admin-share-bots)
- [管理センターでアプリMicrosoft Teams管理する](manage-apps.md)
- [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
- [Teams App Submission API を使用して送信されたカスタム アプリを発行する](submit-approve-custom-apps.md)
