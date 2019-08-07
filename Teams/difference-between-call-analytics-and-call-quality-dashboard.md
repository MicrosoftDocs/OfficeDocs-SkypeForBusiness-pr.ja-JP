---
title: 通話分析および通話品質ダッシュボード
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
ms.topic: conceptual
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 通話分析と通話品質ダッシュボードと、それらを使用して通話品質の問題を監視およびトラブルシューティングする場合について説明します。
ms.openlocfilehash: 535d3bf6ce2abf69143fb270e01bf4f0c2e230dc
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2019
ms.locfileid: "34433600"
---
# <a name="call-analytics-and-call-quality-dashboard"></a>通話分析および通話品質ダッシュボード

Microsoft Teams と Skype for Business では、通話品質の問題を監視してトラブルシューティングするための2つの方法が用意されています。通話分析と通話品質ダッシュボード (CQD)。 この記事では、これらの両方について説明し、どのような場合にそれぞれの方法を使用するべきかを示します。

通話分析と CQD は並列で実行され、個別に、または一緒に使うことができます。 たとえば、通話の問題のトラブルシューティングについては、コミュニケーションサポート担当者がより多くの情報が必要であると判断したとします。 通信サポートスペシャリストは、通信サポートエンジニアに通話を渡し、コミュニケーションサポートスペシャリストよりも詳細な情報にアクセスできます。 さらに、通信サポートエンジニアがネットワークエンジニアに問題を通知することができます。 ネットワークエンジニアは、CQD をチェックして、サイトに関連する全体的な問題が、通話の問題の原因になっている可能性があるかどうかを確認できます。

## <a name="whats-call-analytics-and-when-should-i-use-it"></a>通話分析とは何ですか? どのような場合に使用するものですか?

