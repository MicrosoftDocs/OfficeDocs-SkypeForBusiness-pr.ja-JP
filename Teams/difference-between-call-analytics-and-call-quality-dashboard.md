---
title: 呼び出しを分析し、通話品質のダッシュ ボード
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 分析機能を呼び出すと品質のダッシュ ボードを呼び出すを監視し、通話品質の問題のトラブルシューティングに使用する場合について説明します。
ms.openlocfilehash: a212afea9f8d5010fa68af66ce72b39280a7d11c
ms.sourcegitcommit: 09fcd68e30e7f83110f98172382c74f970b339a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2019
ms.locfileid: "29442438"
---
# <a name="call-analytics-and-call-quality-dashboard"></a>呼び出しを分析し、通話品質のダッシュ ボード

マイクロソフトのチームとビジネス用の Skype が得を監視し、通話品質の問題をトラブルシューティングするための 2 つの方法: 呼び出しの分析と品質のダッシュ ボードを呼び出します。 この記事では、これらの両方について説明し、どのような場合にそれぞれの方法を使用するべきかを示します。
  
**コール分析では、マイクロソフトのチームとビジネス管理センターの Skype です。** すべてのコール情報とユーザーのデータを表示するには、[**呼び出し履歴**] タブを使用します。ダッシュ ボードからユーザーを検索するか、[プロファイル] ページでユーザーの検索、または左側のナビゲーションで、**ユーザー**からユーザーを検索してこれを行うことができます。

> [!IMPORTANT]
> ヘルプデスク エージェントのアクセス許可とネットワーク トポロジのアップロードがで使用できる新しい管理ポータルで、今後数か月。 使用を続行する間、https://adminportal.services.skypeforbusiness.comの第 1 層および第 2 層のヘルプデスクへのアクセス。
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a>通話分析とは何ですか? どのような場合に使用するものですか?

分析機能の呼び出しは、デバイス、ネットワーク、および特定のコールとビジネス アカウントに、マイクロソフトのチームまたは Skype では、各ユーザーが会議に関連する接続に関する詳細情報を示しています。 Office 365 管理者の場合、マイクロソフトのチームとビジネス用の Skype の通話品質と接続の問題のトラブルシューティングを行う分析機能の呼び出しを使用できます。

マイクロソフト チーム & ビジネス管理センターの Skype のユーザーにこの情報を表示するには、すべての通話や会議を表示してそのユーザーが過去 30 日間の参加しているユーザーの詳細ページで、そのユーザーの [**通話履歴**] タブをクリックします。

![ユーザー データの分析機能を呼び出します。](media/call-analytics-user-data.png)

メディアの詳細を含む、ネットワークの統計情報の特定のセッションに関する追加情報を取得するには、詳細を表示するセッションをクリックします。

![ユーザー セッション データの分析機能を呼び出します。](media/call-analytics-user-data-session.png)

管理者以外が、外部の仕入先からのヘルプデスク担当者などをする場合は分析機能の呼び出しを使用することができますアクセス許可を割り当てる分析機能の呼び出しを使用することができますが、マイクロソフトのチーム & ビジネス管理センターの Skype の残りの部分にアクセスすることはできません。 
  
- **ヘルプデスク エージェント通信のスペシャ リストのアクセス許可をサポートする**: エージェントは、限られたデータと分析の呼び出しで、個人を特定できる情報 (PII) を参照してください。 呼び出しをトラブルシューティングすることができますが、通信のサポート ・ エンジニアに会議の問題を渡します。
    
- **通信ヘルプデスク担当者は、エンジニア リングのアクセス許可をサポート**: エージェントは、分析機能の呼び出しで使用可能なすべてのデータを参照してくださいし、通話や会議の両方のトラブルシューティングを行います。 通話ログやユーザー情報に対するフル アクセスが付与されています。

> [!NOTE]
> 通信のサポート ・ スペシャ リストの役割は、第 1 層のサポートに相当と通信のサポート ・ エンジニアの役割は、第 2 層のサポートに相当します。

サポート担当者との通信通信の詳細については、エンジニアの役割をサポートして、[チームを管理する管理者の役割を使用してマイクロソフトのチーム](using-admin-roles.md)を参照してください。

