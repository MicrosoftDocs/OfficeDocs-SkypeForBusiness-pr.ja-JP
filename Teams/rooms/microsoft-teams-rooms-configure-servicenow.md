---
title: ServiceNow を Teams Rooms 用に構成する
author: cazawideh
ms.author: czawideh
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Teams Rooms ポータルで ServiceNow をプレミアムする
f1keywords: ''
ms.openlocfilehash: a8f1e43ca52ee9fa155115fb911f88221cb6fdd0
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432709"
---
# <a name="configure-servicenow-for-teams-rooms"></a>ServiceNow を Teams Rooms 用に構成する

この記事では、Teams Rooms ポータルで ServiceNow 環境を構成するための前提条件とプレミアム説明します。

## <a name="before-you-begin"></a>はじめに

### <a name="teams-rooms-prerequisites"></a>Teams会議室の前提条件

- サービス管理者ロールが割り当てられている必要があります。 詳細については、「Microsoft Teams Rooms Managed Services を使用したロール[ベースのアクセス制御」を参照してください](microsoft-teams-rooms-premium-rbac.md)。

### <a name="servicenow-prerequisites"></a>ServiceNow の前提条件

- 基本承認サインイン、または OAuth サインイン。 詳細については、「ServiceNow での [資格情報の作成」](https://developer.servicenow.com/dev.do#!/learn/learning-plans/rome/servicenow_application_developer/app_store_learnv2_rest_rome_creating_credentials) を参照してください。
- ServiceNow インスタンスとそのインスタンス ホスト名と API URI
- 1 つ以上incident_managerロール
- Table API をサポートする ServiceNow のソフトウェア バージョン

## <a name="configure-your-environment"></a>環境を構成する

環境の構成方法は高度にカスタマイズ可能であり、組織のニーズに応じて異なります。 次の手順では、ServiceNow の既存の構成を Teams Rooms プレミアムします。

1. コピーする ServiceNow インスタンスを開きます。 この情報は、Teams Rooms ポータルで構成フォームをプレミアムがあります。
2. 新しいブラウザー タブで、[会議室] ポータルの [Teamsにプレミアムし](https://portal.rooms.microsoft.com/)、[ ] に移動 **設定。** 次に、左側 **のナビゲーション メニューで [ServiceNow]** を選択して、構成フォームを開きます。
3. サインインする認証方法を選択し、ServiceNow インスタンス ホストと API URI を入力します。
4. [フィールド マッピング] セクションの [ServiceNow フィールド] 列に必要なすべての項目を事前に入力する必要があります。 次の表には、各 ServiceNow フィールドとそれに対応する [会議室] Microsoft Teamsが含まれている。 [フィールド マッピング] セクションの各行のアクションを完了します。 各 ServiceNow フィールドの定義については、「ServiceNow フィールドの定義 [」を参照してください](#servicenow-field-definitions)。

| ServiceNow フィールド | Microsoft Teams[会議室] フィールド | アクション |
| --- | --- | --- |
| short_description | インシデントの説明 | アクションは必要はありません。 [Teams] フィールドは自動的に入力されます。 |
| description | 最初のメッセージ | アクションは必要はありません。 [Teams] フィールドは自動的に入力されます。 |
| assignment_group | ルーム グループ | ServiceNow assignment_groupの値をコピーし、構成フォームの [ServiceNow 値] フィールドに貼り付けます。 複数のユーザー設定がある場合assignment_group追加のカスタム値ごとに[ルーム グループの追加] を選択します。 |
| 重大度 | リング | 重大度は、ServiceNow のカスタム値です。 これは、ServiceNow インスタンスの 2 番目の列の 4 番目の項目です。 値をコピーし、構成フォームの ServiceNow 値フィールドに貼り付けます。 複数の重大度値がある場合は、追加のカスタム値ごとに [呼び出しの追加] を選択します。 |
| コメント (省略可能) | カスタム値* | コメント フィールドを構成フォームに追加するには、フィールド **マッピング** セクションの上部にある [追加] を選択します。 ServiceNow インスタンスのコメント値をコピーし、構成フォームの ServiceNow フィールドに貼り付けます。 ドロップダウン メニューから [Microsoft Teams] フィールドに割り当て、ServiceNow の値をコピーして貼り付けます。 |
| state (解決済み) | カスタム値* | ServiceNow インスタンスから解決状態をコピーし、構成フォームの ServiceNow 値フィールドに貼り付けます。 |
| close_code | カスタム値* | ServiceNow **インスタンスの [** 解決情報] タブで、閉じるコードをコピーし、[ServiceNow 値] フィールドに貼り付け、構成フォームに貼り付けます。 |

*ドロップダウン メニューからカスタム値を選択する

>[!NOTE]
>カスタム値が見つからなかった場合は、ServiceNow 管理者にお問い合わせください。

[インシデントの解決] セクションに必要なフィールドを追加するには、[追加] を **選択します**。

## <a name="test-and-enable"></a>テストと有効化

構成フォームを完了した後、ページ **の下部にある [** テスト] を選択します。 構成を送信するには、テストが必要です。

テストが正常に完了したら、[送信] **を選択して** 変更を保存します。 組織で ServiceNow を有効にする準備ができたら **、[ServiceNow** を有効にしますか?] トグルを [オン] に切り **替えます**。

## <a name="servicenow-field-definitions"></a>ServiceNow フィールドの定義

- **short_description:** ServiceNow の短い説明フィールドは、インシデントの概要を提供する 160 文字の短い英数字の値です。 簡単な説明は、Teams Rooms プレミアムに相当します。

- **description:** ServiceNow の description フィールドは、ServiceNow インシデントの会話履歴の最初の値です。 説明は、Teams Rooms プレミアムメッセージと同じです。

- **assignment_group:** ServiceNow の割り当てグループ フィールドは、インシデントを整理するために使用されます。 割り当てグループは、[会議室] ポータルの [会議室Teamsとプレミアムします。 既定では、1 つのルーム グループが作成され、さらに追加できます。 グループの数と、インシデントをグループ化する方法を決定します。 たとえば、インシデントを場所別に整理することができます。

- **重大度**: ServiceNow の重大度フィールドは、インシデントを優先度別に整理するために使用されます。 優先度を指定する値はカスタマイズ可能です。 重大度は、Teams Rooms ポータルの [呼びプレミアムと同じです。 Teams Rooms ポータルでプレミアムリングをカスタマイズするには、左側のナビゲーション メニューの [**更新** プログラム] に移動します。 次に、[リング] タブ **に移動し** 、[リングの追加 **] を選択します**。

- **コメント**: コメントは、ServiceNow インスタンスのカスタム必須フィールドをポータル構成の Teams Rooms に含プレミアムフィールドです。 コメントと同等の値は、Teams Rooms プレミアムです。

- **state (解決済み)**: ServiceNow の状態 (解決済み) フィールドは、インシデントの解決方法を指定するために使用され、インシデントを閉じる必要があります。 状態 (解決済み) の値はカスタマイズ可能です。 状態 (解決済み) と同等の値は、Teams Rooms プレミアムです。

- **close_code:** インシデントが完全に解決された後に、近いコードをインシデントに割り当てる必要があります。 この値は ServiceNow でカスタマイズできます。 閉じるコードと同等の値は、Teams Rooms プレミアムです。
