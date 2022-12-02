---
title: Teams でポリシー パッケージを管理する
ms.author: mabond
author: mkbond007
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
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams でポリシー パッケージを使用、管理、カスタマイズして、ユーザーグループのポリシーを管理する際の一貫性を簡素化、合理化、および提供する方法について説明します。
ms.openlocfilehash: 138b1cada469a71cf844c8a73b1cb12511fc68b2
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2022
ms.locfileid: "69245737"
---
# <a name="managing-policy-packages-in-teams"></a>Teams でのポリシー パッケージの管理

Microsoft Teams のポリシー パッケージは、組織内で類似の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。 組織全体のユーザーグループのポリシーを管理する際に、一貫性を提供するために、ポリシー パッケージを構築しました。  

[Teams に含まれるポリシー パッケージ](#policy-packages-included-in-teams)を使用することも、[独自のカスタム ポリシー パッケージを作成](#custom-policy-packages)することもできます。

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="管理センターの [ポリシー パッケージ] ページのスクリーンショット。" lightbox="media/policy-packages-admin-center.png":::

ユーザーのニーズに合わせて、ポリシー パッケージ内のポリシーの設定をカスタマイズできます。 パッケージ内のポリシーの設定を変更すると、そのパッケージに割り当てられているすべてのユーザーが更新された設定を取得します。 ポリシー パッケージは、Microsoft Teams 管理センターまたは PowerShell を使用して管理します。

## <a name="what-is-a-policy-package"></a>ポリシー パッケージとは

ポリシー パッケージを使用すると、組織全体の特定のユーザー セットに対して許可または制限する Teams 機能を制御できます。 Teams の各ポリシー パッケージは、ユーザー ロールを中心に設計されており、そのロールに一般的なコラボレーションとコミュニケーション アクティビティをサポートする定義済みのポリシーとポリシー設定が含まれています。

ポリシー パッケージでは、次の種類の Teams ポリシーがサポートされています。

- メッセージング ポリシー
- 会議ポリシー
- アプリのセットアップ ポリシー
- 通話ポリシー
- ライブ イベント ポリシー

## <a name="policy-packages-included-in-teams"></a>Teams に含まれるポリシー パッケージ

Teams には現在、次のポリシー パッケージが含まれています。

| パッケージ名 | 説明 |
|---------|---------|
|教育 (高等教育の学生)    |高等教育の学生に適用されるポリシーとポリシー設定のセットを作成します。|
|教育 (小学生)   |小学生に適用されるポリシーとポリシー設定のセットを作成します。|
|教育 (中等学校の学生)    |セカンダリ 学生に適用されるポリシーとポリシー設定のセットを作成します。         |
|教育 (教師)    |教師に適用されるポリシーとポリシー設定のセットを作成します。      |
|教育 (リモート学習を使用した小学校の教師)    |小学校教師に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。      |
|教育 (リモート学習を使用した小学生)    |小学生に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。      |
|現場マネージャー |一連のポリシーを作成し、それらの設定を組織内の Frontline マネージャーに適用します。 |
|現場担当者 |一連のポリシーを作成し、それらの設定を組織内の現場担当者に適用します。 |
|医療施設の職員  |一連のポリシーとポリシー設定を作成して、登録済看護師、担当看護師、医師、およびソーシャル ワーカーに対して、チャット、通話、シフト管理、会議へのフル アクセスを提供します。 |
|医療情報提供者  |一連のポリシーとポリシー設定を作成して、IT 担当者、情報スタッフ、財務担当者、法令遵守責任者に対して、チャット、通話、会議へのフル アクセスを提供します。|
|医療患者室  |貴社の医療組織の患者室に適用される一連のポリシーとポリシー設定を作成します。 |
|公安責任者   |組織内の公衆安全責任者に適用されるポリシーとポリシー設定のセットを作成します。|
|中小規模のビジネス ユーザー (Business Voice) |ユーザー向けのビジネス音声エクスペリエンス用のアプリを含むアプリセットアップ ポリシーを作成します。|
|中小規模のビジネス ユーザー (Business Voice なし) |ビジネス音声機能を使用せずに、中小規模のビジネス Teams ユーザーに関連するアプリセットアップ ポリシーを作成します。

> [!NOTE]
> Teams の今後のリリースではさらにポリシー パッケージを追加する予定なので、最新の情報を確認してください。  

ポリシー パッケージにリンクされているポリシーを容易に識別できるように、個々のポリシーにはポリシー パッケージ名が付けられます。
たとえば、教育機関の教師に Education (Teacher) ポリシー パッケージを割り当てると、Education_Teacherという名前のポリシーがパッケージ内の各ポリシーに対して作成されます。

:::image type="content" source="media/teams-policy-packages-education.png" alt-text="Education (Teacher) ポリシー パッケージのスクリーンショット。" lightbox="media/teams-policy-packages-education.png":::

## <a name="custom-policy-packages"></a>カスタム ポリシー パッケージ

> [!NOTE]
> カスタム ポリシー パッケージ機能はプレビューで利用できます。 プレビュー後にこの機能を使用するには、各ユーザーに Teams Premium ライセンスが必要です。

カスタム ポリシー パッケージを使用すると、組織内で同様のロールを持つユーザーに対して独自のポリシー セットをバンドルできます。 必要なポリシーの種類とポリシーを追加して、独自のポリシー パッケージを作成します。

新しいカスタム ポリシー パッケージを作成するには:

1. Microsoft Teams 管理センターの左側のウィンドウで、[**ポリシー パッケージ**] を選択し、[**追加**] をクリックします。

    :::image type="content" source="media/policy-packages-add.png" alt-text="管理センターの [ポリシー パッケージ] ページの [追加] ボタンのスクリーンショット。" lightbox="media/policy-packages-add.png":::

2. パッケージの名前と説明を入力します。

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="新しいカスタム ポリシー パッケージを追加するスクリーンショット。" lightbox="media/policy-packages-add-custom.png":::

3. パッケージに含めるポリシーの種類とポリシー名を選択します。

4. **[保存]** を選択します。

## <a name="how-to-use-policy-packages"></a>ポリシー パッケージの使用方法

次に、組織内のポリシー パッケージを使用する方法について説明します。

![ポリシー パッケージの使用方法の概要。](media/manage-policy-packages-overview.png)

- **[表示](#view-the-settings-of-a-policy-in-a-policy-package)**: ポリシー パッケージ内のポリシーを表示します。 次に、パッケージを割り当てる前に、パッケージ内の各ポリシーの設定を表示します。 各設定を理解していることを確認します。 定義済みの値が組織に適しているかどうか、または組織のニーズに基づいて、より制限的または寛大な値に変更する必要があるかどうかを決定します。

    ポリシーが削除された場合でも、設定を表示することはできますが、設定を変更することはできません。 ポリシー パッケージを割り当てると、定義済みの設定で削除されたポリシーが再作成されます。

- **[カスタマイズ](#customize-policies-in-a-policy-package)**: 組織のニーズに合わせてポリシー パッケージ内のポリシーの設定をカスタマイズします。

- **[割り当て](#assign-a-policy-package)**: ポリシー パッケージをユーザーに割り当てます。  

> [!NOTE]
> パッケージを割り当てた後で、ポリシー パッケージ内のポリシーの設定を変更することもできます。 ポリシー設定の変更は、パッケージが割り当てられているユーザーに自動的に適用されます。

Microsoft Teams 管理センターでポリシー パッケージを表示、割り当て、カスタマイズする手順を次に示します。

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>ポリシー パッケージ内のポリシーの設定を表示する

1. Microsoft Teams 管理センターの左側のウィンドウで、[**ポリシー パッケージ**] を選択し、パッケージ名の左側をクリックしてポリシー パッケージを選択します。

2. 表示するポリシーを選択します。

### <a name="customize-policies-in-a-policy-package"></a>ポリシー パッケージ内のポリシーをカスタマイズする

ポリシーの設定は、[**ポリシー パッケージ**] ページから編集するか、Microsoft Teams 管理センターのポリシー ページに直接移動して編集できます。

1. Microsoft Teams 管理センターの左側のウィンドウで、次のいずれかの操作を行います。
    - [ **ポリシー パッケージ**] を選択し、パッケージ名の左側をクリックしてポリシー パッケージを選択します。
    - ポリシーの種類を選択します。  たとえば、[ **メッセージング ポリシー**] をクリックします。

2. 編集するポリシーを選択します。 ポリシー パッケージにリンクされているポリシーの名前は、ポリシー パッケージと同じです。

3. 必要な変更を行い、[ **保存**] をクリックします。

### <a name="assign-a-policy-package"></a>ポリシー パッケージを割り当てる

個々のユーザー、グループ、またはユーザーのバッチにポリシー パッケージを割り当てることができます。 ポリシー パッケージを割り当てる方法の詳細については、「 [ユーザーとグループにポリシー パッケージを割り当てる](assign-policy-packages.md)」を参照してください。

## <a name="related-topics"></a>関連項目

- [ポリシー パッケージを割り当てる](assign-policy-packages.md)
- [EDU 管理者向けの Teams ポリシー パッケージ](policy-packages-edu.md)
- [ヘルスケア向けの Teams ポリシー パッケージ](policy-packages-healthcare.md)
- [政府機関向けの Teams ポリシー パッケージ](policy-packages-gov.md)
