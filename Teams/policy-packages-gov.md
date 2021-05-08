---
title: Teamsのポリシー パッケージを作成する
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: 政府機関のポリシー パッケージを使用Teams管理する方法について学習します。
ms.openlocfilehash: 891d8762a914a003e3707d8f5eab29b3d8d916c9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117775"
---
# <a name="teams-policy-packages-for-government"></a>Teamsのポリシー パッケージを作成する

> [!NOTE]
> 現在、ポリシー パッケージは、Government Microsoft 365 High または DoD GCCでは使用できません。

## <a name="overview"></a>概要

Microsoft Teams の[ポリシー パッケージ](manage-policy-packages.md)は、組織内で類似の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。 ポリシー パッケージにより、ポリシー管理を簡素化し、合理化し、一貫性を高めることができます。 ユーザーのニーズに合わせて、パッケージのポリシーの設定をカスタマイズできます。 ポリシー パッケージ内のポリシーの設定を変更すると、そのパッケージに割り当てられているすべてのユーザーが更新された設定を取得します。 Microsoft Teams 管理センターまたは PowerShell を使用して、ポリシー パッケージを管理できます。

ポリシー パッケージは、以下に対するポリシーを事前に定義しており、内容はパッケージごとに異なります。

- メッセージング
- 会議
- 通話
- アプリのセットアップ
- ライブ イベント

Teams、政府機関向け次のポリシー パッケージが含まれています。

|Microsoft Teams 管理センターのパッケージ名|以下の目的での使用に最適です|説明 |
|---------|---------|---------|
|公安責任者  |政府機関の公安責任者  |組織内の公安責任者に適用される一連のポリシーとポリシー設定を作成します。 |
|Frontline Manager  |政府機関のフロントライン マネージャー |一連のポリシーを作成し、それらの設定を組織内の Frontline Managers に適用します。|
|Frontline worker  |政府機関のフロントライン ワーカー |一連のポリシーを作成し、それらの設定を組織内の Frontline Worker に適用します。|

![ヘルスケア ポリシー パッケージのスクリーンショット](media/policy-packages-gov.png)

ポリシー パッケージにリンクされているポリシーを容易に識別できるように、個々のポリシーにはポリシー パッケージ名が付けられます。 たとえば、組織内のユーザーに Public safety officer ポリシー パッケージを割り当てると、パッケージ内のポリシーごとに PublicSafety_Officer という名前のポリシーが作成されます。

![医療職員パッケージのポリシーのスクリーンショット](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a>ポリシー パッケージを管理する

### <a name="view"></a>表示

パッケージを割り当てる前に、ポリシー パッケージ内の各ポリシーの設定を表示します。 Microsoft Teams 管理センターの左側のナビゲーションで、[**ポリシーパッケージ**] を選択し、パッケージ名を選択して、ポリシー名を選択します。

事前に定義された値が組織に適しているかどうか、または組織のニーズに基づいてより厳しくあるいは緩めにユーザーをカスタマイズする必要があるかどうかを判断します。

### <a name="customize"></a>カスタマイズ

組織のニーズに合わせてポリシー パッケージのポリシーの設定をカスタマイズします。 ポリシー設定の変更は、パッケージが割り当てられているユーザーに自動的に適用されます。 ポリシー パッケージ内のポリシーの設定を編集するには、Microsoft Teams 管理センターでポリシー パッケージを選び、編集するポリシーの名前を選択して、[**編集**] を選択します。

ポリシー パッケージを割り当てると、パッケージ内のポリシーの設定を変更することもできます。 詳細については、[「ポリシー パッケージのポリシーをカスタマイズする」](manage-policy-packages.md#customize-policies-in-a-policy-package)を参照してください。 

### <a name="assign"></a>割り当て

ポリシー パッケージをユーザーに割り当てます。ユーザーにポリシーが割り当てられている場合は、別のポリシーを割り当てると、最新の割り当てが優先されます。

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>1 人または複数のユーザーにポリシー パッケージを割り当てる

1 人または複数のユーザーにポリシー パッケージを割り当てるには、Microsoft Teams 管理センターの左側のナビゲーションから、[**ポリシー パッケージ**] に移動し、[**ユーザーの管理**] を選択します。  

![管理センターでポリシー パッケージを割り当てる方法のスクリーンショット](media/policy-packages-healthcare-assign.png)

詳細については、[「ポリシー パッケージを割り当てる」](manage-policy-packages.md#assign-a-policy-package)を参照してください。

ユーザーにポリシーが割り当てられている場合は、別のポリシーを割り当てると、最新の割り当てが優先されます。

#### <a name="assign-a-policy-package-to-a-group"></a>ポリシー パッケージをグループに割り当てる

**この機能はプライベート プレビューです**

グループにポリシー パッケージを割り当てると、セキュリティ グループや配布リストなど、ユーザーのグループに複数のポリシーを割り当てることができます。 ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。 グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。 この方法は、最大 50,000 ユーザーのグループに推奨されますが、より大きなグループでも機能します。

詳細については、[「グループにポリシー パッケージを割り当てる」](assign-policies.md#assign-a-policy-package-to-a-group)を参照してください。

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>ポリシー パッケージを多数 (一群) のユーザー セットに割り当てる

バッチ ポリシーパッケージの割り当てを使用して、多数のユーザー セットに同時にポリシーパッケージを割り当てることができます。 [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) コマンドレットを使用して、割り当てたい一群のユーザーおよびポリシー パッケージを送信します。 割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。

バッチには最大 5,000 のユーザーを含めることができます。 ユーザーをオブジェクト ID、UPN、SIP アドレス、またはメール アドレスで指定できます。 詳細については、[「一群のユーザーにポリシー パッケージを割り当てる」](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)を参照してください。

## <a name="related-topics"></a>関連項目

[Teams でポリシー パッケージを管理する](manage-policy-packages.md)

[ Teams でユーザーにポリシーを割り当てる](assign-policies.md)