---
title: Microsoft Teams 管理センターで Microsoft Power Platform アプリを管理する
author: cichur
ms.author: v-cichur
manager: serdars
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
localization_priority: Normal
search.appverid: MET150
description: Microsoft Power Platform 上に構築された Microsoft Teams 管理センターでカスタム アプリへのアクセスを管理する方法について説明します。
ms.openlocfilehash: b44bd77a6415be9c9c9454fd96028fdbb8c608c4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831297"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターで Microsoft Power Platform アプリを管理する

## <a name="microsoft-power-platform-apps-in-teams"></a>Teams の Microsoft Power Platform アプリ

この記事では [、Microsoft Teams](https://powerplatform.microsoft.com/) 管理センターで Microsoft Power Platform アプリを管理する方法の概要を説明します。

> [!NOTE]
> この記事は、Power Apps または Power Virtual Agents を使用して組織内のメーカーが作成したカスタム アプリを対象にしています。 これらのカスタム アプリは、Teams に自動的に追加されます。 この記事は、[アプリ] ページからインストールされる Power Apps アプリまたは Power Virtual Agents アプリ、またはアプリセットアップ ポリシーを通じて Teams にピン留めされている Power Apps アプリまたは Power Virtual Agents アプリには適用されません。 これらのアプリは、[アプリの管理] ページで、アプリ[](manage-apps.md)のアクセス許可ポリシーと[](teams-app-permission-policies.md)アプリセットアップ ポリシーを使用して、他のアプリと同じ方法[で管理します](teams-app-setup-policies.md)。

[Power Apps](https://powerapps.microsoft.com) は、組織のメーカーがビジネス データに接続するカスタム アプリを構築するために使用できる、低コード/コードなしアプリケーションの開発環境です。 [Power Virtual Agents は](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) 、強力なボットを作成するメーカー向けコードなしボット構築環境です。 Microsoft Power Platform アプリを Teams に統合すると、組織はビジネス プロセスを合理化し、変化するビジネス ニーズに迅速に対応してコラボレーションを促進し、より生産的なカスタム ソリューションを作成して共有することができます。  

組織内のメーカーによって作成された Microsoft Power Platform アプリは、Teams に自動的に追加されます。 メーカーは [、Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) の共有機能と Power Virtual Agents の共有機能を使用して、アプリにアクセスできる [ユーザーを制御できます](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)。

Microsoft Power Platform アプリを作成または共有すると、同僚が作成した組織名のビルドに移動して ****、[アプリ] ページにアプリを表示して  >  **インストールできます**。 (アプリが作成または共有され、アプリがここに表示されるのに数分かかる場合があります)。

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="同僚が組み込みの Microsoft Power Platform アプリを表示している [アプリ] ページのスクリーンショット":::

アプリが次のいずれかの条件を満たす場合、ユーザーには同僚が組み込みのアプリを表示します。

|Power Apps |Power Virtual Agents  |
|---------|---------|
|<ul><li>ユーザーがアプリを作成しました。</li><li>アプリはユーザーと直接共有されています。</li><li>ユーザーが最近アプリを使用しました。 </li></ul>| <ul><li>ユーザーがボットを作成しました。</li><li>ボットは、ユーザーがメンバーであるチームによって所有されています。 </li></ul>        |

ユーザーは、他の Teams アプリと同じ方法で Microsoft Power Platform アプリをインストールします。 ユーザーは、自分が所有するチーム、自分が参加しているチャット、または個人の範囲など、アクセス許可を持つコンテキストにのみアプリをインストールできます。

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターで Microsoft Power Platform アプリへのアクセスを管理する

管理者は、Microsoft Power Platform アプリを Teams の [アプリ] ページで、同僚が組み込みのアプリに一覧表示するかどうかを制御できます。 Power Apps で作成されたアプリ、または Power Virtual Agents で作成されたアプリをまとめてブロックまたは許可するには[](manage-apps.md)、[アプリの管理] ページの組織レベルで、またはアプリのアクセス許可ポリシーを使用する特定のユーザーに対して行[います。](teams-app-permission-policies.md)

組織 **のアプリ ストアの** 共有 Power Apps アプリと **共有 Power Virtual Agent アプリ** は、その特定のプラットフォームで作成されたアプリを表します。 組織レベルまたは特定のユーザーに対してこれらのアプリの 1 つまたは両方をブロックした場合、それらのユーザーは、同僚によって組み込みのこれらのプラットフォームのアプリを表示できないので、Teams にアプリをインストールできません。  

Power Apps と Power Virtual Agents で作成されたアプリへのアクセスはすべて制御できますが、個々のアプリを許可またはブロックすることはできません。 作成者は、Power Apps と Power Virtual Agents 内から共有機能を使用して、作成したアプリにアクセスできるユーザーを決定します。 メーカーが Power Virtual Agents で作成したアプリをユーザーと共有し、そのユーザーの **共有 Power Virtual Agents アプリ** をブロックした場合、そのユーザーは、そのプラットフォームのアプリを Teams で表示またはインストールすることはできません。

ユーザーが Power Apps または Power Virtual Agents からのアプリへのアクセスを許可され、その後、ユーザーがこれらのプラットフォームの 1 つ以上のプラットフォームからアプリにアクセスできるのをブロックした場合でも、アプリまたはアプリをブロックする前に、インストールした Microsoft Power Platforms アプリにアクセスして使用できます。 ただし、ユーザーは、同僚によって組み込みのこれらのプラットフォームからアプリを表示 **またはインストールできなくなりました**。

> [!NOTE]
> [**アプリの管理**] ページの [カスタム アプリ [](manage-apps.md)の操作を許可する] 組織全体のアプリ設定は、組織内のすべてのユーザーに適用され、カスタム アプリを操作できるかどうかが制御されます。 組織全体のアプリ設定は、すべてのユーザーの動作を制御し、ユーザーに割り当てられている他のアプリのアクセス許可ポリシーを上書きします。 既定では、この設定は[オン] に設定されています。 この設定をオフにすると、組織内のユーザーは、Microsoft Power Platform アプリを含むカスタム アプリを表示またはインストールできない場合があります。 詳細については、「組織全体のアプリ [設定を管理する」を参照してください](manage-apps.md#manage-org-wide-app-settings)。

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>組織の Microsoft Power Platform アプリを許可またはブロックする

既定では、 **組織内のすべての Teams** ユーザーに対して共有 Power Apps と共有 **Power Virtual Agent アプリ** が許可されています。 Microsoft Teams 管理センターの [アプリの管理[](manage-apps.md)] ページで、組織レベルでブロックまたは許可することができます。  

1. Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの [アプリの **管理]**  >  **に移動します**。 ページにアクセスするには、グローバル管理者または Teams サービス管理者である必要があります。
2. アプリの一覧で、次のいずれかの操作を行います。

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="共有 Microsoft Power Platform アプリが表示されている [アプリの管理] ページのスクリーンショット":::

    - 組織内のすべてのユーザーの Power Apps または Power Virtual Agent で作成されたアプリをブロックするには、共有 **Power Apps** または共有 **Power Virtual Agent アプリ** を検索して選び、[ブロック] をクリック **します。**
    - 組織内のすべてのユーザーに対して Power Apps または Power Virtual Agent で作成されたアプリを許可するには、共有 **Power Apps** または共有 **Power Virtual Agent アプリ** を検索して選び、[許可] をクリックします。 

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>特定のユーザーに対して Microsoft Power Platform アプリを許可またはブロックする

組織内の特定のユーザーが Power Apps または Power Virtual Agents で作成されたアプリへのアクセスを許可またはブロックするには、1 つ以上のカスタム アプリのアクセス許可ポリシーを作成して [割り当てる必要があります](teams-app-permission-policies.md)。 

たとえば、特定のユーザーが Power Apps で作成されたアプリにアクセスするのをブロックするには、カスタム アプリのアクセス許可ポリシーを作成して **共有 Power Apps** をブロックし、そのユーザーにポリシーを割り当てします。

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="共有 Power Apps がブロックされたカスタム アプリのアクセス許可ポリシーの例のスクリーンショット":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>監査ログを使用して Microsoft Power Platform のインストール アクティビティを調査する

Teams の監査ログを使用すると、ユーザーが Teams の [アプリ]ページの [ビルド済み] セクションから Microsoft Power Platform アプリをインストールしたイベントを調査できます。 これを行うには **、(AppInstalled** 操作の下で) インストール済み **アプリの** Teams イベントの監査ログを検索し、ユーザーまたは一連のユーザーを検索します。 [](https://docs.microsoft.com/microsoftteams/audit-log-events) 同僚によってビルドされたアプリを見つけるには、指定されたレコードの詳細で **AppDistributionMode** プロパティの **TemplatedInstance** 値を探します。 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="AppDistributionMode プロパティの TemplatedInstance 値のスクリーンショット":::

> [!NOTE]
> フィルター処理を容易にするために、CSV 形式で監査レコードをエクスポートできます。

## <a name="related-topics"></a>関連項目

- [Power Apps でキャンバス アプリを共有する](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)
- [ボットを他のユーザーと共有する](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)
- [Microsoft Teams 管理センターでアプリを管理する](manage-apps.md)
- [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
- [Teams アプリ提出 API を通じて送信されたカスタム アプリを発行する](submit-approve-custom-apps.md)
