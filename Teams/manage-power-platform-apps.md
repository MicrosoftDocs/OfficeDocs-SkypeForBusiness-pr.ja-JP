---
title: Microsoft Teams 管理センターで Microsoft Power Platform アプリを管理する
author: lanachin
ms.author: v-lanac
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
description: Microsoft Teams 管理センターで Microsoft Power Platform 上に構築されたカスタムアプリへのアクセスを管理する方法について説明します。
ms.openlocfilehash: 5675083c3a7b0aaea2fb053609cbf7da800dbe42
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753572"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターで Microsoft Power Platform アプリを管理する

## <a name="microsoft-power-platform-apps-in-teams"></a>Teams の Microsoft Power Platform アプリ

この記事では、microsoft Teams 管理センターで [Microsoft Power Platform](https://powerplatform.microsoft.com/) アプリを管理する方法の概要について説明します。

> [!NOTE]
> この記事は、Power Apps または Power Virtual Agent を使用して、組織内のメーカーによって作成されたカスタムアプリを対象としています。 これらのカスタムアプリは、自動的に Teams に追加されます。 この記事は、アプリのページからインストールされた、またはアプリセットアップポリシーによってチームにピン留めされた Power Apps アプリや Power Virtual Agent アプリには適用されません。 これらのアプリは、[アプリの [管理](manage-apps.md) ] ページの他のアプリと同様に、 [アプリのアクセス許可ポリシー](teams-app-permission-policies.md)とアプリの [セットアップポリシー](teams-app-setup-policies.md)を使って管理します。

[Power Apps](https://powerapps.microsoft.com) は、組織内の開発者が、ビジネスデータに接続するカスタムアプリを構築するために使用できる低コード/コードなしのアプリケーション開発環境です。 [Power Virtual agent](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) は、開発者が強力なボットを作成するためのコードなしボット構築環境です。 Microsoft の Power Platform アプリを Teams に統合することで、組織はビジネスプロセスを合理化し、変化するビジネスニーズに迅速に対応してコラボレーションを強化し、ユーザー設定のソリューションを作成および共有して生産性を高めることができます。  

組織内のメーカーによって作成された Microsoft Power Platform アプリは、Teams に自動的に追加されます。 メーカーは、 [Power Apps の共有機能](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) と、 [power Virtual agent の共有機能](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)を使用して、アプリにアクセスできるユーザーを制御できます。

Microsoft Power Platform アプリを作成または共有した場合、ユーザーは、同僚によって作成された***組織名に合わせ*** て [アプリ] ページで表示およびインストールでき  >  **Built by your colleagues**ます。 アプリを作成または共有した後で、アプリがここに表示されるまでに数分かかることがあります。

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="同僚が作成した Microsoft Power Platform アプリが表示されている [アプリ] ページのスクリーンショット":::

アプリが次のいずれかの条件を満たしている場合、ユーザーには、 **同僚によって作成** されたアプリが表示されます。

|Power Apps |Power Virtual Agent  |
|---------|---------|
|<ul><li>ユーザーがアプリを作成しました。</li><li>アプリはユーザーと直接共有されました。</li><li>ユーザーが最近アプリを使用しました。 </li></ul>| <ul><li>ユーザーがボットを作成しました。</li><li>ボットは、ユーザーが所属するチームによって所有されています。 </li></ul>        |

ユーザーは、他の Teams アプリをインストールする場合と同じ方法で、Microsoft Power Platform アプリをインストールします。 ユーザーは、アクセス許可が与えられているコンテキスト (自分が所有するチーム、所属しているチャット、個人のスコープなど) にのみアプリをインストールできることに注意してください。

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターで Microsoft Power Platform アプリへのアクセスを管理する

管理者として、Teams の [アプリ] ページで [ **同僚が作成** した Microsoft Power Platform] アプリがリストされているかどうかを制御できます。 [ [アプリの管理](manage-apps.md) ] ページの組織レベルで、または [アプリのアクセス許可ポリシー](teams-app-permission-policies.md)を使用する特定のユーザーに対して、Power Apps または power Virtual agent で作成されたすべてのアプリを、一括ブロックまたは許可することができます。

組織のアプリストアで共有されている **Power apps** アプリと **Power Virtual Agent アプリ** アプリは、その特定のプラットフォームで作成されたすべてのアプリを表します。 これらのアプリを組織レベルでブロックするか、または特定のユーザーに対してブロックすると、それらのユーザーは、 **同僚によって構築** されているプラットフォームのアプリを表示することはできません。これらのアプリを Teams にインストールすることはできません。  

Power Apps と Power Virtual Agent で作成されたすべてのアプリへのアクセスを制御することはできますが、個々のアプリを許可またはブロックすることはできません。 メーカーは、Power Apps と Power Virtual Agent 内の共有機能を通じて作成されたアプリにだれがアクセスできるかを決定します。 メーカーが、Power Virtual Agent でユーザーと共に作成されたアプリを共有している場合、そのユーザーに対して **共有の Power Virtual Agent アプリ** をブロックすると、そのユーザーはチーム内のそのプラットフォームのアプリを表示したりインストールしたりすることはできなくなります。

ユーザーが Power Apps または Power Virtual Agent からアプリにアクセスすることを許可されている場合、そのユーザーがこれらのプラットフォームのいずれかまたは両方からアプリにアクセスするのをブロックすると、ユーザーはアプリやアプリをブロックする前にインストールされた Microsoft Power app アプリにアクセスして使用することができます。 ただし、ユーザーは、 **同僚によって構築**されたこれらのプラットフォームのアプリを表示したりインストールしたりすることはできなくなります。

> [!NOTE]
> [[アプリの管理](manage-apps.md)] ページの [**カスタムアプリでの操作を許可する**] は、組織内のすべてのユーザーに適用され、ユーザーがカスタムアプリを操作できるかどうかを制御します。 組織全体のアプリの設定では、すべてのユーザーに対する動作が管理され、ユーザーに割り当てられている他のアプリのアクセス許可ポリシーは上書きされます。 既定では、この設定はオンになっています。 この設定を無効にした場合、組織のユーザーは、Microsoft Power Platform アプリなどのカスタムアプリを表示またはインストールすることはできません。 詳細については、「 [組織全体のアプリ設定を管理](manage-apps.md#manage-org-wide-app-settings)する」を参照してください。

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>組織に対して Microsoft Power Platform アプリを許可またはブロックする

既定では、組織内のすべての Teams ユーザーに対して、 **共有の Power Apps** **アプリと共有 power Agent アプリ** が許可されています。 Microsoft Teams 管理センターの [ [アプリの管理](manage-apps.md) ] ページでは、組織レベルでそれらのユーザーをブロックまたは許可することができます。  

1. Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動  >  **Manage apps**します。 ページにアクセスするには、グローバル管理者または Teams サービス管理者である必要があります。
2. アプリの一覧で、次のいずれかの操作を行います。

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="共有されている Microsoft Power Platform アプリが表示された [アプリの管理] ページのスクリーンショット":::

    - 組織内のすべてのユーザーに対して、Power Apps または Power Virtual agent で作成されたアプリをブロックするには、 **共有の Power apps** または **共有の Power virtual Agent アプリ**を検索して選択し、[ **ブロック**] をクリックします。
    - 組織内のすべてのユーザーに対して、Power Apps または Power Virtual Agent で作成されたアプリを許可するには、 **共有の Power apps** または **共有の Power virtual Agent アプリ**を検索して選択し、[ **許可**] をクリックします。

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>特定のユーザーに対して Microsoft Power Platform アプリを許可またはブロックする

組織内の特定のユーザーが、Power Apps または Power Virtual Agent で作成されたアプリにアクセスすることを許可または禁止するには、1つ以上のカスタム [アプリのアクセス許可ポリシー](teams-app-permission-policies.md)を作成して割り当てます。 

たとえば、特定のユーザーが Power Apps で作成されたアプリにアクセスするのをブロックするには、共有された **Power apps**をブロックするカスタムアプリのアクセス許可ポリシーを作成し、そのユーザーにポリシーを割り当てます。

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="共有の Power Apps がブロックされたカスタムアプリのアクセス許可ポリシーの例のスクリーンショット":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>監査ログを使用して Microsoft Power Platform のインストールアクティビティを調査する

Teams の監査ログを使って、ユーザーが Teams の [アプリ] ページの [ **同僚によって作成** された Microsoft Power Platform] セクションから Microsoft Power Platform アプリをインストールしたイベントを調査できます。 これを行うには、ユーザーまたはユーザーのセットに対し**て、インストールされているアプリ**チームイベント ( **appinstalled**操作の下) の[監査ログを検索](https://docs.microsoft.com/microsoftteams/audit-log-events)します。 **同僚によっ**てインストールされたアプリを見つけるには、特定のレコードの詳細にある**app荷 Mode**プロパティの**TemplatedInstance**値を探します。 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="App荷 Mode プロパティの TemplatedInstance 値のスクリーンショット":::

> [!NOTE]
> 簡単にフィルター処理できるように、CSV 形式で監査レコードをエクスポートすることができます。

## <a name="related-topics"></a>関連項目

- [Power Apps で canvas アプリを共有する](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)
- [ボットを他のユーザーと共有する](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)
- [Microsoft Teams 管理センターでアプリを管理する](manage-apps.md)
- [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
- [Teams アプリ申請 API を通じて送信されたカスタムアプリを公開する](submit-approve-custom-apps.md)
