---
title: 場所データの追加と更新
author: tonysmit
ms.author: tonysmit
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: サイトにアップロードする方法について説明します。
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.locations.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e7e9211b207c008de22fe86ae0c7bb6c9f9ac51
ms.sourcegitcommit: 1336f6c182043016c42660d5f21632d82febb658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "34667483"
---
<a name="adding-and-updating-locations-data"></a>場所データの追加と更新
============================

オフィス、建物、または組織のサイトの物理的な場所を示すために、組織内で場所を使用します。 [場所] ページを使用すると、管理者は、物理的な場所と関連付けられたネットワークサブネットの一覧を含むテキストファイル (.csv または .tsv) を提供することができます。 このファイルは、レポートを生成するために通話分析と通話品質ダッシュボードによって使用されます。 ユーザーがサブネットマッピングをアップロードすると、これらのサービスによって提供されるレポートにも場所名が含まれます。これにより、レポートがわかりやすくなり、問題が発生した場合にを修復するすることができます。

指定した場所データは1つのデータ構造です。現在、位置情報データを編集するために使用できるインターフェイスはありません。 

**サブネットと場所の表を編集するには**

1. [**場所のデータの置換**] をクリックします。
2. [**場所データの置換**] ウィンドウで、[**ファイルの選択**] をクリックし、編集した .csv または .tsv ファイルを参照してアップロードします。 
3. [**アップロード**] をクリックします。 


サンプルテンプレートは[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)からダウンロードできます。

次の例を使用して、データファイルを作成することができます。 

> [!IMPORTANT]
> データファイルには、列見出し (ネットワーク、ネットワーク名など) を含めることはできません。 これらは、情報提供のためだけに使用されます。 </br>

|ネットワーク|ネットワーク名|ネットワークの範囲|建物名|所有権の種類|建物の種類|Office の種類の作成|市区町村|郵便番号|居住|都道府県|Region|企業内|簡易ルート|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0 |SVC-1|32|USCAMTV001|Contoso&F|Office|&F|山地表示|94043|プロセッサー|FR-CA|プロセッサー|1|1|
|10.0.130.0 |SVC-1|32|USCAMTV001|Contoso&F|Office|&F|山地表示|94043|プロセッサー|FR-CA|プロセッサー|1|1|
|10.0.131.0 |SVC-1|32|USCAMTV001|Contoso&F|Office|&F|山地表示|94043|プロセッサー|FR-CA|プロセッサー|1|1|
|10.0.132.0 |SVC-1|32|USCAMTV001|Contoso&F|Office|&F|山地表示|94043|プロセッサー|FR-CA|プロセッサー|1|1|


データファイルの書式設定の詳細については、「[テナントデータファイルの形式と建物データファイルの構造](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-structure)」を参照してください。


## <a name="related-topics"></a>関連トピック

[通話分析をセットアップする](set-up-call-analytics.md)
