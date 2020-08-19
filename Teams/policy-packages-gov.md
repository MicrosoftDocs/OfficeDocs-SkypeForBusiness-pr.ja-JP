---
title: Government の Teams ポリシーパッケージ
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
description: 政府機関組織の Teams ポリシーパッケージを使用および管理する方法について説明します。
ms.openlocfilehash: 738197a82303c1149ebc89a8e3ad7c6b37df90eb
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804033"
---
# <a name="teams-policy-packages-for-government"></a>Government の Teams ポリシーパッケージ

> [!NOTE]
> ポリシーパッケージは、現在、Microsoft 365 Government GCC 高または米国の展開では利用できません。

## <a name="overview"></a>概要

Microsoft Teams の [ポリシーパッケージ](manage-policy-packages.md) は、組織内で同様の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。 ポリシー パッケージにより、ポリシー管理を簡素化し、合理化し、一貫性を高めることができます。 パッケージ内のポリシーの設定をカスタマイズして、ユーザーのニーズに合わせることができます。 ポリシーパッケージのポリシーの設定を変更すると、そのパッケージに割り当てられているすべてのユーザーが更新された設定を取得します。 ポリシーパッケージを管理するには、Microsoft Teams 管理センターまたは PowerShell を使用します。

ポリシーパッケージでは、パッケージに応じて、次のポリシーが事前に定義されています。

- Messaging
- 会議
- 通話
- アプリのセットアップ
- ライブ イベント

現在、Teams には、政府向けの次のポリシーパッケージが含まれています。

|Microsoft Teams 管理センターのパッケージ名|以下の目的での使用に最適です|説明 |
|---------|---------|---------|
|公安責任者  |政府機関組織の公安責任者  |組織の公衆安全責任者に適用される一連のポリシーとポリシー設定を作成します。 |
|Firstline manager  |政府機関組織の firstline Manager |一連のポリシーを作成し、組織の Firstline Manager にそれらの設定を適用します。|
|Firstline worker  |政府機関組織の firstline 員 |一連のポリシーを作成し、それらの設定を組織の Firstline Worker に適用します。|

![ヘルスケアポリシーパッケージのスクリーンショット](media/policy-packages-gov.png)

個々のポリシーには、ポリシーパッケージの名前が割り当てられているため、ポリシーパッケージにリンクされているポリシーを簡単に識別することができます。 たとえば、パブリックセーフティオフィサーポリシーパッケージを組織内のユーザーに割り当てると、PublicSafety_Officer という名前のポリシーがパッケージ内のポリシーごとに作成されます。

![医療用臨床 worker パッケージのポリシーのスクリーンショット](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a>ポリシー パッケージを管理する

### <a name="view"></a>表示

パッケージを割り当てる前に、ポリシーパッケージの各ポリシーの設定を表示します。 Microsoft Teams 管理センターの左のナビゲーションで、[ **ポリシーパッケージ**] を選択し、パッケージ名を選択して、ポリシー名を選びます。

定義済みの値が組織に適しているかどうかを判断します。または、組織のニーズに基づいて、ユーザー設定の値をカスタマイズする必要があるかどうかを決定します。

### <a name="customize"></a>カスタマイズ

組織のニーズに合わせて、ポリシーパッケージのポリシーの設定を必要に応じてカスタマイズします。 ポリシー設定に加えた変更は、パッケージを割り当てられたユーザーに自動的に適用されます。 ポリシーパッケージ内のポリシーの設定を編集するには、Microsoft Teams 管理センターでポリシーパッケージを選び、編集するポリシーの名前を選んで、[ **編集**] を選びます。

ポリシーパッケージを割り当てると、パッケージのポリシーの設定を変更できることに注意してください。 詳細については、「 [ポリシーパッケージの](manage-policy-packages.md#customize-policies-in-a-policy-package)ポリシーをカスタマイズする」を参照してください。 

### <a name="assign"></a>割り当てる

ポリシーパッケージをユーザーに割り当てます。 ポリシーパッケージを1人または複数のユーザーに割り当てるには、[ **ユーザーの管理**] をクリックします。 [PowerShell を使用](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation)して、ユーザーの大規模なバッチにポリシーパッケージを割り当てることもできます。 

Microsoft Teams 管理センターまたは PowerShell を使用してポリシーパッケージを割り当てる手順については、「 [ポリシーパッケージを割り当てる](manage-policy-packages.md#assign-a-policy-package)」をご覧ください。

![管理センターでポリシーパッケージを割り当てる方法のスクリーンショット](media/policy-packages-gov-assign.png)

ユーザーにポリシーが割り当てられていて、後で別のポリシーを割り当てると、最新の割り当てが優先されます。

## <a name="related-topics"></a>関連項目

[Teams でポリシー パッケージを管理する](manage-policy-packages.md)

[チームのユーザーにポリシーを割り当てる](assign-policies.md) 
