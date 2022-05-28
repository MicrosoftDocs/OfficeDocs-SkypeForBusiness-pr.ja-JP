---
title: Teams Rooms用に ServiceNow を構成する
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Teams Rooms プレミアム ポータルでの ServiceNow の構成の詳細
f1keywords: ''
ms.openlocfilehash: c11a4e3cf4f128c8043ad2451f7d0a7a2ffe1c2e
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761499"
---
# <a name="configure-servicenow-for-teams-rooms"></a>Teams Rooms用に ServiceNow を構成する

この記事では、Teams Rooms プレミアム ポータルで ServiceNow 環境を構成するための前提条件と手順について説明します。

## <a name="before-you-begin"></a>はじめに

### <a name="teams-rooms-prerequisites"></a>Teams Rooms前提条件

- サービス管理者ロールが割り当てられている必要があります。 詳細については、「[Microsoft Teams Rooms マネージド サービスを使用したロールベースのアクセス制御](microsoft-teams-rooms-premium-rbac.md)」を参照してください。

### <a name="servicenow-prerequisites"></a>ServiceNow の前提条件

- Basic Authorization サインイン、または [OAuth](https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/security/concept/c_OAuthApplications.html) サインイン。 詳細については、「ServiceNow での [資格情報の作成」を](https://developer.servicenow.com/dev.do#!/learn/learning-plans/rome/servicenow_application_developer/app_store_learnv2_rest_rome_creating_credentials) 参照してください。
- ServiceNow インスタンスとそのインスタンスのホスト名と API URI
- incident_manager 以上のロール
- Table APIをサポートする ServiceNow のソフトウェア バージョン

## <a name="configure-your-environment"></a>環境を構成する

環境の構成方法は高度にカスタマイズ可能であり、組織のニーズに依存します。 次の手順では、ServiceNow の既存の構成を Teams Rooms プレミアム ポータルにコピーする方法について説明します。

1. コピーする ServiceNow インスタンスを開きます。 Teams Rooms プレミアム ポータルで構成フォームを完了すると、これを参照する必要があります。
2. 新しいブラウザー タブで、[Teams Rooms プレミアム ポータル](https://portal.rooms.microsoft.com/)に移動し **、設定** に移動します。 次に、左側のナビゲーション メニューで **[ServiceNow** ] を選択して、構成フォームを開きます。
3. サインインする認証方法を選択し、ServiceNow インスタンス ホストと API URI を入力します。
4. [フィールド マッピング] セクションの [ServiceNow フィールド] 列に必要なすべての項目は、事前に入力する必要があります。 次の表には、各 ServiceNow フィールドとそれに対応するMicrosoft Teams Rooms フィールドが含まれています。 [フィールド マッピング] セクションの各行のアクションを完了します。 各 ServiceNow フィールドの定義については、「 [ServiceNow フィールド定義」を](#servicenow-field-definitions)参照してください。

| ServiceNow フィールド | Microsoft Teams Rooms フィールド | アクション |
| --- | --- | --- |
| short_description | インシデントの説明 | アクションは必要ありません。 Teams Rooms フィールドは自動入力されます。 |
| 説明 | 最初のメッセージ | アクションは必要ありません。 Teams Rooms フィールドは自動入力されます。 |
| assignment_group | 会議室グループ | ServiceNow インスタンスのassignment_group値をコピーし、構成フォームの ServiceNow 値フィールドに貼り付けます。 複数のassignment_groupがある場合は、追加のカスタム値ごとに **[ルーム グループの追加** ] を選択します。 |
| 重大 度 | リング | 重大度は ServiceNow のカスタム値です。 これは、ServiceNow インスタンスの 2 番目の列の 4 番目の項目です。 値をコピーし、構成フォームの ServiceNow 値フィールドに貼り付けます。 複数の重大度値がある場合は、追加のカスタム値ごとに **[リングの追加** ] を選択します。 |
| コメント (省略可能) | カスタム値* | 構成フォームにコメント フィールドを追加するには、フィールド マッピング セクションの上部にある **[追加** ] を選択します。 ServiceNow インスタンスのコメント値をコピーし、構成フォームの ServiceNow フィールドに貼り付けます。 ドロップダウン メニューから Microsoft Teams Room フィールドを割り当て、ServiceNow 値をコピーして貼り付けます。 |
| 状態 (解決済み) | カスタム値* | ServiceNow インスタンスから解決状態をコピーし、構成フォームの ServiceNow 値フィールドに貼り付けます。 |
| close_code | カスタム値* | ServiceNow インスタンスの [ **解決情報** ] タブで、閉じたコードをコピーし、構成フォームの ServiceNow 値フィールドに貼り付けます。 |

*ドロップダウン メニューからカスタム値を選択する

>[!NOTE]
>カスタム値が見つからない場合は、ServiceNow 管理者にお問い合わせください。

[インシデントの解決] セクションに必要なフィールドを追加するには、[ **追加]** を選択します。

## <a name="test-and-enable"></a>テストと有効化

構成フォームに入力したら、ページの下部にある **[テスト** ] を選択します。 構成を送信するには、テストが必要です。

テストが正常に完了したら、[ **送信]** を選択して変更を保存します。 組織で ServiceNow を有効にする準備ができたら、[ **ServiceNow を有効にしますか?** ] トグルを **[オン]** に切り替えます。

## <a name="servicenow-field-definitions"></a>ServiceNow フィールド定義

- **short_description**: ServiceNow の短い説明フィールドは、インシデントの概要を示す短い 160 文字の英数字の値です。 短い説明は、Teams Rooms プレミアム ポータルのインシデントの説明と同じです。

- **description**: ServiceNow の説明フィールドは、ServiceNow インシデントの会話履歴の最初の値です。 説明は、Teams Rooms プレミアム ポータルの最初のメッセージと同じです。

- **assignment_group**: ServiceNow の割り当てグループ フィールドは、インシデントを整理するために使用されます。 割り当てグループは、Teams Rooms プレミアム ポータルの会議室グループと同じです。 既定では、1 つのルーム グループがあり、さらに追加できます。 グループの数とインシデントをグループ化する方法を決定します。 たとえば、場所別にインシデントを整理することもできます。

- **重大度**: ServiceNow の重大度フィールドは、優先度別にインシデントを整理するために使用されます。 優先度を指定する値はカスタマイズ可能です。 重大度は、Teams Rooms プレミアム ポータルの [リング] フィールドと同じです。 Teams Rooms プレミアム ポータルでリングをカスタマイズするには、左側のナビゲーション メニューの **[更新プログラム**] に移動します。 次に、[ **リング** ] タブに移動し、[ **リングの追加**] を選択します。

- **コメント**: コメントは ServiceNow の省略可能なフィールドであり、Teams Rooms プレミアム ポータル構成に ServiceNow インスタンスのカスタム必須フィールドを含めるために使用されます。 コメントに相当するのは、Teams Rooms プレミアム ポータルのカスタム値です。

- **状態 (解決済み)**: ServiceNow の状態 (解決済み) フィールドは、インシデントの解決方法を指定するために使用され、インシデントを閉じる必要があります。 状態 (解決済み) 値はカスタマイズ可能です。 状態に相当する (解決済み) は、Teams Rooms プレミアム ポータルのカスタム値です。

- **close_code**: 完全に解決されたら、インシデントに近いコードを割り当てる必要があります。 この値は、ServiceNow でカスタマイズできます。 クローズ コードと同等の値は、Teams Rooms プレミアム ポータルのカスタム値です。
