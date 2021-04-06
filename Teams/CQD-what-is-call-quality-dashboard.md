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
description: 通話品質ダッシュボード (CQD) と、それを使用して Microsoft Teams の会議および通話品質に関するレポートを表示する方法について説明します。
ms.openlocfilehash: d262449394d9ad880d13897988e40e26dd98578c
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593835"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>通話品質ダッシュボード (CQD) とは

Microsoft 通話品質ダッシュボード (CQD) [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - Microsoft Teams、Skype for Business Online、Skype for Business Server 2019 の通話と会議の品質を組織全体のレベルで表示します。 

  
最新バージョンの CQD は、ほぼリアルタイム [(NRT)](CQD-data-and-reports.md)データ フィードを備え、通話の終了から 30 分以内に CQD で通話レコードを利用できます。

CQD にエンド ユーザーを特定できる [情報 (EUII)](CQD-data-and-reports.md#euii-data)データが含まれる場合は [、Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)全体で EUII と同じ方法で管理されます。

CQD は、Teams 管理者、Skype for Business 管理者、ネットワーク エンジニアが、組織全体のレベルで通話と会議の品質を監視するのに役立ちます。 CQD を使用して、パフォーマンスの品質を向上するために **ネットワーク** を最適化します。 特定のユーザーの通話と会議の情報を調える必要がある場合は、CQD データとユーザーごとの通話分析を[組み合わせて使用します](use-call-analytics-to-troubleshoot-poor-call-quality.md)。

たとえば、CQD を使用すると、ユーザーの低品質 (ユーザーごとの通話分析を使用して確認した) がネットワークの問題に起因し、他の多くのユーザーにも影響を与えると判断できます。 CQD は、個々の通話エクスペリエンスと、Teams または Skype for Business を使用して行われた通話の全体的な品質の両方をキャプチャします。 CQD では、全体的なパターンが明らかになる可能性があります。そのため、ネットワーク エンジニアは、情報に基づいた通話品質の評価を行います。 CQD は、全体的な通話品質、サーバーとクライアントのストリーム、クライアントとクライアントのストリーム、音声品質 SLA に関する洞察を提供する通話品質メトリックのレポートを提供 [します](https://go.microsoft.com/fwlink/p/?linkid=846252)。 
  
![通話品質ダッシュボードのスクリーンショット。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

CQD では、建物とエンドポイントの情報をアップロードして、Location-Enhanced レポートを使用して、ユーザーの建物内の通話品質と信頼性を分析することができます。 データを評価して、問題が 1 人のユーザーに分離されているのか、それともユーザーの大きなセグメントに影響を与えるのか判断できます。 CQD で作成またはエンドポイント固有のビューを有効にする場合、管理者 [](CQD-upload-tenant-building-data.md)は CQD テナント データアップロード ページで建物またはエンドポイントの情報を **アップロードする必要** があります。

![通話品質ダッシュボードの通話品質レポートLocation-Enhancedスクリーンショット。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Teams のサービス品質[](quality-of-experience-review-guide.md)の管理を担当する Teams 管理者またはサポート エンジニアに詳細なガイダンスを提供する、通話と会議の品質の管理に関する記事をお見逃しなく。

## <a name="legacy-version-of-cqd-cqdlynccom"></a>従来のバージョンの CQD (CQD.lync.com)

現在のバージョンの CQD ( https://CQD.Teams.microsoft.com) は従来のバージョンの CQD ( https://CQD.lync.com) . CQD.lync.com (Skype for Business 管理センターから利用できます) は引き続き使用できますが、2020 年 7 月 1 日現在、CQD からのデータが使用されています。Teams.microsoft.com、古い CQD (CQD.lync.com) の建物やクエリ のデータを表示または変更 CQD.lync.com。 このデータを引き続き移行していない CQD.lync.com 場合は、サポート チケットを記録します。

> [!IMPORTANT]
> 2021 年 7 月 31 日より、従来のバージョンの CQD (CQD.lync.com。 この日付を終えた後、CQD に自動的にリダイレクトされます。Teams.microsoft.com データにアクセスしようと CQD.lync.com、未読の建物やクエリ データは失われます。

## <a name="use-power-bi-to-analyze-cqd-data"></a>Power BI を使用して CQD データを分析する

2020 年 1 月の新機能: [CQD 用の Power BI クエリ テンプレートをダウンロードします](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 カスタマイズ可能な Power BI テンプレートを使用して、CQD データを分析およびレポートできます。

詳細 [については、「Power BI を使用して CQD データを分析する](CQD-Power-BI-query-templates.md) 」を参照してください。



## <a name="related-topics"></a>関連項目

[Teams の通話品質の向上と監視](monitor-call-quality-qos.md)

[通話品質ダッシュボード (CQD) を設定する](turning-on-and-using-call-quality-dashboard.md)

[テナントと建物のデータをアップロードする](CQD-upload-tenant-building-data.md)

[CQD データとレポート](CQD-data-and-reports.md)

[CQD を使用して通話と会議の品質を管理する](quality-of-experience-review-guide.md)

[CQD で使用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD でのストリームの分類](stream-classification-in-call-quality-dashboard.md)

[Power BI を使用して CQD データを分析する](CQD-Power-BI-query-templates.md)


[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)
