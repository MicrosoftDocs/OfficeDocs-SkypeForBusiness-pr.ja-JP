---
title: レポート ラベルを追加して更新する
author: tonysmit
ms.author: tonysmit
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 物理的な場所と関連付けられたサブネットの一覧を含むテキスト ファイルをアップロードして、レポート ラベルを追加および更新する方法について説明します。
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
ms.openlocfilehash: 189b821e7238911190c4c72c07b863fc961f3074
ms.sourcegitcommit: ab9d27d7ddd1494539ae9424de200c9d0e76a9ec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2021
ms.locfileid: "59984612"
---
# <a name="add-and-update-reporting-labels"></a>レポート ラベルを追加して更新する

レポート ラベルは、オフィス、建物、または組織サイトの物理的な場所を示すために組織で使用されます。 Microsoft Teams管理センターの [レポート ラベル] ページでは、物理的な場所とその関連するネットワーク サブネットの一覧を含むテキスト ファイル (.csvまたは .tsv) を指定できます。 このファイルは、レポートを生成するために Call Analytics によって使用されます。 サブネット マッピングをアップロードすると、これらのサービスによって提供されるレポートにも場所名が含まれるため、潜在的な問題の修復にレポートを理解して使用しやすくなります。

> [!IMPORTANT]
> アップロードしたレポート ラベルは、顧客データまたは個人データと見なされる情報を含め、Office 365に関する契約に基づく *サポート* *データ* として処理されます。 この情報はサポート目的で Microsoft エンジニアに表示されるため、 *サポート データ* として Microsoft に提供したくないデータは含めないでください。

指定するレポート ラベルと場所データは 1 つのデータ構造です。現在、データを個別に編集するためのインターフェイスはありません。

**サブネットと場所のテーブルを編集するには**

1. Microsoft Teams管理センターの左側のナビゲーションで、[**Analytics & レポート** > **レポート**] をクリックします。
2. [**アップロード データ**] をクリックします。
3. **[アップロード データ**] ウィンドウで [**ファイルの選択**] をクリックし、編集した.csvファイルまたは .tsv ファイルを参照してアップロードします。
4. **[アップロード**] をクリックします。

サンプル テンプレート [は、ここで](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)ダウンロードできます。

次の例を使用して、データ ファイルを作成します。

> [!IMPORTANT]
> データ ファイルに列ヘッダー (ネットワーク、ネットワーク名など) を含めてはなりません。 これらは、情報提供のみを目的としてここで使用されます。 <br>

|ネットワーク|ネットワーク名|ネットワーク範囲|建物名|所有権の種類|建物の種類|Office型の構築|市区町村|郵便番号|国|都道府県|Region|会社の内部|高速ルート|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|マウンテン ビュー|94043|私たち|CA|私たち|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|マウンテン ビュー|94043|私たち|CA|私たち|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|マウンテン ビュー|94043|私たち|CA|私たち|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|マウンテン ビュー|94043|私たち|CA|私たち|1|1|

データ ファイルの書式設定の詳細については、「 [テナント データ ファイルの形式」と「データ ファイル構造の構築](CQD-upload-tenant-building-data.md#upload-building-data-file)」を参照してください。

## <a name="related-topics"></a>関連項目

[通話分析を設定する](set-up-call-analytics.md)

[通話分析を使用して通話品質の低下のトラブルシューティングを行う](use-call-analytics-to-troubleshoot-poor-call-quality.md)