**通話分析は[Microsoft Teams 管理センター](https://admin.teams.microsoft.com)で利用できるようになりました。** すべての通話情報とユーザーのデータを表示するには、[**通話履歴**] タブを使用します。この操作を行うには、ユーザーのプロファイルページで、ダッシュボードからユーザーを検索するか、左側のナビゲーションでユーザー **** を検索します。

[通話分析] には、Microsoft Teams または Skype for Business アカウントの各ユーザーの特定の通話と会議に関連するデバイス、ネットワーク、接続に関する詳細情報が表示されます。 このユーザの通話品質が悪いのはなぜですか? Microsoft Teams と Skype for Business の通話品質と接続の問題のトラブルシューティングを行うには、通話分析を使用して、Office 365 管理者またはトレーニングされたヘルプデスクエージェントが、電話に関連するデバイス、ネットワーク、接続、その他の要因を調査します。

Microsoft Teams 管理センターでユーザーのこの情報を表示するには、[ユーザーの詳細] ページでそのユーザーの [**通話履歴**] タブをクリックして、過去30日間にユーザーが参加したすべての通話と会議を表示します。

![すべての分析ユーザーデータのスクリーンショット。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

詳細なメディアとネットワークの統計情報など、特定のセッションに関する追加情報を取得するには、セッションをクリックして詳細を表示します。

![通話分析のユーザーセッションデータのスクリーンショット。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

外部ベンダーからのヘルプデスクエージェントなど、管理者以外のユーザーが通話分析を使用できるようにする場合は、通話分析を使用できるようにアクセス許可を割り当てることができますが、Microsoft Teams 管理センターの残りの部分にはアクセスできません。 
  
- **通信がサポートされているヘルプデスクエージェント: スペシャリストの権限**: 担当者は、通話分析で一部のデータと個人情報 (PII) を確認できます。 通話のトラブルシューティングを行うことはできますが、会議の問題はコミュニケーションサポートエンジニアに渡します。
    
- **通信サポートエンジニアのアクセス許可を持つヘルプデスクエージェント**: エージェントは、通話分析で利用可能なすべてのデータを表示し、通話と会議の両方のトラブルシューティングを行います。 通話ログやユーザー情報に対するフル アクセスが付与されています。

> [!NOTE]
> 通信サポートスペシャリストの役割は、プレビューポータルでの階層1のサポートロールと同じであり、通信サポートエンジニアロールは、プレビューポータルの階層2のサポートロールと同じです。

通信サポートスペシャリストと通信サポートエンジニアロールの詳細については、「 [Microsoft teams の管理者ロールを使用してチームを管理する](using-admin-roles.md)」を参照してください。

> [!IMPORTANT]
> ヘルプデスクのエージェントの権限とネットワークトポロジのアップロードは、Microsoft Teams 管理センターで利用できます。 通信サポートスペシャリストおよび通信サポートエンジニアは、このポータルを使って通話分析と通話品質ダッシュボードにアクセスできます。
    
通話分析のセットアップの詳細については、「[Skype for Business の通話分析のセットアップ](set-up-call-analytics.md)」をご覧ください。 ヘルプデスクエージェントが通話分析を使用する方法について詳しくは、「[通話分析を使用して低品質の通話品質をトラブルシューティングする」を](use-call-analytics-to-troubleshoot-poor-call-quality.md)ご覧ください。
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>通話品質ダッシュボードとは何ですか? どのような場合に使用するものですか?
  
通話分析は管理者およびヘルプデスクエージェントが特定の通話に関する通話品質の問題を解決するために設計されていますが、通話品質ダッシュボード (CQD) は、チーム管理者、Skype for Business 管理者、ネットワークエンジニアがネットワークを最適化するために設計されています。 CQD では、特定のユーザーからフォーカスが移動され、チーム全体または Skype for Business 組織の集計情報が表示されます。 詳細については、「 [Teams および Skype For Business Online の通話品質ダッシュボードの機能](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD)」を参照してください。
  
ユーザーの通話品質の低下は、他の多くのユーザーにも影響するネットワークの問題が原因である可能性があります。 CQD には個別の通話エクスペリエンスは表示されませんが、Microsoft Teams または Skype for Business を使用して発信した通話の全体的な品質は、キャプチャされます。 CQD では、全体のパターンが明らかに示され、ネットワーク エンジニアは確かな情報に基づく通話品質の評価を行えるようになります。 CQD は通話品質の指標のレポートを提供します。これにより、全体的な通話品質、サーバークライアントストリーム、クライアントクライアントストリーム、音声品質[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)を把握できます。
  
![通話品質ダッシュボードのスクリーンショット。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

CQD の場所で強化されたレポートを使用して、問題が単一ユーザーに限定されているか、またはユーザーの大きなセグメントに影響を与えるかを判断するために、ユーザーの建物内の総通話品質と信頼性を評価できます。

![通話品質ダッシュボードの場所の拡張されたレポートのスクリーンショット。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

> [!NOTE]
> CQD での建物またはエンドポイント固有のビューを有効にするには、管理者が CQD のテナントデータアップロードページで[建物またはエンドポイントの情報をアップロード](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information)する必要があります。 

ヘルプデスクエージェントなどの非管理者が通話品質ダッシュボードを使用できるようにするには、これらのユーザーに**Teams Communications Support エンジニア**、 **Teams コミュニケーションサポートスペシャリスト**、または**レポート閲覧**者の役割を割り当てることができます。 次の役割を持つユーザーは、通話品質ダッシュボードにアクセスできます。

- グローバル管理者
- グローバルリーダー
- Skype for Business 管理者
- Teams サービス管理者
- Teams 通信管理者
- Teams 通信サポート エンジニア
- Teams 通信サポート スペシャリスト
- レポートリーダー

> [!NOTE]
> Teams 通信サポートエンジニア、Teams 通信サポートスペシャリスト、およびレポートリーダーの役割は、CQD のテナントデータアップロードページ上のファイルを変更したり、テナントの CQD をアクティブ化したりすることはできません。

これらの役割の詳細については、「 [Office 365 管理者ロールについ](/office365/admin/add-users/about-admin-roles)て」を参照してください。

CQD の詳細については、「 [Microsoft teams および skype For Business online の通話品質ダッシュボードをオンにして使用する](turning-on-and-using-call-quality-dashboard.md)」と「 [Microsoft teams および Skype for Business Online の通話品質ダッシュボードで利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)」を参照してください。
  
## <a name="related-topics"></a>関連トピック

[ビデオ: 通話品質の概要](https://aka.ms/teams-quality)

[通話分析をセットアップする](set-up-call-analytics.md)

[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Microsoft Teams および Skype for Business Online で通話品質ダッシュボードをオンにして使用する](turning-on-and-using-call-quality-dashboard.md)
