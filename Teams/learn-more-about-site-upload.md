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
description: サイトにアップロードする方法をについて説明します。
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.locations.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a9274952d74c3bf55943ed6b028fd630ab2078e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33921283"
---
<a name="adding-and-updating-locations-data"></a>場所データの追加と更新
============================

場所は、オフィス、建物、または組織のサイトの物理的な場所を示すために、組織で使用されます。 場所のページで、テキスト ファイル (.csv または .tsv) を提供することで管理者は、物理的な場所と、関連付けられているネットワークのサブネットの一覧が含まれています。 このファイルは、レポートを生成するために分析機能を呼び出すと呼び出し品質のダッシュ ボードで使用されます。 お客様は、そのサブネットのマッピングをアップロードするときにこれらのサービスが提供するレポートには、場所の名前も、レポートを容易に理解し、潜在的な問題の修復に使用が含まれます。

場所データを提供するは 1 つのデータ構造体: 現在の場所のデータを個別の編集を行うに利用できるインタ フェースはありません。 

**サブネットと場所のテーブルを編集するのには**

1. **場所のデータを置換**] をクリックします。
2. **場所データを置換**] ウィンドウで、[**ファイルを選択**する] をクリックするを参照し、編集した .csv または .tsv ファイルをアップロードします。 
3. [**アップロード**] をクリックします。 


サンプル テンプレートをダウンロードすることができます[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)。

次の例を使用すると、データ ファイルの作成に役立ちます。 

> [!IMPORTANT]
> データ ファイルは、ネットワーク、ネットワーク名など) などの列のヘッダーを含めないようにします。 これらは、情報提供のみを目的としており、ここで使用されます。 </br>

|ネットワーク|ネットワーク名|ネットワークの範囲|建物の名前|所有権の種類|建物の種類|Office タイプの建物|市区町村|郵便番号|国|都道府県|Region|内側株式会社|高速ルート|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0 |SVC-1|32|USCAMTV001|Contoso 社専用の RE&F|Office|RE&F|マウンテン ビュー|94043|ご|CA|ご|1|1|
|10.0.130.0 |SVC-1|32|USCAMTV001|Contoso 社専用の RE&F|Office|RE&F|マウンテン ビュー|94043|ご|CA|ご|1|1|
|10.0.131.0 |SVC-1|32|USCAMTV001|Contoso 社専用の RE&F|Office|RE&F|マウンテン ビュー|94043|ご|CA|ご|1|1|
|10.0.132.0 |SVC-1|32|USCAMTV001|Contoso 社専用の RE&F|Office|RE&F|マウンテン ビュー|94043|ご|CA|ご|1|1|


データ ファイルの書式設定の詳細については、[テナントのデータ ファイルの形式とデータ ファイルの構造を構築](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-building-data-file-structure)を参照してください。


## <a name="related-topics"></a>関連トピック

[通話分析をセットアップする](set-up-call-analytics.md)
