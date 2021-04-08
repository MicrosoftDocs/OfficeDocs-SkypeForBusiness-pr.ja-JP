---
title: Microsoft Teams でポリシー パッケージを管理する
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: sekrantz, aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams でポリシー パッケージを使用して管理し、ユーザー グループのポリシーを管理する際に、一貫性を簡素化、合理化、および提供する方法について説明します。
ms.openlocfilehash: 1b7e6e5c6311ebd51b0f00b86953291ed4ac63b3
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2021
ms.locfileid: "51634237"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Microsoft Teams でポリシー パッケージを管理する

Microsoft Teams のポリシー パッケージは、組織内で類似の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。 組織全体のユーザー グループのポリシーを管理する際に、簡素化、合理化、一貫性を確保するために、ポリシー パッケージを構築しました。  

Teams に含まれる [ポリシー パッケージを使用するか](#policy-packages-included-in-teams) 、(プライベート プレビューで) 独自 [のカスタム](#custom-policy-packages) ポリシー パッケージを作成できます。

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="管理センターの [ポリシー パッケージ] ページのスクリーンショット":::

ユーザーのニーズに合わせて、ポリシー パッケージ内のポリシーの設定をカスタマイズできます。 パッケージ内のポリシーの設定を変更すると、そのパッケージに割り当てられているすべてのユーザーが更新された設定を取得します。 ポリシー パッケージを管理するには、Microsoft Teams 管理センターまたは PowerShell を使用します。

## <a name="what-is-a-policy-package"></a>ポリシー パッケージとは

ポリシー パッケージを使用すると、組織全体の特定のユーザー セットに対して許可または制限する Teams の機能を制御できます。 Teams の各ポリシー パッケージは、ユーザー ロールを中心に設計され、その役割に一般的なコラボレーションおよびコミュニケーション アクティビティをサポートする定義済みのポリシーとポリシー設定が含まれています。

ポリシー パッケージは、次の Teams ポリシーの種類をサポートします。

- メッセージング ポリシー
- 会議ポリシー
- アプリセットアップ ポリシー
- 通話ポリシー
- ライブ イベント ポリシー

## <a name="policy-packages-included-in-teams"></a>Teams に含まれるポリシー パッケージ

Teams には現在、次のポリシー パッケージが含まれています。

| パッケージ名 | 説明 |
|---------|---------|
|Education (高等教育学生)    |高等教育の学生に適用されるポリシーとポリシー設定のセットを作成します。|
|Education (小学校の学生)   |プライマリ 学生に適用されるポリシーとポリシー設定のセットを作成します。|
|Education (中等学生)    |第 2 学生に適用されるポリシーとポリシー設定のセットを作成します。         |
|Education (教師)    |教師に適用されるポリシーとポリシー設定のセットを作成します。      |
|Education (リモート学習を使用する小学校教師)    |小学校教師に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。      |
|Education (リモート学習を使用する主な学生)    |小学生に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。      |
|Frontline Manager |一連のポリシーを作成し、それらの設定を組織内の Frontline マネージャーに適用します。 |
|最前線の従業員 |一連のポリシーを作成し、それらの設定を組織内の Frontline ワーカーに適用します。 |
|医療施設の職員  |一連のポリシーとポリシー設定を作成して、登録済看護師、担当看護師、医師、およびソーシャル ワーカーに対して、チャット、通話、シフト管理、会議へのフル アクセスを提供します。 |
|医療情報提供者  |一連のポリシーとポリシー設定を作成して、IT 担当者、情報スタッフ、財務担当者、法令遵守責任者に対して、チャット、通話、会議へのフル アクセスを提供します。|
|医療患者室  |貴社の医療組織の患者室に適用される一連のポリシーとポリシー設定を作成します。|
|中小規模ビジネス ユーザー (Business Voice) |ビジネス ボイス エクスペリエンス用のアプリを含むアプリセットアップ ポリシーを作成します。|
|中小規模ビジネス ユーザー (Business Voice を使用しない) |中小規模のビジネス Teams ユーザーに関連するアプリセットアップ ポリシーを作成します (ビジネスボイス以外のエクスペリエンス)。
|公安責任者   |組織の公安責任者に適用される一連のポリシーとポリシー設定を作成します。|

> [!NOTE]
> Teams の今後のリリースでポリシー パッケージを追加する予定なので、最新の情報を確認してください。  

ポリシー パッケージにリンクされているポリシーを容易に識別できるように、個々のポリシーにはポリシー パッケージ名が付けられます。
たとえば、学校の教師に教育 (教師) ポリシー パッケージを割り当てると、パッケージ内のポリシーごとに Education_Teacher という名前のポリシーが作成されます。

![Education (教師) ポリシー パッケージのスクリーンショット](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>カスタム ポリシー パッケージ

**カスタム ポリシー パッケージは、Government Community Cloud (GCC) ではまだ利用できません**

カスタム ポリシー パッケージを使用すると、組織内で同様の役割を持つユーザーに独自のポリシー セットをバンドルできます。 必要なポリシーの種類とポリシーを追加して、独自のポリシー パッケージを作成します。

新しいカスタム ポリシー パッケージを作成するには、

1. Microsoft Teams 管理センターの左側のナビゲーションで、[ポリシー **パッケージ]** を選択し、[追加] をクリック **します**。

    :::image type="content" source="media/policy-packages-add.png" alt-text="管理センターの [ポリシー パッケージ] ページの [追加] ボタンのスクリーンショット":::

2. パッケージの名前と説明を入力します。

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="新しいカスタム ポリシー パッケージの追加のスクリーンショット":::

3. パッケージに含めるポリシーの種類とポリシー名を選択します。

4. **[保存]** をクリックします。

## <a name="how-to-use-policy-packages"></a>ポリシー パッケージの使い方

組織でポリシー パッケージを使用する方法の概要を次に示します。

![ポリシー パッケージの使い方の概要](media/manage-policy-packages-overview.png)

- **[表示](#view-the-settings-of-a-policy-in-a-policy-package)**: ポリシー パッケージ内のポリシーを表示します。 次に、パッケージを割り当てる前に、パッケージ内の各ポリシーの設定を表示します。 各設定を理解している必要があります。 定義済みの値が組織に適しているのか、または組織のニーズに基づいて制限を厳しくするか、適切に変更する必要があるのかを決定します。

    ポリシーが削除された場合でも、設定は表示できますが、設定は変更されません。 ポリシー パッケージを割り当てると、定義済みの設定で削除されたポリシーが再び作成されます。

- **[カスタマイズ](#customize-policies-in-a-policy-package)**: 組織のニーズに合わせてポリシー パッケージ内のポリシーの設定をカスタマイズします。

- **[割り](#assign-a-policy-package)** 当て: ポリシー パッケージをユーザーに割り当てる。  

> [!NOTE]
> また、パッケージを割り当て後にポリシー パッケージ内のポリシーの設定を変更することもできます。 ポリシー設定の変更は、パッケージが割り当てられているユーザーに自動的に適用されます。

Microsoft Teams 管理センターでポリシー パッケージを表示、割り当て、カスタマイズする手順は次のとおりです。

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>ポリシー パッケージ内のポリシーの設定を表示する

1. Microsoft Teams 管理センターの左側のナビゲーションで、[ポリシー パッケージ] を選択し、パッケージ名の左側をクリックしてポリシー パッケージを選択します。

2. 表示するポリシーをクリックします。

### <a name="customize-policies-in-a-policy-package"></a>ポリシー パッケージ内のポリシーをカスタマイズする

ポリシーの設定は、[ポリシー パッケージ]ページから、または Microsoft Teams 管理センターのポリシー ページに直接移動して編集できます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、次のいずれかの操作を行います。
    - [ **ポリシー パッケージ]** をクリックし、パッケージ名の左側をクリックしてポリシー パッケージを選択します。
    - ポリシーの種類をクリックします。  たとえば、[メッセージング ポリシー **] をクリックします**。

2. 編集するポリシーを選択します。 ポリシー パッケージにリンクされているポリシーは、ポリシー パッケージと同じ名前です。

3. 必要な変更を行い、[保存] をクリック **します**。

### <a name="assign-a-policy-package"></a>ポリシー パッケージを割り当てる

ポリシー パッケージは、個々のユーザー、グループ、またはユーザーのバッチに割り当てできます。 ポリシー パッケージを割り当てる方法の詳細については、「ユーザーとグループにポリシー パッケージを割り当 [てる」を参照してください](assign-policy-packages.md)。

## <a name="related-topics"></a>関連項目

- [ポリシー パッケージを割り当てる](assign-policy-packages.md)
- [EDU 管理者向け Teams ポリシー パッケージ](policy-packages-edu.md)
- [ヘルスケア向けの Teams ポリシー パッケージ](policy-packages-healthcare.md)
- [政府機関向け Teams ポリシー パッケージ](policy-packages-gov.md)