> [!IMPORTANT]
> ヘルプデスク エージェントのアクセス許可とネットワーク トポロジのアップロードは、マイクロソフトのチーム & ビジネス管理センターの Skype で利用できます。 通信のサポート ・ スペシャ リストとの通信のサポート エンジニアは、分析機能の呼び出しと呼び出し品質のダッシュ ボードにアクセスするのにはこのポータルを使用できます。
    
通話分析のセットアップの詳細については、「[Skype for Business の通話分析のセットアップ](set-up-call-analytics.md)」をご覧ください。 ヘルプデスクの担当者が分析機能の呼び出しを機能させる方法の詳細については、[品質の低い呼び出しのトラブルシューティングを行うコール分析機能の使用](use-call-analytics-to-troubleshoot-poor-call-quality.md)を参照してください。
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>通話品質ダッシュボードとは何ですか? どのような場合に使用するものですか?

呼び出しの分析では、ユーザーによって発生した通話の音質に関する情報の詳細に特定できます。 ユーザー Tony Smith は午後の不適切な呼び出しを理由がでしたか。 分析機能の呼び出しを使用すると、マイクロソフトのチームまたは業務管理者またはヘルプデスクの訓練を受けたエージェントの Skype 調べることができます、デバイス、ネットワーク、接続、およびトニーの呼び出しに関連するその他の要因です。
  
通話分析が、特定の通話の品質に関する問題を管理者やヘルプデスク エージェントがトラブルシューティングできるように設計されているのに対し、通話品質ダッシュボード (CQD) は Skype for Business 管理者やネットワーク エンジニアがネットワークを最適化できるように設計されています。 CQD では特定のユーザーから焦点を外して、代わりに Skype for Business 組織全体の集計された情報について考察することになります。 
  
Tony の通話が低品質であったことは、他の数多くのユーザーにも影響を及ぼしている、ネットワークの問題がおそらく原因だと考えられます。Tony の個人的な通話経験については CQD で見ることはできませんが、Skype for Business を使用した通話の品質の全体像を把握できます。CQD では、全体のパターンが明らかに示され、ネットワーク エンジニアは確かな情報に基づく通話品質の評価を行えるようになります。CQD は通話品質の指標のレポートを提供し、全体的な通話品質、サーバーとクライアント間およびクライアント同士の間のストリーム、および音声品質の [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252) についての洞察を得られます。 
  
![Screenshot of Call Quality Dashboard in the Skype for Business Admin Center. Tabs shown are Overall Call Quality, Server - Client, Client - Client, and View Quality SLA.](media/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
詳細については、「[Skype for Business Online の通話品質ダッシュボードの機能](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD)」をご覧ください。
  
呼び出しの分析と救難が並列で実行し、個別にまたは一緒に使用することができます。 たとえば、サポート ・ スペシャ リストは、呼び出しに関する問題のトラブルシューティング ヘルプが必要があることを決定する通信があるとします。 通信のサポート担当者は、分析機能の呼び出しで通信スペシャ リストのサポートの詳細については、アクセス権を持つ通信サポート ・ エンジニアへの呼び出しを渡します。 さらに、通信のサポート ・ エンジニアは、ネットワーク ・ エンジニアの問題を警告できます。 ネットワーク エンジニア リングは、全体的なサイトに関連する問題が呼び出しに関する問題の原因の原因になる可能性があるかどう救難をチェックします。
  
救難に関する詳細について[を有効にしてマイクロソフトのチームとビジネス オンラインの Skype の品質ダッシュ ボードの呼び出しを使用して](turning-on-and-using-call-quality-dashboard.md)、[ディメンションとメジャーのマイクロソフトのチームとビジネス オンラインの Skype の品質ダッシュ ボードの呼び出しで使用可能な](dimensions-and-measures-available-in-call-quality-dashboard.md)を参照してください。
  
## <a name="related-topics"></a>関連トピック

[分析機能の呼び出しを設定します](set-up-call-analytics.md)

[通話分析を使用して低い通話品質をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[有効にして、マイクロソフトのチームと Skype のオンライン ビジネスの品質のダッシュ ボードの呼び出しを使用して](turning-on-and-using-call-quality-dashboard.md)