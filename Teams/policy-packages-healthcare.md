---
title: ヘルスケア向けの Teams ポリシー パッケージ
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
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 医療組織用の Teams ポリシー パッケージを使用および管理する方法について説明します。
ms.openlocfilehash: 830b8fc5f6938f84f188f5f5d732a3ecfd6eb5b1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117765"
---
# <a name="teams-policy-packages-for-healthcare"></a>ヘルスケア向けの Teams ポリシー パッケージ

## <a name="overview"></a>概要

Microsoft Teams の[ポリシー パッケージ](manage-policy-packages.md)は、組織内で類似の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。 ポリシー パッケージにより、ポリシー管理を簡素化し、合理化し、一貫性を高めることができます。 ユーザーのニーズに合わせて、パッケージのポリシーの設定をカスタマイズできます。 ポリシー パッケージ内のポリシーの設定を変更すると、そのパッケージに割り当てられているすべてのユーザーが更新された設定を取得します。 Microsoft Teams 管理センターまたは PowerShell を使用して、ポリシー パッケージを管理できます。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

ポリシー パッケージは、以下に対するポリシーを事前に定義しており、内容はパッケージごとに異なります。

- メッセージング
- 会議
- 通話
- アプリのセットアップ
- ライブ イベント

Microsoft Teams には現在、次のヘルスケア ポリシー パッケージが含まれています。

|Microsoft Teams 管理センターのパッケージ名|以下の目的での使用に最適です|説明 |
|---------|---------|---------|
|医療施設の職員  |貴社の医療組織の医療者  |一連のポリシーとポリシー設定を作成して、登録済看護師、担当看護師、医師、およびソーシャル ワーカーに対して、チャット、通話、シフト管理、会議へのフル アクセスを提供します。 |
|医療情報提供者  |医療組織の情報提供者 |一連のポリシーとポリシー設定を作成して、IT 担当者、情報スタッフ、財務担当者、法令遵守責任者に対して、チャット、通話、会議へのフル アクセスを提供します。|
|医療患者室  |患者室のデバイス|貴社の医療組織の患者室に適用される一連のポリシーとポリシー設定を作成します。|

![ヘルスケア ポリシー パッケージのスクリーンショット](media/policy-packages-healthcare.png)

ポリシー パッケージにリンクされているポリシーを容易に識別できるように、個々のポリシーにはポリシー パッケージ名が付けられます。 たとえば、医療職員のポリシー パッケージを組織内の臨床医に割り当てると、パッケージ内のポリシーごとに Healthcare_ClinicalWorker という名称のポリシーが作成されます。

![医療職員パッケージのポリシーのスクリーンショット](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a>ポリシー パッケージの概要

医療ポリシー パッケージの使用を開始するには、Microsoft 管理センターのオンボーディング ハブで、[**Healthcare**] を選択し、[**役割によってポリシー設定を割り当てる**] を選択します。 開始する準備ができたら、組織内のユーザーに割り当てるポリシー パッケージを決定します。

パッケージの特定のポリシーの詳細と各設定を確認するには、[**ポリシーの詳細の表示**] を選択します。 Teams 管理センターでの割り当て後にこれらは、[カスタマイズすることができます](manage-policy-packages.md#customize-policies-in-a-policy-package)。

割り当てるパッケージを 1 つ以上選択し、[**次へ**] をクリックします。 役割に最適なポリシー パッケージを検索して、ユーザーをそこに追加できます。 1 人のユーザーを複数のポリシー パッケージに同時に割り当てることはできません。

適切なポリシー パッケージにユーザーを追加したら、[**完了**] をクリックして、終了します。 Microsoft Teams 管理センターで引き続きポリシー パッケージをカスタマイズおよび管理できます。

## <a name="manage-policy-packages"></a>ポリシー パッケージを管理する

### <a name="view"></a>表示

パッケージを割り当てる前に、ポリシー パッケージ内の各ポリシーの設定を表示します。 Microsoft Teams 管理センターの左側のナビゲーションで、[**ポリシーパッケージ**] に移動して、パッケージ名を選択して、ポリシー名を選択します。

事前に定義された値が組織に適しているかどうか、または組織のニーズに基づいてより厳しくあるいは緩めにユーザーをカスタマイズする必要があるかどうかを判断します。

### <a name="customize"></a>カスタマイズ

組織のニーズに合わせてポリシー パッケージのポリシーの設定をカスタマイズします。 ポリシー設定の変更は、パッケージが割り当てられているユーザーに自動的に適用されます。 ポリシー パッケージ内のポリシーの設定を編集するには、Microsoft Teams 管理センターの左側のナビゲーションで、[**ポリシー パッケージ**] に移動して、編集するポリシーの名前を選択した後、[**編集**] を選択します。

ポリシー パッケージを割り当てると、パッケージ内のポリシーの設定を変更することもできます。 詳細については、[「ポリシー パッケージのポリシーをカスタマイズする」](manage-policy-packages.md#customize-policies-in-a-policy-package)を参照してください。

### <a name="assign"></a>割り当て

ユーザーにポリシー パッケージを割り当てる。 ユーザーにポリシーが割り当てられている場合は、別のポリシーを割り当てると、最新の割り当てが優先されます。

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