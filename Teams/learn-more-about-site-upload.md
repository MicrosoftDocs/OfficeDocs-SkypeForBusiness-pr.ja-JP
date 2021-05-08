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
description: 物理的な場所と関連するサブネットの一覧を含むテキスト ファイルをアップロードして、レポート ラベルを追加および更新する方法について学習します。
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
ms.openlocfilehash: 481e087a6cfe2b641f6b81fcfc893d50f27cbf47
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237487"
---
<a name="add-and-update-reporting-labels"></a>レポート ラベルを追加して更新する
============================

レポート ラベルは、オフィス、ビル、または組織サイトの物理的な場所を示すために組織内で使用されます。 Microsoft Teams 管理センターの [レポート ラベル] ページでは、物理的な場所と関連付けられているネットワーク サブネットの一覧を含むテキスト ファイル (.csv または .tsv) を提供できます。 このファイルは、レポートを生成するために通話分析によって使用されます。 サブネット マッピングをアップロードすると、これらのサービスによって提供されるレポートにも場所の名前が含まれるので、レポートを理解し、潜在的な問題を修復するために使用しやすくなります。

> [!IMPORTANT]
> アップロードしたレポート ラベルは、Office 365に関する契約の下でサポート データとして処理されます。顧客データまたは個人データと見なされる情報も *含めて、* この情報はサポート目的で Microsoft エンジニアに表示されますので、Microsoft にサポート データとして提供しないデータは含めここではお使いください。

提供するレポート のラベルと場所のデータは、1 つのデータ構造です。現在、データを個別に編集できるインターフェイスはありません。

**サブネットと場所のテーブルを編集するには**

1. 管理センターの左側のナビゲーションで、[場所Microsoft Teamsラベル]  >  **をクリックします**。
2. [データ **アップロード] をクリックします**。
3. [データ **アップロード ウィンドウで**、[ファイルの選択] をクリックし、編集したファイルまたは .tsv .csvを参照してアップロードします。
4. [アップロード]**をクリックします**。

サンプル テンプレートは、 からダウンロード [できます](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)。

次の例を使用して、データ ファイルを作成します。

> [!IMPORTANT]
> データ ファイルに列見出し (ネットワーク、ネットワーク名など) を含めてはならない。 これらは情報提供のみを目的としてここで使用されます。 <br>

|ネットワーク|ネットワーク名|ネットワーク範囲|建物名|所有権の種類|建物の種類|Building Office Type|市区町村|郵便番号|国|都道府県|Region|Inside Corp|Express Route|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|マウンテン ビュー|94043|米国|CA|米国|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|マウンテン ビュー|94043|米国|CA|米国|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|マウンテン ビュー|94043|米国|CA|米国|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|マウンテン ビュー|94043|米国|CA|米国|1|1|

データ ファイルの書式設定の詳細については、「テナント データ ファイル形式」と「データ ファイル構造の [構築」を参照してください](CQD-upload-tenant-building-data.md#upload-building-data-file)。

## <a name="related-topics"></a>関連トピック

[通話分析を設定する](set-up-call-analytics.md)

[通話分析を使用して低品質の通話のトラブルシューティングを行う](use-call-analytics-to-troubleshoot-poor-call-quality.md)
