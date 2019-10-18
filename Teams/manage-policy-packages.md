---
title: Microsoft Teams でポリシーパッケージを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sekrantz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams でポリシーパッケージを使用および管理する方法について説明します。
ms.openlocfilehash: 1caa1606f330b92507342140efbfc144def8c547
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571947"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Microsoft Teams でポリシーパッケージを管理する

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Microsoft Teams のポリシーパッケージは、組織内で同様の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。 組織全体のユーザーグループのポリシーを管理する際の一貫性を高めるために、ポリシーパッケージを作成しました。  

ポリシーパッケージをユーザーに割り当てると、パッケージ内のポリシーが作成され、組織のニーズに合わせてパッケージ内のポリシーの設定をカスタマイズすることができます。

## <a name="what-is-a-policy-package"></a>ポリシーパッケージとは

ポリシーパッケージを使用すると、組織内の特定のユーザーのセットに対して許可または制限するチームの機能を制御できます。 Teams の各ポリシーパッケージは、ユーザーロールをベースに設計されており、その役割で一般的なコラボレーションと通信のアクティビティをサポートする定義済みのポリシーおよびポリシー設定が含まれています。

チームには現在、次のポリシーパッケージが含まれています。

|**パッケージ名**  |**説明** |
|---------|---------|
|Education_Teacher パッケージ     |教師に適用される一連のポリシーとポリシー設定を作成します。      |
|Education_PrimaryStudent パッケージ    |主要な学生に適用される一連のポリシーとポリシー設定を作成します。|
|Education_SecondaryStudent パッケージ    |第2の学生に適用される一連のポリシーとポリシー設定を作成します。         |
|Education_HigherEducationStudent パッケージ    |高等教育機関向けの学生に適用される一連のポリシーとポリシー設定を作成します。|

> [!NOTE]
> 今後のチームのリリースでポリシーパッケージを追加しますので、最新の情報を確認してください。  

個々のポリシーには、ポリシーパッケージの名前が割り当てられているため、ポリシーパッケージにリンクされているポリシーを簡単に識別することができます。
たとえば、学校の教師に Education_Teacher ポリシーパッケージを割り当てると、Education_Teacher という名前のポリシーがパッケージ内の各ポリシーに対して作成されます。

![Education_Teacher ポリシーパッケージのスクリーンショット](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a>ポリシーパッケージの使用方法

組織でポリシーパッケージを使用する方法については、次の表をご覧ください。

![ポリシーパッケージの使用方法の概要](media/manage-policy-packages-overview.png)

- **[表示](#view-the-settings-of-a-policy-in-a-policy-package)**: パッケージを割り当てる前に、ポリシーパッケージ内の各ポリシーの設定を表示します。 各設定を理解していることを確認して、組織にとって事前に定義された値が適切かどうかを確認します。また、組織のニーズに基づいて、定義済みの値を変更する必要があるかどうかを判断する必要があります。

    ポリシーが削除された場合でも、設定は表示できますが、設定を変更することはできません。 ポリシーパッケージを割り当てるときに、削除されたポリシーが定義済みの設定で再作成されます。

- **[割り当て](#assign-a-policy-package)**: ポリシーパッケージをユーザーに割り当てます。 ポリシーパッケージのポリシーは、パッケージを割り当てるまで作成されないことに注意してください。その後、パッケージ内の個々のポリシーの設定を変更することができます。  

- **[カスタマイズ](#customize-policies-in-a-policy-package)**: 組織のニーズに合わせてポリシーパッケージのポリシーの設定をカスタマイズします。 ポリシー設定に加えた変更は、パッケージを割り当てられたユーザーに自動的に適用されます。

Microsoft Teams 管理センターでポリシーパッケージを表示、割り当て、カスタマイズする方法の手順を次に示します。

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>ポリシーパッケージ内のポリシーの設定を表示する

1. Microsoft Teams 管理センターの左のナビゲーションで、[**ポリシーパッケージ**] をクリックし、パッケージ名の左側をクリックしてポリシーパッケージを選択します。
2. 表示するポリシーをクリックします。

### <a name="assign-a-policy-package"></a>ポリシーパッケージを割り当てる

#### <a name="assign-a-policy-package-to-one-user"></a>1人のユーザーにポリシーパッケージを割り当てる

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。
2. ユーザーのページで、[**ポリシー**] をクリックし、[**ポリシーパッケージ**] の横にある [**編集**] をクリックします。
3. [**ポリシーパッケージの割り当て**] ウィンドウで、割り当てるパッケージを選択し、[**保存**] をクリックします。

#### <a name="assign-a-policy-package-to-multiple-users"></a>ポリシーパッケージを複数のユーザーに割り当てる

1. Microsoft Teams 管理センターの左のナビゲーションで、[**ポリシーパッケージ**] に移動し、パッケージ名の左側をクリックして割り当てるポリシーパッケージを選択します。
2. [**ユーザーの管理**] をクリックします。
3. [**ユーザーの管理**] ウィンドウで、[表示名] または [ユーザー名] でユーザーを検索し、名前を選択して [**追加**] をクリックします。 追加するユーザーごとに、この手順を繰り返します。
4. ユーザーの追加が完了したら、[**保存**] をクリックします。

### <a name="customize-policies-in-a-policy-package"></a>ポリシーパッケージのポリシーをカスタマイズする

ポリシーの設定を編集するには、[**ポリシーパッケージ**] ページを使用するか、Microsoft Teams 管理センターの [ポリシー] ページに直接移動します。

1. Microsoft Teams 管理センターの左側のナビゲーションで、次のいずれかの操作を行います。
    - [**ポリシーパッケージ**] をクリックし、パッケージ名の左側をクリックしてポリシーパッケージを選択します。
    - [ポリシーの種類] をクリックします。  たとえば、[**メッセージングポリシー**] をクリックします。
2. 編集するポリシーをクリックします。 ポリシーパッケージにリンクされているポリシーは、ポリシーパッケージと同じ名前になっています。
3. 必要な変更を加えて、[**保存**] をクリックします。

## <a name="troubleshooting"></a>トラブルシューティング

**ポリシーパッケージを割り当てるときにエラーが表示される**

この問題は、パッケージ内の1つ以上のポリシーが正常に作成または適用されなかった場合に発生することがあります。 ポリシーパッケージをユーザーに割り当て直します。 通常、操作を再試行すると、この問題は修正されます。
