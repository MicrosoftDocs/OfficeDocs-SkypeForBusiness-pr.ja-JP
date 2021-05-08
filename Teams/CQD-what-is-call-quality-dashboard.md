---
title: 通話品質ダッシュボード (CQD) とは
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 通話品質ダッシュボード (CQD) と、このダッシュボードを使用して、会議や通話の品質に関するレポートを表示する方法についてMicrosoft Teams。
ms.openlocfilehash: d262449394d9ad880d13897988e40e26dd98578c
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593835"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>通話品質ダッシュボード (CQD) とは

Microsoft 通話品質ダッシュボード (CQD) [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - Microsoft Teams、Skype for Business Online、および Skype for Business Server 2019 の通話と会議の品質を組織全体で表示します。 

  
最新バージョンの CQD では、ほぼリアルタイム [(NRT)](CQD-data-and-reports.md)のデータ フィードが備わっています。つまり、呼び出しの終了から 30 分以内に CQD で通話レコードを利用できます。

CQD にエンド ユーザー識別可能な[情報 (EUII)](CQD-data-and-reports.md#euii-data)データが含まれる場合は、 全体を通じて EUII と同じ方法[で管理Microsoft 365。](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)

CQD は、組織全体のTeams、Skype for Business 管理者、ネットワーク エンジニアが通話と会議の品質を監視するのに役立ちます。 CQD を使用して、ネットワークを最適化 **して** パフォーマンスの品質を向上させます。 特定のユーザーの通話と会議の情報を調ぶ必要がある場合は、ユーザーごとの呼び出し分析と組み合わせて CQD データ[を使用します](use-call-analytics-to-troubleshoot-poor-call-quality.md)。

たとえば、CQD を使用すると、ユーザーの低品質 (ユーザーごとの通話分析を使用して観察した) が、他の多くのユーザーにも影響を与えるネットワークの問題が原因と判断できます。 CQD は、個々の呼び出しエクスペリエンスと、Teams または Skype for Business を使用して行われた呼び出しの全体的な品質の両方をキャプチャします。 CQD では、全体的なパターンが明らかになる可能性があります。そのため、ネットワーク エンジニアは、通話品質に関する情報に基づいた評価を行います。 CQD は、全体的な通話品質、サーバー クライアント ストリーム、クライアント クライアント ストリーム、音声品質 SLA に関する分析情報を提供する通話品質メトリックのレポートを提供 [します](https://go.microsoft.com/fwlink/p/?linkid=846252)。 
  
![通話品質ダッシュボードのスクリーンショット。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

CQD では、建物とエンドポイントの情報をアップロードして、Location-Enhanced レポートを使用して、ユーザーの建物内の通話品質と信頼性を分析できます。 データを評価して、問題が 1 人のユーザーに分離されているのか、それともより大きなユーザー セグメントに影響を及ぼすのか判断できます。 CQD で構築ビューまたはエンドポイント固有のビューを有効にするには、[](CQD-upload-tenant-building-data.md)管理者が CQD テナント データの作成またはエンドポイント情報を [CQD テナント データ] ページにアップロードアップロードがあります。

![通話品質ダッシュボードの [通話レポート] Location-Enhancedスクリーンショット。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

通話と会議品質の[](quality-of-experience-review-guide.md)管理に関する記事をお見逃しなく。この記事では、Teams でサービス品質の管理を担当する Teams 管理者またはサポート エンジニアに関する詳細なガイダンスを提供しています。

## <a name="legacy-version-of-cqd-cqdlynccom"></a>従来のバージョンの CQD (CQD.lync.com)

現在のバージョンの CQD ( は https://CQD.Teams.microsoft.com) 、従来のバージョンの CQD ( に置き換えました https://CQD.lync.com) 。 引き続き CQD.lync.com (Skype for Business 管理センターから利用可能) を使用できますが、2020 年 7 月 1 日の現在、CQD からのデータが使用されています。Teams.microsoft.com、古い CQD (CQD.lync.com) から建物やクエリ データを表示または変更 CQD.lync.com。 このデータを移行していない場合は CQD.lync.com、サポート チケットを記録します。

> [!IMPORTANT]
> 2021 年 7 月 31 日より、従来のバージョンの CQD (CQD.lync.com) が廃止されます。 その日付が終わり、自動的に CQD にリダイレクトされます。Teams.microsoft.com にアクセスしようとすると、CQD.lync.com、および見落とされていない建物またはクエリ データは失われます。

## <a name="use-power-bi-to-analyze-cqd-data"></a>CQD Power BI分析するには、次のコマンドを使用します。

2020 年 1 月の新機能: [CQD Power BIテンプレートをダウンロードします](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 カスタマイズ可能Power BI、CQD データの分析とレポートに使用できるテンプレートです。

詳細[については、「Power BI を使用して CQD データを分析する](CQD-Power-BI-query-templates.md)」を参照してください。



## <a name="related-topics"></a>関連トピック

[Teams の通話品質の向上と監視](monitor-call-quality-qos.md)

[通話品質ダッシュボード (CQD) を設定する](turning-on-and-using-call-quality-dashboard.md)

[アップロードとデータの構築](CQD-upload-tenant-building-data.md)

[CQD データとレポート](CQD-data-and-reports.md)

[CQD を使用して通話と会議の品質を管理する](quality-of-experience-review-guide.md)

[CQD で使用可能なディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD のストリーム分類](stream-classification-in-call-quality-dashboard.md)

[CQD Power BI分析するには、次のコマンドを使用します。](CQD-Power-BI-query-templates.md)


[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)
