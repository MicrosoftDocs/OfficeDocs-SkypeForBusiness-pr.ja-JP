---
title: ポリシー パッケージを管理Microsoft Teams
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
description: ユーザー グループのポリシーを管理する際に、Microsoft Teams でポリシー パッケージを使用および管理して、一貫性を簡単に、合理化し、一貫性を提供する方法について説明します。
ms.openlocfilehash: 2fd892bc440996c7c1f000402122ad268a402ebb6bf382672813efa296de819f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341789"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>ポリシー パッケージを管理Microsoft Teams

[ポリシー パッケージ] Microsoft Teamsは、組織で同様の役割を持つユーザーに割り当て可能な定義済みのポリシーとポリシー設定のコレクションです。 組織全体のユーザーグループのポリシーを管理する際に一貫性を提供するために、ポリシー パッケージを構築しました。  

カスタム ポリシー パッケージに[含まれているポリシー パッケージをTeams](#policy-packages-included-in-teams)独自[のカスタム ポリシー パッケージを作成することもできます](#custom-policy-packages)。

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="管理センターの [ポリシー パッケージ] ページのスクリーンショット":::

ポリシー パッケージ内のポリシーの設定は、ユーザーのニーズに合わせてカスタマイズできます。 パッケージ内のポリシーの設定を変更すると、そのパッケージに割り当てられているすべてのユーザーが更新された設定を取得します。 ポリシー パッケージは、管理センターまたは PowerShell Microsoft Teams使用して管理します。

> [!NOTE]
> ユーザーごとに、カスタム ポリシー パッケージの割り当てを受け取る場合は、Advanced Communications アドオンが必要です。 詳細については、「Advanced [Communications add-on for Microsoft Teams」 を参照してください](/microsoftteams/teams-add-on-licensing/advanced-communications)。

## <a name="what-is-a-policy-package"></a>ポリシー パッケージとは

ポリシー パッケージを使用すると、組織Teams特定のユーザー セットを許可または制限する機能を制御できます。 Teams の各ポリシー パッケージは、ユーザー ロールを中心に設計され、その役割に一般的なコラボレーションおよび通信アクティビティをサポートする定義済みのポリシーとポリシー設定が含まれています。

ポリシー パッケージは、次の種類のポリシー Teamsサポートします。

- メッセージング ポリシー
- 会議ポリシー
- アプリのセットアップ ポリシー
- 通話ポリシー
- ライブ イベント ポリシー

## <a name="policy-packages-included-in-teams"></a>ポリシー パッケージは、Teams

Teamsには、次のポリシー パッケージが含まれています。

| パッケージ名 | 説明 |
|---------|---------|
|教育 (高等教育学生)    |高等教育学生に適用される一連のポリシーとポリシー設定を作成します。|
|教育 (小学生)   |プライマリ 学生に適用されるポリシーとポリシー設定のセットを作成します。|
|教育 (中学生)    |中学生に適用される一連のポリシーとポリシー設定を作成します。         |
|教育 (教師)    |教師に適用されるポリシーとポリシー設定のセットを作成します。      |
|教育 (リモートラーニングを使用する小学校の教師)    |リモート学習を使用する場合に学生の安全と共同作業を最大化するために、初等教師に適用される一連のポリシーを作成します。      |
|教育 (リモートラーニングを使用する小学校の生徒)    |一連のポリシーを作成し、初等学生に適用して、リモートラーニングを使用する際の学生の安全性とコラボレーションを最大化します。      |
|フロントライン マネージャー |一連のポリシーを作成し、それらの設定を組織内のフロントライン 管理者に適用します。 |
|フロントライン ワーカー |一連のポリシーを作成し、それらの設定を組織内のフロントライン ワーカーに適用します。 |
|医療従事者  |登録された看護師、看護師、医師、ソーシャル ワーカーなどの臨床労働者にチャット、通話、シフト管理、会議へのフル アクセスを提供する一連のポリシーとポリシー設定を作成します。 |
|医療情報ワーカー  |IT 担当者、情報担当者、財務担当者、コンプライアンス担当者などの情報ワーカーにチャット、通話、会議へのフル アクセスを提供する一連のポリシーとポリシー設定を作成します。|
|医療患者の部屋  |医療組織の患者室に適用される一連のポリシーとポリシー設定を作成します。|
|中小規模のビジネス ユーザー (Business Voice) |ビジネス音声エクスペリエンス用のアプリを含むアプリセットアップ ポリシーを作成します。|
|中小規模のビジネス ユーザー (Business Voice なし) |小規模および中規模のビジネス ユーザーに関連するアプリ セットアップ Teamsを作成します (ビジネス音声以外のエクスペリエンス)。
|公安責任者   |組織内の公衆安全担当者に適用される一連のポリシーとポリシー設定を作成します。|

> [!NOTE]
> 今後のリリースではポリシー パッケージを追加する予定Teams、最新の情報を確認してください。  

個々のポリシーにはポリシー パッケージの名前が付き、ポリシー パッケージにリンクされているポリシーを簡単に識別できます。
たとえば、学校の教師に Education (Teacher) ポリシー パッケージを割り当てると、パッケージ内のポリシーごとに Education_Teacher という名前のポリシーが作成されます。

![Education (Teacher) ポリシー パッケージのスクリーンショット](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>カスタム ポリシー パッケージ

**カスタム ポリシー パッケージは、ユーザー設定でまだ使用Government Community Cloud (GCC)**

カスタム ポリシー パッケージを使用すると、組織内で同様の役割を持つユーザーの独自のポリシー セットをバンドルできます。 必要なポリシーの種類とポリシーを追加して、独自のポリシー パッケージを作成します。

新しいカスタム ポリシー パッケージを作成するには、次の方法を実行します。

1. 管理センターの左側のナビゲーションで、[Microsoft Teams パッケージ] を選択し、[追加] を **クリックします**。

    :::image type="content" source="media/policy-packages-add.png" alt-text="管理センターの [ポリシー パッケージ] ページの [追加] ボタンのスクリーンショット":::

2. パッケージの名前と説明を入力します。

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="新しいカスタム ポリシー パッケージの追加のスクリーンショット":::

3. パッケージに含めるポリシーの種類とポリシー名を選択します。

4. [**保存**] をクリックします。

## <a name="how-to-use-policy-packages"></a>ポリシー パッケージの使い方

組織でポリシー パッケージを使用する方法の概要を次に示します。

![ポリシー パッケージの使用方法の概要](media/manage-policy-packages-overview.png)

- **[表示](#view-the-settings-of-a-policy-in-a-policy-package)**: ポリシー パッケージ内のポリシーを表示します。 次に、パッケージを割り当てる前に、パッケージ内の各ポリシーの設定を表示します。 各設定を理解してください。 定義済みの値が組織に適しているかどうか、または組織のニーズに基づいて、それらをより制限的または寛大に変更する必要があるかどうかを決定します。

    ポリシーが削除された場合でも、設定を表示できますが、設定は変更されません。 ポリシー パッケージを割り当てると、定義済みの設定で削除されたポリシーが再作成されます。

- **[カスタマイズ](#customize-policies-in-a-policy-package)**: 組織のニーズに合わせてポリシー パッケージ内のポリシーの設定をカスタマイズします。

- **[割り](#assign-a-policy-package)** 当て: ポリシー パッケージをユーザーに割り当てる。  

> [!NOTE]
> また、パッケージを割り当て後にポリシー パッケージ内のポリシーの設定を変更することもできます。 ポリシー設定に加えた変更は、パッケージが割り当てられているユーザーに自動的に適用されます。

管理センターでポリシー パッケージを表示、割り当て、カスタマイズするMicrosoft Teams次に示します。

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>ポリシー パッケージ内のポリシーの設定を表示する

1. Microsoft Teams管理センターの左側のナビゲーションで、[ポリシー パッケージ]を選択し、パッケージ名の左側をクリックしてポリシー パッケージを選択します。

2. 表示するポリシーをクリックします。

### <a name="customize-policies-in-a-policy-package"></a>ポリシー パッケージ内のポリシーをカスタマイズする

ポリシーの設定は、[ポリシー パッケージ]ページから、または管理センターのポリシー ページに直接移動Microsoft Teamsできます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、次のいずれかを実行します。
    - [ **ポリシー パッケージ]** をクリックし、パッケージ名の左側をクリックしてポリシー パッケージを選択します。
    - ポリシーの種類をクリックします。  たとえば、[メッセージング ポリシー **] をクリックします**。

2. 編集するポリシーを選択します。ポリシー パッケージにリンクされているポリシー名は、ポリシー パッケージと同じです。

3. 必要な変更を行い、[保存] を **クリックします**。

### <a name="assign-a-policy-package"></a>ポリシー パッケージの割り当て

ポリシー パッケージは、個々のユーザー、グループ、またはユーザーのバッチに割り当てできます。 ポリシー パッケージを割り当てる方法の詳細については、「ポリシー パッケージをユーザーとグループに割り当 [てる」を参照してください](assign-policy-packages.md)。

## <a name="related-topics"></a>関連項目

- [ポリシー パッケージを割り当てる](assign-policy-packages.md)
- [Teams EDU 管理者向けポリシー パッケージ](policy-packages-edu.md)
- [Teamsのポリシー パッケージ](policy-packages-healthcare.md)
- [Teamsポリシー パッケージ](policy-packages-gov.md)
