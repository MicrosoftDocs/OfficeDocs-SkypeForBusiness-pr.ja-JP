---
title: Microsoft Teams でポリシー パッケージを管理する
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
description: Microsoft Teams でポリシー パッケージを使用および管理して、ユーザー グループのポリシーを管理する際の一貫性を簡素化、合理化、および提供する方法について説明します。
ms.openlocfilehash: 10c7eaad9342d1c005c6290ebc957c3580db3962
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270852"
---
# <a name="manage-policy-packages-for-microsoft-teams"></a>Microsoft Teams のポリシー パッケージを管理する

Microsoft Teams のポリシー パッケージは、組織内で類似の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。 組織全体のユーザー グループのポリシーを管理する際に一貫性を提供するために、ポリシー パッケージを構築しました。  

[Teams に含まれるポリシー パッケージを](#policy-packages-included-in-teams)使用することも、[独自のカスタム ポリシー パッケージを作成](#custom-policy-packages)することもできます。

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="管理センターの [ポリシー パッケージ] ページのスクリーンショット。" lightbox="media/policy-packages-admin-center.png":::

ポリシー パッケージ内のポリシーの設定は、ユーザーのニーズに合わせてカスタマイズできます。 パッケージ内のポリシーの設定を変更すると、そのパッケージに割り当てられているすべてのユーザーが更新された設定を取得します。 ポリシー パッケージは、Microsoft Teams 管理センターまたは PowerShell を使用して管理します。

> [!NOTE]
> この機能は、すべての Microsoft Teams のお客様向けのパブリック プレビューで一時的に利用できます。 プレビュー後にこの機能を取得するには、各ユーザーに Advanced Communications アドオン ライセンスが必要です。 詳細については、「[Microsoft Teams 用 Advanced Communications アドオン](/microsoftteams/teams-add-on-licensing/advanced-communications)」を参照してください。

## <a name="what-is-a-policy-package"></a>ポリシー パッケージとは

ポリシー パッケージを使用すると、組織全体の特定のユーザー セットを許可または制限する Teams 機能を制御できます。 Teams の各ポリシー パッケージは、ユーザー ロールを中心に設計されており、そのロールに一般的なコラボレーションと通信アクティビティをサポートする定義済みのポリシーとポリシー設定が含まれています。

ポリシー パッケージでは、次の Teams ポリシーの種類がサポートされます。

- メッセージング ポリシー
- 会議ポリシー
- アプリのセットアップ ポリシー
- 通話ポリシー
- ライブ イベント ポリシー

## <a name="policy-packages-included-in-teams"></a>Teams に含まれるポリシー パッケージ

Teams には現在、次のポリシー パッケージが含まれています。

| パッケージ名 | 説明 |
|---------|---------|
|教育機関 (高等教育学生)    |教育機関の学生に適用される一連のポリシーとポリシー設定を作成します。|
|教育機関 (初等生)   |初等生に適用される一連のポリシーとポリシー設定を作成します。|
|教育機関 (中等教育学生)    |中等生に適用される一連のポリシーとポリシー設定を作成します。         |
|教育機関 (教師)    |教師に適用される一連のポリシーとポリシー設定を作成します。      |
|教育 (リモート ラーニングを使用した初等教育)    |小学校教師に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。      |
|教育 (リモート ラーニングを使用した初等教育)    |小学生に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。      |
|現場マネージャー |一連のポリシーを作成し、その設定を組織内のフロントライン マネージャーに適用します。 |
|現場担当者 |一連のポリシーを作成し、その設定を組織内のフロントライン ワーカーに適用します。 |
|医療施設の職員  |一連のポリシーとポリシー設定を作成して、登録済看護師、担当看護師、医師、およびソーシャル ワーカーに対して、チャット、通話、シフト管理、会議へのフル アクセスを提供します。 |
|医療情報提供者  |一連のポリシーとポリシー設定を作成して、IT 担当者、情報スタッフ、財務担当者、法令遵守責任者に対して、チャット、通話、会議へのフル アクセスを提供します。|
|医療患者室  |貴社の医療組織の患者室に適用される一連のポリシーとポリシー設定を作成します。 |
|公安担当者   |組織内の公衆安全責任者に適用される一連のポリシーとポリシー設定を作成します。|
|中小規模ビジネス ユーザー (Business Voice) |ユーザーのビジネス音声エクスペリエンス用のアプリを含むアプリセットアップ ポリシーを作成します。|
|中小規模のビジネス ユーザー (Business Voice を使用しない) |ビジネス音声機能を使用せずに、中小規模のビジネス Teams ユーザーに関連するアプリセットアップ ポリシーを作成します。

> [!NOTE]
> Teams の今後のリリースでポリシー パッケージを追加する予定なので、最新の情報を確認してください。  

ポリシー パッケージにリンクされているポリシーを容易に識別できるように、個々のポリシーにはポリシー パッケージ名が付けられます。
たとえば、教育機関 (教師) ポリシー パッケージを学校の教師に割り当てると、パッケージ内のポリシーごとにEducation_Teacherという名前のポリシーが作成されます。

:::image type="content" source="media/teams-policy-packages-education.png" alt-text="Education (Teacher) ポリシー パッケージのスクリーンショット。" lightbox="media/teams-policy-packages-education.png":::

## <a name="custom-policy-packages"></a>カスタム ポリシー パッケージ

カスタム ポリシー パッケージを使用すると、組織内で同様のロールを持つユーザーに対して独自のポリシー セットをバンドルできます。 必要なポリシーの種類とポリシーを追加して、独自のポリシー パッケージを作成します。

新しいカスタム ポリシー パッケージを作成するには:

1. Microsoft Teams 管理センターの左側のウィンドウで、 **ポリシー パッケージ** を選択し、[ **追加**] をクリックします。

    :::image type="content" source="media/policy-packages-add.png" alt-text="管理センターの [ポリシー パッケージ] ページの [追加] ボタンのスクリーンショット。" lightbox="media/policy-packages-add.png":::

2. パッケージの名前と説明を入力します。

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="新しいカスタム ポリシー パッケージを追加するスクリーンショット。" lightbox="media/policy-packages-add-custom.png":::

3. パッケージに含めるポリシーの種類とポリシー名を選択します。

4. **[保存]** を選択します。

## <a name="how-to-use-policy-packages"></a>ポリシー パッケージを使用する方法

組織でポリシー パッケージを使用する方法の概要を次に示します。

![ポリシー パッケージを使用する方法の概要。](media/manage-policy-packages-overview.png)

- **[表示](#view-the-settings-of-a-policy-in-a-policy-package)**: ポリシー パッケージ内のポリシーを表示します。 次に、パッケージを割り当てる前に、パッケージ内の各ポリシーの設定を表示します。 各設定を理解していることを確認します。 定義済みの値が組織に適しているかどうか、または組織のニーズに基づいて、より制限の厳しい値または緩やかなものに変更する必要があるかどうかを決定します。

    ポリシーが削除された場合でも、設定は表示できますが、設定を変更することはできません。 削除されたポリシーは、ポリシー パッケージを割り当てるときに定義済みの設定で再作成されます。

- **[カスタマイズ](#customize-policies-in-a-policy-package)**: 組織のニーズに合わせてポリシー パッケージ内のポリシーの設定をカスタマイズします。

- **[割り当て](#assign-a-policy-package)**: ポリシー パッケージをユーザーに割り当てます。  

> [!NOTE]
> パッケージを割り当てた後で、ポリシー パッケージ内のポリシーの設定を変更することもできます。 ポリシー設定の変更は、パッケージが割り当てられているユーザーに自動的に適用されます。

Microsoft Teams 管理センターでポリシー パッケージを表示、割り当て、カスタマイズする手順を次に示します。

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>ポリシー パッケージ内のポリシーの設定を表示する

1. Microsoft Teams 管理センターの左側のウィンドウで、 **ポリシー パッケージ** を選択し、パッケージ名の左側をクリックしてポリシー パッケージを選択します。

2. 表示するポリシーを選択します。

### <a name="customize-policies-in-a-policy-package"></a>ポリシー パッケージ内のポリシーをカスタマイズする

ポリシーの設定は、[ **ポリシー パッケージ** ] ページまたは Microsoft Teams 管理センターのポリシー ページに直接移動して編集できます。

1. Microsoft Teams 管理センターの左側のウィンドウで、次のいずれかの操作を行います。
    - **[ポリシー パッケージ**] を選択し、パッケージ名の左側をクリックしてポリシー パッケージを選択します。
    - ポリシーの種類を選択します。  たとえば、[ **メッセージング ポリシー**] をクリックします。

2. 編集するポリシーを選択します。 ポリシー パッケージにリンクされているポリシーの名前は、ポリシー パッケージと同じです。

3. 必要な変更を加え、[保存] をクリック **します**。

### <a name="assign-a-policy-package"></a>ポリシー パッケージを割り当てる

ポリシー パッケージは、個々のユーザー、グループ、またはユーザーのバッチに割り当てることができます。 ポリシー パッケージを割り当てる方法の詳細については、「 [ユーザーとグループにポリシー パッケージを割り当てる」を](assign-policy-packages.md)参照してください。

## <a name="related-topics"></a>関連項目

- [ポリシー パッケージを割り当てる](assign-policy-packages.md)
- [EDU 管理者向けの Teams ポリシー パッケージ](policy-packages-edu.md)
- [ヘルスケア向けの Teams ポリシー パッケージ](policy-packages-healthcare.md)
- [政府機関向けの Teams ポリシー パッケージ](policy-packages-gov.md)
