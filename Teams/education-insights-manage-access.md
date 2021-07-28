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
ms.openlocfilehash: 2a8883b48b2fc5efc33b3c4e0128cc5ac3d3c760
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587296"
---
# <a name="manage-user-access-to-education-insights"></a>Education Insights へのユーザー アクセスを管理する

このドキュメントでは、[Microsoft Teams の Education Insights](class-insights.md) へのユーザー アクセスを管理するために必要な手順について説明します。

教育リーダー、地区リーダー、学校長、学部長、カウンセラー、教科長、プログラム ディレクター、ソーシャル ワーカー、心理学者に許可を与える必要があります。 教職員には、クラス チームを所有している場合、*自動的* に許可が与えられます。

組織レベルの Insights を提供するには、[学生情報システム (SIS) からデータをインポートする](education-insights-sis-data-sync.md)必要があります。これは、Insights が教育システムの階層構造を正しくマッピングできるようにするためです。

> [!NOTE]
> Insights へのユーザー アクセスを管理できるのはグローバル管理者のみです。

> [!TIP]
> すべての教育リーダーに対して Insights を有効にして、各学校を理解するためのデータを入手し、問題をすばやく特定して教育者をサポートできるようにすることをお勧めします。 パイロットを実行している場合でも、すべての教育リーダーに対して Insights を有効にしておくと役立つ場合がありますが、コミュニケーションはパイロット グループのユーザーのみを対象とします。

## <a name="manange-permissions"></a>アクセス許可の管理

* Insights アプリを開き、**[設定]** タブをクリックし、**[ユーザーのアクセス許可]** を選択する

:::image type="content" source="media/insights-user-permissions.png" alt-text="設定":::

> [!NOTE]
> 組織レベルのアクセス許可を付与すると、そのユーザーはその下のすべての組織単位を見ることができます。
> 
> それらを必要とする教育リーダーとそのリーダーが担当する組織単位にのみ許可を与えます。 特定の組織のユーザー許可が必要かどうかわからない場合は、法務担当者や人事担当者など、組織のプライバシーに関する専門家に相談してください。

## <a name="role-based-permissions"></a>役割に基づくアクセス許可

[SDS V2.1 ファイル形式](/schooldatasync/sds-v2.1-csv-file-format)または[ SDS V2 ファイル形式](/schooldatasync/sds-v2-csv-file-format)を使用した場合、教育システム内のすべての役割と学校のすべての階層をインポートすることができます。 この完全なマッピングにより、役割にアクセス許可を割り当てることができます。 

> [!NOTE]
> ユーザーに役割が割り当てられた場合は、そのユーザーに関連するデータを見るための適切なアクセス許可が自動的に付与されます。
>
> ユーザーがある役割を外れた場合、その役割に対するアクセス許可は自動的に取り消されます (ただし、個々のアクセス許可は維持される場合があります)。


* 必要に応じて、**[役割に基づくアクセス許可]** タブをクリックします。

  教育組織での役割の一覧、各役割の階層レベル、その役割を割り当てられているユーザー数、役割のアクセス許可限レベルが表示されます。 
  
  :::image type="content" source="media/insights-role-based-permissions.png" alt-text="役割に基づくアクセス許可":::
  
  1 つ以上の組織レベルでの役割がある場合、その役割は各レベルで 1 回ずつ、複数回表示されます。 スクリーンショットでは、学校レベルと地区レベルの両方に校長が存在するため、'校長' には 2 つの行があります。
  
* 各役割について、鉛筆アイコンをクリックして、アクセス許可レベルを選択します。 既定では、役割に分析情報を表示するアクセス許可がありません。
* 権限レベルの選択 - **自分の組織のデータを表示** または **なし**。

  :::image type="content" source="media/insights-role-based-permissions-panel.png" alt-text="役割に基づくアクセス許可パネル":::
  
  より微妙なアクセス許可レベルを必要とするユーザーがリストに表示された場合は、[SIS からインポートされたデータ](education-insights-sis-data-sync.md)でそのユーザーの役割や組織を調整し、(必要に応じて) [個々のアクセス許可を付与](#grant-individual-permission-to-a-user)します。

* **[変更の保存]** をクリックします。

  この権限レベルは、この役割と組織レベルを持つ任意の新規ユーザーに自動的に割り当てられるようになりました。 ユーザーは、その階層のレベルと階層下のすべての組織単位のデータを見ることができます。  


## <a name="individual-permissions"></a>個々のアクセス許可

SDS V2 を使用して組織の SIS データをインポートしていない場合は、個々のアクセス許可を使用してユーザーのアクセス許可を調整したり、ユーザーごとにアクセス許可を割り当てたりします。

* **[個々のアクセス許可]** タブをクリックします。
  
  教育組織で個々のアクセス許可を付与されているユーザーが表示されます。 
  
  :::image type="content" source="media/insights-individual-permissions.png" alt-text="個々のアクセス許可":::
  
### <a name="grant-individual-permission-to-a-user"></a>個々のアクセス許可をユーザーに付与する
* 画面左上の **[個々のアクセス許可]** をクリックします。
* 各ユーザーのユーザー名またはメール アドレスを入力します。
* アクセス許可レベルを選択します。
  * **[すべて]** では、ユーザーはすべてのレベルのすべての組織単位を表示できます。 これはほとんど使用されていません。
  * **特定の組織** とは、ユーザーが選択した組織単位と、その下のすべての組織単位を表示することを意味します。 入力を開始し、一覧から組織単位を選択します。
* **[アクセス許可の付与]** をクリックして保存します。

### <a name="change-the-individual-permission-of-a-user"></a>ユーザーの個々のアクセス許可の変更
* 関連するユーザーに対して、鉛筆アイコンをクリックして、個々のアクセス許可レベルを選択します。
* アクセス許可レベルを選択します。
  * **[すべて]** では、ユーザーはすべてのレベルのすべての組織単位を表示できます。 これはほとんど使用されていません。
  * **特定の組織** とは、ユーザーが選択した組織単位と、その下のすべての組織単位を表示することを意味します。 入力を開始し、一覧から組織単位を選択します。
  * **[なし]** は、ユーザーが自分の役割によって自動的に割り当てられた組織単位 (ある場合) のみを表示することを意味します。
  
  :::image type="content" source="media/insights-individual-permissions-panel.png" alt-text="個々のアクセス許可パネル":::

* **[変更の保存]** をクリックして保存します。
