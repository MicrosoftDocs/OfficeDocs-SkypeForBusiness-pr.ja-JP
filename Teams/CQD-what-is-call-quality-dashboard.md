---
title: 通話品質ダッシュボード (CQD) とは?
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 通話品質ダッシュボード (CQD) と、それを使用して Microsoft Teams の会議と通話品質に関するレポートを表示する方法について説明します。
ms.openlocfilehash: f87f8184b0417d04206d31780392f21dca387d10
ms.sourcegitcommit: 115e44f33fc7993f6eb1bc781f83eb02a506e29b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2021
ms.locfileid: "60909558"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>通話品質ダッシュボード (CQD) とは?

Microsoft 通話品質ダッシュボード (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - Microsoft Teams、Skype for Business Online、Skype for Business Server 2019 に関する通話と会議の品質を **組織全体レベル** で表示します。 

  
最新バージョンの CQD は、[near-real-time (NRT) データ フィード](CQD-data-and-reports.md)を備えています。つまり、通話レコードは、呼び出しの終了から 30 分以内に CQD で使用できます。

CQD に [個人を特定できる情報 (EUII) データが含まれている場合](CQD-data-and-reports.md#euii-data)、[Microsoft 365 全体の EUII](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview) と同じ方法で管理されます。

CQD は、Teams 管理者、Skype for Business 管理者、ネットワーク エンジニアが組織全体のレベルで通話と会議の品質を監視できるように設計されています。 CQD を使用して **ネットワークを最適化** してパフォーマンスの品質を向上させます。 **固有のユーザー** の通話と会議の情報を確認する必要がある場合は、CQD データをユーザーごとの[通話分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)と組み合わせて使用します。

たとえば、CQD を使用すると、(ユーザーごとの通話分析を使用して観察した) ユーザーの通話品質の低下は、他の多くのユーザーにも影響するネットワークの問題が原因であると判断できます。 CQD は、個々の通話エクスペリエンスと、Teams または Skype for Business を使用して行われた通話の全体的な品質の両方を捕捉します。 CQD を使うと、全体的なパターンが明らかになる場合があるので、ネットワーク エンジニアは情報に基づいた通話品質の評価を行うことができます。 CQD には、通話品質の指標に関するレポートが示されます。これにより、全体的な通話品質、サーバー/クライアント間のストリーム、クライアント/クライアント間のストリーム、および音声品質 [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252) についての分析情報が得られます。 
  
![通話品質ダッシュボードのスクリーンショット。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

CQD では、建物とエンドポイントの情報をアップロードすることをお勧めします。これにより、位置情報拡張レポートを使用して、ユーザーの建物内の通話の品質と信頼性を分析できます。 データを評価して、問題が 1 人のユーザーに分離されているか、より大きなユーザー セグメントに影響するかを判断できます。 CQD で建物またはエンドポイント固有のビューを有効にするには、管理者が CQD の **テナント データのアップロード** ページに[建物またはエンドポイントの情報をアップロードする](CQD-upload-tenant-building-data.md)必要があります。

![通話品質ダッシュボードの位置情報拡張レポートのスクリーンショット。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

「[通話と会議の品質の管理](quality-of-experience-review-guide.md)」の記事をお見逃しなく。Teams のサービス品質の管理を担当する Teams 管理者またはサポート エンジニアに詳細なガイダンスを提供します。


## <a name="use-power-bi-to-analyze-cqd-data"></a>Power BI を使用して CQD データを分析する

2020 年 1 月の新機能: [CQD 用の Power BI クエリ テンプレートのダウンロード](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 CQD データの分析やレポートに使えるカスタマイズ可能な Power BI テンプレートです。

「[Power BI を使って CQD データを分析する](CQD-Power-BI-query-templates.md)」をご覧ください。



## <a name="related-topics"></a>関連項目

[Teams の通話品質の向上と監視](monitor-call-quality-qos.md)

[通話品質ダッシュボード (CQD) をセットアップする](turning-on-and-using-call-quality-dashboard.md)

[テナントと建物のデータをアップロードする](CQD-upload-tenant-building-data.md)

[CQD のデータとレポート](CQD-data-and-reports.md)

[CQD を使用して通話と会議の品質を管理する](quality-of-experience-review-guide.md)

[CQD で利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD のストリーム分類](stream-classification-in-call-quality-dashboard.md)

[Power BI を使用して CQD データを分析する](CQD-Power-BI-query-templates.md)


[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)
