---
title: レポート ラベルを追加して更新する
author: tonysmit
ms.author: tonysmit
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 通話分析と通話品質ダッシュボードレポートのレポートラベルとして使用する、物理的な場所と関連するサブネットの一覧が含まれているテキストファイルをアップロードする方法について説明します。
ms.custom:
- NewAdminCenter_Update
f1.keywords:
- ms.teamsadmincenter.locations.reportinglabels.overview
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.location
- ms.teamsadmincenter.locations.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19d3197d91b7139089a940c19ff23c1dcc99a290
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707863"
---
<a name="add-and-update-reporting-labels"></a>レポート ラベルを追加して更新する
============================

レポートラベルは、オフィス、建物、または組織のサイトの物理的な場所を示すために、組織内で使用されます。 Microsoft Teams 管理センターの [レポートのラベル] ページでは、物理的な場所の一覧と関連するネットワークサブネットを含むテキストファイル (.csv または .tsv) を指定できます。 このファイルは、レポートを生成するために通話分析と通話品質ダッシュボードによって使用されます。 サブネットマッピングをアップロードすると、これらのサービスによって提供されるレポートにも場所名が含まれます。これにより、レポートがわかりやすくなり、問題が発生した場合にを修復するすることができます。

提供するレポートのラベルと場所のデータは1つのデータ構造です。現在、データを編集するために使用できるインターフェイスはありません。

**サブネットと場所の表を編集するには**

1. Microsoft Teams 管理センターの左のナビゲーションで、[**場所** > ] をクリック**します。**
2. [**場所のデータの置換**] をクリックします。
3. [**場所データの置換**] ウィンドウで、[**ファイルの選択**] をクリックし、編集した .csv または .tsv ファイルを参照してアップロードします。
4. [**アップロード**] をクリックします。

サンプルテンプレートは[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)からダウンロードできます。

次の例を使用して、データファイルを作成します。

> [!IMPORTANT]
> データファイルには、列見出し (ネットワーク、ネットワーク名など) を含めることはできません。 これらは、情報提供のためだけに使用されます。 <br>

|ネットワーク|ネットワーク名|ネットワークの範囲|建物名|所有権の種類|建物の種類|Office の種類の作成|市区町村|郵便番号|居住|都道府県|Region|企業内|簡易ルート|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0 |SVC-1|32|USCAMTV001|Contoso&F|Office|&F|山地表示|94043|プロセッサー|FR-CA|プロセッサー|1|1|
|10.0.130.0 |SVC-1|32|USCAMTV001|Contoso&F|Office|&F|山地表示|94043|プロセッサー|FR-CA|プロセッサー|1|1|
|10.0.131.0 |SVC-1|32|USCAMTV001|Contoso&F|Office|&F|山地表示|94043|プロセッサー|FR-CA|プロセッサー|1|1|
|10.0.132.0 |SVC-1|32|USCAMTV001|Contoso&F|Office|&F|山地表示|94043|プロセッサー|FR-CA|プロセッサー|1|1|

データファイルの書式設定の詳細については、「[テナントデータファイルの形式と建物データファイルの構造](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-structure)」を参照してください。

## <a name="related-topics"></a>関連トピック

[通話分析をセットアップする](set-up-call-analytics.md)
