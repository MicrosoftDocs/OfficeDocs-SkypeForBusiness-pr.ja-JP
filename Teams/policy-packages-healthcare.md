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
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: 医療組織の Teams ポリシーパッケージを使用および管理する方法について説明します。
ms.openlocfilehash: e7b01935969105abae447ae896480e1faf67fa40
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578218"
---
# <a name="teams-policy-packages-for-healthcare"></a>医療用の Teams ポリシーパッケージ

## <a name="overview"></a>概要

Microsoft Teams の[ポリシーパッケージ](manage-policy-packages.md)は、組織内で同様の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。 ポリシー パッケージにより、ポリシー管理を簡素化し、合理化し、一貫性を高めることができます。 パッケージ内のポリシーの設定をカスタマイズして、ユーザーのニーズに合わせることができます。 ポリシーパッケージのポリシーの設定を変更すると、そのパッケージに割り当てられているすべてのユーザーが更新された設定を取得します。 ポリシーパッケージを管理するには、Microsoft Teams 管理センターまたは PowerShell を使用します。

ポリシーパッケージでは、パッケージに応じて、次のポリシーが事前に定義されています。

- 会議
- ライブ イベント
- 通話
- メッセージング
- Teams
- アプリのセットアップ

Teams には現在、以下の医療ポリシーパッケージが含まれています。

|Microsoft Teams 管理センターのパッケージ名|以下の目的での使用に最適です|説明 |
|---------|---------|---------|
|医療診療員  |医療機関向けの臨床従業員  |登録された看護師、料金の看護師、医師、ソーシャルワーカーなどの、チャット、通話、シフト管理、および会議へのフルアクセスを可能にする、一連のポリシーとポリシー設定を作成します。 |
|医療情報の作業者  |医療機関のインフォメーションワーカー |IT 担当者、informatics 職員、財務担当者、コンプライアンス責任者、チャット、通話、会議へのフルアクセスなどの情報を提供する一連のポリシーとポリシー設定を作成します。|
|医療の治療室  |患者室のデバイス|医療機関の患者の会議室に適用される一連のポリシーとポリシー設定を作成します。|

![ヘルスケアポリシーパッケージのスクリーンショット](media/policy-packages-healthcare.png)

個々のポリシーには、ポリシーパッケージの名前が割り当てられているため、ポリシーパッケージにリンクされているポリシーを簡単に識別することができます。 たとえば、医療臨床 worker ポリシーパッケージを組織内の clinicians に割り当てると、パッケージ内のポリシーごとに Healthcare_ClinicalWorker という名前のポリシーが作成されます。

![医療用臨床 worker パッケージのポリシーのスクリーンショット](media/policy-packages-healthcare-clinical-worker.png)

## <a name="manage-policy-packages"></a>ポリシー パッケージを管理する

### <a name="view"></a>表示

パッケージを割り当てる前に、ポリシーパッケージの各ポリシーの設定を表示します。 Microsoft Teams 管理センターの左のナビゲーションで、[**ポリシーパッケージ**] を選択し、パッケージ名を選択して、ポリシー名を選びます。

定義済みの値が組織に適しているかどうかを判断します。または、組織のニーズに基づいて、ユーザー設定の値をカスタマイズする必要があるかどうかを決定します。

### <a name="customize"></a>カスタマイズ

組織のニーズに合わせて、ポリシーパッケージのポリシーの設定を必要に応じてカスタマイズします。 ポリシー設定に加えた変更は、パッケージを割り当てられたユーザーに自動的に適用されます。 ポリシーパッケージ内のポリシーの設定を編集するには、Microsoft Teams 管理センターでポリシーパッケージを選び、編集するポリシーの名前を選んで、[**編集**] を選びます。

ポリシーパッケージを割り当てると、パッケージのポリシーの設定を変更できることに注意してください。 詳細については、「[ポリシーパッケージの](manage-policy-packages.md#customize-policies-in-a-policy-package)ポリシーをカスタマイズする」を参照してください。 

### <a name="assign"></a>割り当てる

ポリシーパッケージをユーザーに割り当てます。 ポリシーパッケージを1人または複数のユーザーに割り当てるには、[**ユーザーの管理**] をクリックします。 PowerShell を使用して、ユーザーの大規模なバッチにポリシーパッケージを割り当てることもできます。 ポリシーパッケージを割り当てる手順については、「[ポリシーパッケージを割り当てる](manage-policy-packages.md#assign-a-policy-package)」をご覧ください。

![管理センターでポリシーパッケージを割り当てる方法のスクリーンショット](media/policy-packages-healthcare-assign.png)

ユーザーにポリシーが割り当てられていて、後で別のポリシーを割り当てると、最新の割り当てが優先されます。

## <a name="related-topics"></a>関連項目

[Teams でポリシー パッケージを管理する](manage-policy-packages.md)

[チームのユーザーにポリシーを割り当てる](assign-policies.md)
