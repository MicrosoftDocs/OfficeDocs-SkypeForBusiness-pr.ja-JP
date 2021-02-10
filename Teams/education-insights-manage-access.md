---
title: Education Insights へのユーザー アクセスを管理する
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Microsoft Teams の Education Insights へのユーザー アクセスを管理します。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32bd773975ff6b67d28ab765ffa7c932e978af7d
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145937"
---
# <a name="manage-user-access-to-education-insights"></a>Education Insights へのユーザー アクセスを管理する

このドキュメントでは、[Microsoft Teams の Education Insights](class-insights.md) へのユーザー アクセスを管理するために必要な手順について説明します。

教育リーダー、地区リーダー、学校長、学部長、カウンセラー、教科長、プログラム ディレクター、ソーシャル ワーカー、心理学者に許可を与える必要があります。 教職員には、クラス チームを所有している場合、*自動的* に許可が与えられます。

組織レベルの Insights を提供するには、[学生情報システム (SIS) からデータをインポートする](education-insights-sis-data-sync.md)必要があります。これは、Insights が教育システムの階層構造を正しくマッピングできるようにするためです。

> [!NOTE]
> Insights へのユーザー アクセスを管理できるのはグローバル管理者のみです。

> [!TIP]
> すべての教育リーダーに対して Insights を有効にして、各学校を理解するためのデータを入手し、問題をすばやく特定して教育者をサポートできるようにすることをお勧めします。 パイロットを実行している場合でも、すべての教育リーダーに対して Insights を有効にしておくと役立つ場合がありますが、コミュニケーションはパイロット グループのユーザーのみを対象とします。



## <a name="grant-permissions"></a>アクセス許可を付与する

* Insights アプリを開き、**[設定]** タブをクリックし、**[ユーザーのアクセス許可]** を選択する

:::image type="content" source="media/insights-user-permissions.png" alt-text="設定":::

* **[ユーザーの追加]** を選択します。
* 各ユーザーのユーザー名またはメール アドレスを入力します。
* アクセス許可レベルを選択します。
  * **[すべての組織へのアクセス]** では、ユーザーはすべてのレベルのすべての組織単位を表示できます。
  * **[特定の学校へのアクセス]** では、ユーザーは選択した学校のみを表示できます。 入力を開始し、一覧から学校を選択します。 複数の学校をまとめて追加することができます。
* **[新しいユーザーを追加する]** をクリックします。

:::image type="content" source="media/insights-add-users.png" alt-text="アクセス許可を付与する":::

> [!NOTE]
> それらを必要とする教育リーダーとそのリーダーが担当する組織単位にのみ許可を与えます。 特定の組織のユーザー許可が必要かどうかわからない場合は、法務担当者や人事担当者など、組織のプライバシーに関する専門家に相談してください。

## <a name="edit-permissions"></a>アクセス許可を編集する
* 特定のユーザーを選び、**[アクセス許可の編集]** を選択します。
* アクセス許可レベルまたは学校の一覧を更新し、**[アクセス許可の更新]** をクリックします。

:::image type="content" source="media/insights-edit-users.png" alt-text="アクセス許可を編集する":::

## <a name="remove-permissions"></a>権限の削除
* 削除するユーザーを選択し、**[ユーザーの削除]** を選択します。
* これらのユーザーは、組織レベルの Insights にアクセスできなくなりますが、クラス チームを所有している場合は、クラス レベルの Insights にアクセスできます。

:::image type="content" source="media/insights-remove-users.png" alt-text="アクセス許可を削除する":::
