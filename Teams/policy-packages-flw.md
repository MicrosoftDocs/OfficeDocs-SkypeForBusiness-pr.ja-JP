---
title: 現場担当者向けの Teams ポリシー パッケージ
ms.author: v-lanachin
author: LanaChin
manager: samanro
ms.reviewer: ''
ms.topic: conceptual
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
f1.keywords: ''
ms.custom: ''
ms.localizationpriority: high
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft 365 for frontline workers
description: 組織内現場担当者向けの Teams ポリシー パッケージの使用方法および管理方法について説明します。
ms.openlocfilehash: 790d9bf7dbf90fadf48c9e5e0818d3eddeac4b75
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131216"
---
# <a name="teams-policy-packages-for-frontline-workers"></a>現場担当者向けの Teams ポリシー パッケージ

## <a name="overview"></a>概要

Microsoft Teams の[ポリシー パッケージ](manage-policy-packages.md)は、組織内で類似の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。 ポリシー パッケージにより、ポリシー管理を簡素化し、合理化し、一貫性を高めることができます。

ユーザーのニーズに合わせて、パッケージのポリシーの設定をカスタマイズできます。 ポリシー パッケージ内のポリシーの設定を変更すると、そのパッケージに割り当てられているすべてのユーザーが更新された設定を取得します。 Microsoft Teams 管理センターまたは PowerShell を使用して、ポリシー パッケージを管理できます。

ポリシー パッケージは、以下に対するポリシーを事前に定義しており、内容はパッケージごとに異なります。

- メッセージング
- 会議
- 通話
- アプリのセットアップ
- ライブ イベント

Teams には、**現場マネージャー** ポリシー パッケージと **現場担当者** ポリシー パッケージがあります。

|Microsoft Teams 管理センターのパッケージ名|説明 |
|---------|---------|
|**現場マネージャー** |一連のポリシーを作成し、その設定を組織内の現場マネージャーに適用します。 |
|**現場担当者**  |一連のポリシーを作成し、その設定を組織内の現場担当者に適用します。|

:::image type="content" source="media/policy-packages-flw.png" alt-text="現場ポリシー パッケージのスクリーンショット。" lightbox="media/policy-packages-flw.png":::

ポリシー パッケージにリンクされているポリシーを容易に識別できるように、個々のポリシーにはポリシー パッケージ名が付けられます。 たとえば、現場マネージャーのポリシー パッケージを組織内のストア マネージャーに割り当てると、パッケージ内のポリシーごとに Frontline_Manager という名前のポリシーが作成されます。

:::image type="content" source="media/policy-packages-flw-frontline-manager.png" alt-text="現場マネージャーのポリシー パッケージのポリシーのスクリーンショット。" lightbox="media/policy-packages-flw-frontline-manager.png":::

## <a name="manage-policy-packages"></a>ポリシー パッケージを管理する

### <a name="view"></a>表示

パッケージを割り当てる前に、ポリシー パッケージ内の各ポリシーの設定を表示します。 Microsoft Teams 管理センターの左側のナビゲーションで、[**ポリシーパッケージ**] に移動して、パッケージ名を選択して、ポリシー名を選択します。

事前に定義された値が組織に適しているかどうか、または組織のニーズに基づいてより厳しくあるいは緩めにユーザーをカスタマイズする必要があるかどうかを判断します。

### <a name="customize"></a>カスタマイズ

組織のニーズに合わせてポリシー パッケージのポリシーの設定をカスタマイズします。 ポリシー設定の変更は、パッケージが割り当てられているユーザーに自動的に適用されます。 ポリシー パッケージ内のポリシーの設定を編集するには、Microsoft Teams 管理センターの左側のナビゲーションで、[**ポリシー パッケージ**] に移動して、編集するポリシーの名前を選択した後、[**編集**] を選択します。

ポリシー パッケージを割り当てると、パッケージ内のポリシーの設定を変更することもできます。 詳細については、[「ポリシー パッケージのポリシーをカスタマイズする」](manage-policy-packages.md#customize-policies-in-a-policy-package)を参照してください。

### <a name="assign"></a>割り当て

Assign the policy package to users. If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.

> [!NOTE]
> カスタム ポリシー パッケージの割り当てを受け取るには、各ユーザーに Advanced Communications アドオンが必要です。 詳細については、「[Microsoft Teams 用 Advanced Communications アドオン](/microsoftteams/teams-add-on-licensing/advanced-communications)」を参照してください。

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>1 人または複数のユーザーにポリシー パッケージを割り当てる

1 人または複数のユーザーにポリシー パッケージを割り当てるには、Microsoft Teams 管理センターの左側のナビゲーションから、[**ポリシー パッケージ**] に移動し、[**ユーザーの管理**] を選択します。  

:::image type="content" source="media/policy-packages-flw-frontline-manager-assign.png" alt-text="Teams 管理センターでユーザーにポリシー パッケージを割り当てる方法のスクリーンショット。" lightbox="media/policy-packages-flw-frontline-manager-assign.png":::

詳細については、「[ポリシー パッケージをユーザーに割り当てる](assign-policy-packages.md#assign-a-policy-package-to-users)」を参照してください。

#### <a name="assign-a-policy-package-to-a-group"></a>ポリシー パッケージをグループに割り当てる

グループへのポリシー パッケージの割り当てでは、セキュリティ グループや配布リストなど、複数のポリシーをユーザーのグループに割り当てできます。 ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。 グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。 この方法は、最大 50,000 ユーザーのグループに推奨されますが、より大きなグループでも機能します。

詳細については、[「グループにポリシー パッケージを割り当てる」](assign-policy-packages.md#assign-a-policy-package-to-a-group)を参照してください。

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>ポリシー パッケージを多数 (一群) のユーザー セットに割り当てる

バッチ ポリシーパッケージの割り当てを使用して、多数のユーザー セットに同時にポリシーパッケージを割り当てることができます。 [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) コマンドレットを使用して、割り当てたい一群のユーザーおよびポリシー パッケージを送信します。 割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。

バッチには最大 5,000 のユーザーを含めることができます。 ユーザーは、オブジェクト ID またはセッション開始プロトコル (SIP) アドレスで指定できます。 詳細については、[「一群のユーザーにポリシー パッケージを割り当てる」](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)を参照してください。

## <a name="related-topics"></a>関連項目

- [Teams でポリシー パッケージを管理する](manage-policy-packages.md)
- [ユーザーとグループにポリシー パッケージを割り当てる](assign-policy-packages.md)
