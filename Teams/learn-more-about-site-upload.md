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
description: レポートラベルを追加して更新する方法については、「物理的な場所と関連サブネットの一覧を含むテキストファイルをアップロードする」を参照してください。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- ms.teamsadmincenter.locations.reportinglabels.overview
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.location
- ms.teamsadmincenter.locations.overview
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b32e9db020b3498e8185b4d38e25d1d9a1feca5
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085293"
---
<a name="add-and-update-reporting-labels"></a>レポート ラベルを追加して更新する
============================

レポートラベルは、オフィス、建物、または組織のサイトの物理的な場所を示すために、組織内で使用されます。 Microsoft Teams 管理センターの [レポートのラベル] ページでは、物理的な場所の一覧と関連するネットワークサブネットを含むテキストファイル (.csv または .tsv) を指定できます。 このファイルは、レポートを生成するために通話分析によって使用されます。 サブネットマッピングをアップロードすると、これらのサービスによって提供されるレポートにも場所名が含まれます。これにより、レポートがわかりやすくなり、問題が発生した場合にを修復するすることができます。

> [!IMPORTANT]
> アップロードするレポートラベルは、Office 365 の契約で*サポートデータ*として扱われます。これには、*顧客データ*や*個人データ*と見なされる情報も含まれます。 この情報は Microsoft エンジニアにサポートを提供するため、サポート*データ*として提供したくないデータは含めないでください。

提供するレポートのラベルと場所のデータは1つのデータ構造です。現在、データを編集するために使用できるインターフェイスはありません。

**サブネットと場所の表を編集するには**

1. Microsoft Teams 管理センターの左のナビゲーションで、[**場所**] をクリックし  >  **Reporting labels**ます。
2. [**場所のデータの置換**] をクリックします。
3. [**場所の置換] データ**ウィンドウで、[**ファイルの選択**] をクリックし、編集した .csv または .tsv ファイルを参照してアップロードします。
4. [**アップロード**] をクリックします。

サンプルテンプレートは[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)からダウンロードできます。

次の例を使用して、データファイルを作成します。

> [!IMPORTANT]
> データファイルには、列見出し (ネットワーク、ネットワーク名など) を含めることはできません。 これらは、情報提供のためだけに使用されます。 <br>

|ネットワーク|ネットワーク名|ネットワークの範囲|建物名|所有権の種類|建物の種類|Office の種類の作成|市区町村|郵便番号|居住|都道府県|Region|企業内|簡易ルート|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso&F|Office|&F|山地表示|94043|プロセッサー|FR-CA|プロセッサー|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso&F|Office|&F|山地表示|94043|プロセッサー|FR-CA|プロセッサー|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso&F|Office|&F|山地表示|94043|プロセッサー|FR-CA|プロセッサー|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso&F|Office|&F|山地表示|94043|プロセッサー|FR-CA|プロセッサー|1|1|

データファイルの書式設定の詳細については、「[テナントデータファイルの形式と建物データファイルの構造](CQD-upload-tenant-building-data.md#upload-building-data-file)」を参照してください。

## <a name="related-topics"></a>関連トピック

[通話分析を設定する](set-up-call-analytics.md)
