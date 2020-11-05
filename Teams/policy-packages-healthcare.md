---
title: 医療用の Teams ポリシーパッケージ
author: lanachin
ms.author: v-lanac
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
description: 医療組織の Teams ポリシーパッケージを使用および管理する方法について説明します。
ms.openlocfilehash: b8317a7f860d0ab8510a6170b69a50f7a3387ebd
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908516"
---
# <a name="teams-policy-packages-for-healthcare"></a>医療用の Teams ポリシーパッケージ

## <a name="overview"></a>概要

Microsoft Teams の [ポリシーパッケージ](manage-policy-packages.md) は、組織内で同様の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。 ポリシー パッケージにより、ポリシー管理を簡素化し、合理化し、一貫性を高めることができます。 パッケージ内のポリシーの設定をカスタマイズして、ユーザーのニーズに合わせることができます。 ポリシーパッケージのポリシーの設定を変更すると、そのパッケージに割り当てられているすべてのユーザーが更新された設定を取得します。 ポリシーパッケージを管理するには、Microsoft Teams 管理センターまたは PowerShell を使用します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

ポリシーパッケージでは、パッケージに応じて、次のポリシーが事前に定義されています。

- Messaging
- 会議
- 通話
- アプリのセットアップ
- ライブ イベント

Teams には現在、以下の医療ポリシーパッケージが含まれています。

|Microsoft Teams 管理センターのパッケージ名|以下の目的での使用に最適です|説明 |
|---------|---------|---------|
|医療診療員  |医療機関向けの臨床従業員  |登録された看護師、料金の看護師、医師、ソーシャルワーカーなどの、チャット、通話、シフト管理、および会議へのフルアクセスを可能にする、一連のポリシーとポリシー設定を作成します。 |
|医療情報の作業者  |医療機関のインフォメーションワーカー |IT 担当者、informatics 職員、財務担当者、コンプライアンス責任者、チャット、通話、会議へのフルアクセスなどの情報を提供する一連のポリシーとポリシー設定を作成します。|
|医療の治療室  |患者室のデバイス|医療機関の患者の会議室に適用される一連のポリシーとポリシー設定を作成します。|

![ヘルスケアポリシーパッケージのスクリーンショット](media/policy-packages-healthcare.png)

個々のポリシーには、ポリシーパッケージの名前が割り当てられているため、ポリシーパッケージにリンクされているポリシーを簡単に識別することができます。 たとえば、医療臨床 worker ポリシーパッケージを組織内の clinicians に割り当てると、パッケージ内のポリシーごとに Healthcare_ClinicalWorker という名前のポリシーが作成されます。

![医療用臨床 worker パッケージのポリシーのスクリーンショット](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a>ポリシーパッケージの概要

医療ポリシーパッケージの概要については、Microsoft 管理センターのオンボードハブで、[ **医療** ] を選んでから、[ **役割別にポリシー設定を割り当てる** ] を選びます。 作業を開始する準備ができたら、組織内の個人を割り当てるポリシーパッケージを決定します。

[ **ポリシーの詳細の表示** ] を選択して、パッケージ内の特定のポリシーとその設定を詳しく確認します。 これらは、Teams 管理センターで割り当て後に [カスタマイズすることができ](manage-policy-packages.md#customize-policies-in-a-policy-package) ます。

割り当てるパッケージを1つまたは複数選択して、[ **次へ** ] をクリックします。 ポリシーパッケージにユーザーを検索して追加することで、その役割に最適です。 1人のユーザーを一度に複数のポリシーパッケージに割り当てることはできません。

適切なポリシーパッケージにユーザーを追加したら、 **[完了** ] で選択内容が終了します。 引き続き、Microsoft Teams 管理センターでポリシーパッケージのカスタマイズと管理を行うことができます。

## <a name="manage-policy-packages"></a>ポリシー パッケージを管理する

### <a name="view"></a>表示

パッケージを割り当てる前に、ポリシーパッケージの各ポリシーの設定を表示します。 Microsoft Teams 管理センターの左のナビゲーションで、[ **ポリシーパッケージ** ] に移動し、パッケージ名を選択して、ポリシー名を選びます。

定義済みの値が組織に適しているかどうかを判断します。または、組織のニーズに基づいて、ユーザー設定の値をカスタマイズする必要があるかどうかを決定します。

### <a name="customize"></a>カスタマイズ

組織のニーズに合わせて、ポリシーパッケージのポリシーの設定を必要に応じてカスタマイズします。 ポリシー設定に加えた変更は、パッケージを割り当てられたユーザーに自動的に適用されます。 ポリシーパッケージ内のポリシーの設定を編集するには、Microsoft Teams 管理センターの左側のナビゲーションで [ **ポリシー** パッケージ] に移動し、ポリシーパッケージを選び、編集するポリシーの名前を選んで、[ **編集** ] を選びます。

ポリシーパッケージを割り当てると、パッケージのポリシーの設定を変更できることに注意してください。 詳細については、「 [ポリシーパッケージの](manage-policy-packages.md#customize-policies-in-a-policy-package)ポリシーをカスタマイズする」を参照してください。

### <a name="assign"></a>割り当てる

ポリシーパッケージをユーザーに割り当てます。 ユーザーにポリシーが割り当てられていて、後で別のポリシーを割り当てると、最新の割り当てが優先されます。

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>1人または複数のユーザーにポリシーパッケージを割り当てる

ポリシーパッケージを1人または複数のユーザーに割り当てるには、Microsoft Teams 管理センターの左側のナビゲーションで [ **ポリシーパッケージ** ] に移動し、[ **ユーザーの管理** ] を選択します。  

![管理センターでポリシーパッケージを割り当てる方法のスクリーンショット](media/policy-packages-healthcare-assign.png)

詳細については、「 [ポリシーパッケージを割り当てる](manage-policy-packages.md#assign-a-policy-package)」を参照してください。

ユーザーにポリシーが割り当てられていて、後で別のポリシーを割り当てると、最新の割り当てが優先されます。

#### <a name="assign-a-policy-package-to-a-group"></a>ポリシーパッケージをグループに割り当てる

**この機能はプライベートプレビュー**

グループにポリシーパッケージを割り当てると、セキュリティグループや配布リストなど、複数のポリシーをユーザーのグループに割り当てることができます。 ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。 グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。 この方法は、最大5万ユーザーのグループに推奨されますが、大規模なグループでも動作します。

詳細については、「 [ポリシーパッケージをグループに割り当てる](assign-policies.md#assign-a-policy-package-to-a-group)」を参照してください。

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>ポリシーパッケージを大規模なユーザー (バッチ) に割り当てる

バッチポリシーパッケージの割り当てを使用して、一度に多くのユーザーにポリシーパッケージを割り当てます。 [CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation)コマンドレットを使用して、ユーザーのバッチと、割り当てるポリシーパッケージを送信します。 割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。

バッチには最大 5,000 のユーザーを含めることができます。 ユーザーは、オブジェクト Id、UPN、SIP アドレス、またはメールアドレスで指定できます。 詳細については、「 [ユーザーのバッチにポリシーパッケージを割り当てる](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)」を参照してください。

## <a name="related-topics"></a>関連項目

[Teams でポリシー パッケージを管理する](manage-policy-packages.md)

[チームのユーザーにポリシーを割り当てる](assign-policies.md)
