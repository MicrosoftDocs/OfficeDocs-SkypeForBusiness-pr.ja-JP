---
title: アプリケーションでポリシー パッケージを管理Microsoft Teams
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
description: Microsoft Teams でポリシー パッケージを使用および管理して、ユーザー グループのポリシーを管理する際の一貫性を簡素化、合理化、および提供する方法について説明します。
ms.openlocfilehash: 63900f301a8b3a48a8c17c6278808cd52e2445da
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2021
ms.locfileid: "52810185"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>アプリケーションでポリシー パッケージを管理Microsoft Teams

Microsoft Teams のポリシー パッケージは、組織内で類似の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。 組織全体のユーザー のグループに対するポリシーを管理する際に、一貫性を提供するために、ポリシー パッケージを構築しました。  

アプリケーションに含まれている[ポリシー パッケージをTeams](#policy-packages-included-in-teams)独自のカスタム ポリシー[パッケージを作成できます](#custom-policy-packages)。

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="管理センターの [ポリシー パッケージ] ページのスクリーンショット":::

ユーザーのニーズに合わせて、ポリシー パッケージ内のポリシーの設定をカスタマイズできます。 パッケージ内のポリシーの設定を変更すると、そのパッケージに割り当てられているすべてのユーザーが更新された設定を取得します。 ポリシー パッケージは、管理センターまたは PowerShell Microsoft Teams使用して管理します。

> [!NOTE]
> カスタム ポリシー パッケージの割り当てを受け取るには、各ユーザーに Advanced Communications アドオンが必要です。 詳細については、「Advanced [Communications add-on for Microsoft Teams」を参照してください](/microsoftteams/teams-add-on-licensing/advanced-communications)。

## <a name="what-is-a-policy-package"></a>ポリシー パッケージとは

ポリシー パッケージを使用するとTeams特定のユーザーセットに対して許可または制限する機能を制御できます。 Teams の各ポリシー パッケージは、ユーザー ロールを中心に設計され、そのロールに一般的なコラボレーションおよび通信アクティビティをサポートする定義済みのポリシーとポリシー設定が含まれています。

ポリシー パッケージは、次の種類のポリシー Teamsサポートしています。

- メッセージング ポリシー
- 会議ポリシー
- アプリセットアップ ポリシー
- 通話ポリシー
- ライブ イベント ポリシー

## <a name="policy-packages-included-in-teams"></a>Teams に含まれるポリシー パッケージ

Teamsには、現在、次のポリシー パッケージが含まれています。

| パッケージ名 | 説明 |
|---------|---------|
|教育 (高等教育学生)    |一連のポリシーとポリシー設定を作成します。この設定は、高学年の学生に適用されます。|
|Education (Primary school student)   |プライマリ 学生に適用されるポリシーとポリシー設定のセットを作成します。|
|教育 (中学生)    |セカンダリ 学生に適用される一連のポリシーとポリシー設定を作成します。         |
|教育 (教師)    |教師に適用されるポリシーとポリシー設定のセットを作成します。      |
|教育 (リモート学習を使用するプライマリ スクール教師)    |小学校教師に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。      |
|教育 (リモート学習を使用するプライマリ スチューデント)    |小学生に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。      |
|Frontline Manager |一連のポリシーを作成し、それらの設定を組織内の Frontline マネージャーに適用します。 |
|Frontline worker |一連のポリシーを作成し、組織内の Frontline worker にそれらの設定を適用します。 |
|医療施設の職員  |一連のポリシーとポリシー設定を作成して、登録済看護師、担当看護師、医師、およびソーシャル ワーカーに対して、チャット、通話、シフト管理、会議へのフル アクセスを提供します。 |
|医療情報提供者  |一連のポリシーとポリシー設定を作成して、IT 担当者、情報スタッフ、財務担当者、法令遵守責任者に対して、チャット、通話、会議へのフル アクセスを提供します。|
|医療患者室  |貴社の医療組織の患者室に適用される一連のポリシーとポリシー設定を作成します。|
|中小企業ユーザー (Business Voice) |ビジネス音声エクスペリエンス用のアプリを含むアプリセットアップ ポリシーを作成します。|
|中小企業ユーザー (Business Voice なし) |ユーザー (非 Business Voice エクスペリエンス) に関連するTeamsセットアップ ポリシーを作成します。
|公安責任者   |組織内の公安責任者に適用される一連のポリシーとポリシー設定を作成します。|

> [!NOTE]
> Teams の今後のリリースでポリシー パッケージを追加する予定なので、最新の情報を確認してください。  

ポリシー パッケージにリンクされているポリシーを容易に識別できるように、個々のポリシーにはポリシー パッケージ名が付けられます。
たとえば、学校の教師に Education (Teacher) ポリシー パッケージを割り当てると、パッケージ内のポリシーごとに Education_Teacher という名前のポリシーが作成されます。

![Education (Teacher) ポリシー パッケージのスクリーンショット](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>カスタム ポリシー パッケージ

**カスタム ポリシー パッケージは、アプリケーションではまだ使用Government Community Cloud (GCC)**

カスタム ポリシー パッケージを使用すると、組織内で同様のロールを持つユーザーに対して独自のポリシー セットをバンドルできます。 必要なポリシーの種類とポリシーを追加して、独自のポリシー パッケージを作成します。

新しいカスタム ポリシー パッケージを作成するには:

1. 管理センターの左側のナビゲーションMicrosoft Teams[ポリシー パッケージ] を選択し、[追加] を **クリックします**。

    :::image type="content" source="media/policy-packages-add.png" alt-text="管理センターの [ポリシー パッケージ] ページの [追加] ボタンのスクリーンショット":::

2. パッケージの名前と説明を入力します。

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="新しいカスタム ポリシー パッケージの追加のスクリーンショット":::

3. パッケージに含めるポリシーの種類とポリシー名を選択します。

4. **[保存]** をクリックします。

## <a name="how-to-use-policy-packages"></a>ポリシー パッケージの使い方

次に、組織でポリシー パッケージを使用する方法の概要を示します。

![ポリシー パッケージの使用方法の概要](media/manage-policy-packages-overview.png)

- **[表示](#view-the-settings-of-a-policy-in-a-policy-package)**: ポリシー パッケージ内のポリシーを表示します。 次に、パッケージを割り当てる前に、パッケージ内の各ポリシーの設定を表示します。 各設定を理解してください。 定義済みの値が組織に適しているかどうか、または組織のニーズに基づいて、より制限の厳しい値を変更する必要があるかどうかを決定します。

    ポリシーが削除された場合でも、設定を表示できますが、設定を変更する必要があります。 ポリシー パッケージを割り当てると、定義済みの設定で削除されたポリシーが再作成されます。

- **[カスタマイズ](#customize-policies-in-a-policy-package)**: 組織のニーズに合わせてポリシー パッケージ内のポリシーの設定をカスタマイズします。

- **[割り](#assign-a-policy-package)** 当て: ポリシー パッケージをユーザーに割り当てる。  

> [!NOTE]
> パッケージを割り当て後に、ポリシー パッケージ内のポリシーの設定を変更することもできます。 ポリシー設定の変更は、パッケージが割り当てられているユーザーに自動的に適用されます。

管理センターでポリシー パッケージを表示、割り当て、カスタマイズするMicrosoft Teamsします。

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>ポリシー パッケージ内のポリシーの設定を表示する

1. Microsoft Teams 管理センターの左側のナビゲーションで、[ポリシー パッケージ] を選択し、パッケージ名の左側をクリックしてポリシー パッケージを選択します。

2. 表示するポリシーをクリックします。

### <a name="customize-policies-in-a-policy-package"></a>ポリシー パッケージ内のポリシーをカスタマイズする

ポリシーの設定は、[ポリシー パッケージ]ページで編集するか、管理センターのポリシー ページに直接移動Microsoft Teamsできます。

1. 管理センターの左側のMicrosoft Teams、次のいずれかの操作を行います。
    - [ **ポリシー パッケージ]** をクリックし、パッケージ名の左側をクリックしてポリシー パッケージを選択します。
    - ポリシーの種類をクリックします。  たとえば、[メッセージング ポリシー **] をクリックします**。

2. 編集するポリシーを選択します。 ポリシー パッケージにリンクされているポリシーは、ポリシー パッケージと同じ名前です。

3. 必要な変更を行い、[保存] を **クリックします**。

### <a name="assign-a-policy-package"></a>ポリシー パッケージを割り当てる

ポリシー パッケージは、個々のユーザー、グループ、またはユーザーのバッチに割り当てできます。 ポリシー パッケージを割り当てる方法の詳細については、「ユーザーとグループにポリシー パッケージを割り当 [てる」を参照してください](assign-policy-packages.md)。

## <a name="related-topics"></a>関連項目

- [ポリシー パッケージの割り当て](assign-policy-packages.md)
- [Teams EDU 管理者向けポリシー パッケージの作成](policy-packages-edu.md)
- [ヘルスケア向けの Teams ポリシー パッケージ](policy-packages-healthcare.md)
- [Teamsのポリシー パッケージを作成する](policy-packages-gov.md)
