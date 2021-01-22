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
description: 物理的な場所と関連するサブネットのリストを含むテキスト ファイルをアップロードして、レポート ラベルを追加および更新する方法について学習します。
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
ms.openlocfilehash: 4a1af7f14695d1f933a9c3902b373eb668044e24
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918643"
---
<a name="add-and-update-reporting-labels"></a>レポート ラベルを追加して更新する
============================

レポート ラベルは、オフィス、建物、または組織サイトの物理的な場所を示すために組織で使用されます。 Microsoft Teams 管理センターの [レポート ラベル] ページでは、物理的な場所と関連するネットワーク サブネットの一覧を含むテキスト ファイル (.csv または .tsv) を提供できます。 このファイルは、通話分析によってレポートを生成するために使用されます。 サブネット マッピングをアップロードすると、これらのサービスによって提供されるレポートにも場所の名前が含まれるので、潜在的な問題の修復にレポートを理解し、使用しやすくなります。

> [!IMPORTANT]
> アップロードしたレポート ラベルは、Office  365 に関する契約の下でサポート データとして処理されます。この場合、顧客データまたは個人データと見なされる情報も *含めて処理されます*。 この情報はサポート目的で Microsoft エンジニアに表示されますので、Microsoft にサポート データとして提供しないデータは含めここではお使いください。

レポートのラベルと場所のデータは、単一のデータ構造です。現在、データを個別に編集できるインターフェイスはありません。

**サブネットと場所のテーブルを編集するには**

1. Microsoft Teams 管理センターの左側のナビゲーションで、[場所レポート ラベル **]**  >  **をクリックします**。
2. [場所 **データの置換] をクリックします**。
3. [場所データ **の置換]** ウィンドウで、[ファイルの選択] をクリックし、編集した .csv ファイルまたは .tsv ファイルを参照してアップロードします。
4. [アップロード **] をクリックします**。

サンプル テンプレートはここでダウンロード [できます](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)。

データ ファイルを作成するには、次の例を使用します。

> [!IMPORTANT]
> データ ファイルには、列見出し (ネットワーク、ネットワーク名など) を含めてはならない。 これらは情報提供のみを目的としてここで使用されます。 <br>

|ネットワーク|ネットワーク名|ネットワーク範囲|建物名|所有権の種類|建物の種類|建物Office種類|市区町村|郵便番号|国|都道府県|Region|Inside Corp|高速ルート|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|マウンテン ビュー|94043|米国|CA|米国|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|マウンテン ビュー|94043|米国|CA|米国|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|マウンテン ビュー|94043|米国|CA|米国|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|マウンテン ビュー|94043|米国|CA|米国|1|1|

データ ファイルの書式設定の詳細については、「テナント データ ファイル形式」および「建物データ ファイル [構造」を参照してください](CQD-upload-tenant-building-data.md#upload-building-data-file)。

## <a name="related-topics"></a>関連トピック

[通話分析を設定する](set-up-call-analytics.md)

[通話分析を使用して低品質の通話のトラブルシューティングを行う](use-call-analytics-to-troubleshoot-poor-call-quality.md)
