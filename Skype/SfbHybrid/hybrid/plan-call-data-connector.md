---
title: 通話データ コネクタの計画|通話品質ダッシュボードの監視ハイブリッド分析
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: ハイブリッド シナリオでの Skype for Business Online テレメトリ ツールの使用によるオンプレミスの実装の監視の概要。
ms.openlocfilehash: f47f0969d102408299678842b18bb503eaf6aea0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110553"
---
# <a name="plan-call-data-connector"></a>通話データ コネクタの計画

## <a name="overview"></a>概要

このトピックでは、Skype for Business Server Call Data Connector を実装するための利点、計画上の考慮事項、および要件について説明します。 通話データ コネクタの構成の詳細については、「Configure Call Data [Connector」を参照してください](configure-call-data-connector.md)。


通話データ コネクタは、すべてのユーザーの通話品質を監視するために、さまざまなオンプレミスツールとオンライン ツールを使用する必要がなくなったため、ハイブリッド環境での通話監視を大幅に簡素化します。 ユーザーがオンプレミスまたはオンラインの場合は、組織全体の通話品質をオンラインで表示できます。

通話データ コネクタを使用すると、1 つのツールセットを使用して次のタスクを実行できます。

- Microsoft Teams、Skype for Business Online、Skype for Business Server 全体でユーザー エクスペリエンスを監視します。

- ネットワーク全体の問題を表示およびトラブルシューティングします。

- Call Analytics にヘルプデスクと管理者の役割を割り当て、ヘルプデスクの作業者が自分の責任領域を表示およびトラブルシューティングできます。

次の図に示すように、Skype for Business Server は通話データをクラウド サービスにプッシュして、Skype for Business Online Call Analytics (CA) ツールと通話品質ダッシュボード (CQD) ツールを活用できます。

![SfB クラウドボイスメール](../../sfbserver2019/media/call-data-connector-plan-1.png)

サーバーは、QoE (QoE) データと通話詳細記録 (CDR) データの両方をオンライン サービスにプッシュします。

Call Analytics および CQD ツールを使用すると、通話の品質を監視し、Microsoft Teams および Skype for Business サービスの接続の問題を次のようにトラブルシューティングできます。

- Call Analytics は、特定の呼び出しに関する品質の問題に焦点を当てします。 Skype for Business アカウントの各ユーザーの通話と会議に関する詳細情報を表示します。  Call Analytics を使用すると、ヘルプデスクのオペレーターにアクセス許可を割り当て、その後、Skype for Business 管理センターの残りの部分にアクセスせずに通話を監視できます。

- 品質ダッシュボードの呼び出しは、組織全体のネットワークパフォーマンスと問題に焦点を当て、 Skype for Business 管理者およびネットワーク エンジニアは、このツールを使用してネットワークパフォーマンスのトラブルシューティングと最適化を行います。

詳細については、「Call [Analytics and Call Quality Dashboard」を参照してください](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)。

もちろん、一部の通話品質データをオンプレミスに保持する必要があります。 たとえば、カスタマイズされたレポートとワークフローでサード パーティ製のソリューションを使用している場合などです。  データ コネクタの呼び出しでは、次の図に示すように、データのコピーをオンプレミス サーバーに保持しながら、オンライン サービスへのデータの送信を構成できます。

![SfB クラウドボイスメール](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>要件

次の要件では、サポートされているトポロジに Skype for Business Server が既に展開済みである必要があります。  Skype for Business Server およびサポートされるトポロジの展開の詳細については、「トポロジの基本 [」を参照してください](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md)。 通話データ コネクタを構成するには、次の手順を実行する必要があります。

- ハイブリッド接続を有効にする。 Skype for Business Server が既に展開済みで、通話データ コネクタを有効にする場合は、オンプレミス環境とオンライン環境の間にハイブリッド接続がセットアップされている必要があります。 これは、分割ドメイン構成と呼ばれる場合があります。

   詳細については、「Plan hybrid connectivity between Skype for Business Server and [Microsoft 365 or Office 365」](plan-hybrid-connectivity.md) および「Configure hybrid connectivity between Skype for Business Server and [Microsoft 365 or Office 365」](configure-hybrid-connectivity.md)を参照してください。

- Microsoft 365 または 365 組織Office認証し、次の役割を有効にしてください。

  - Skype for Business Server Administrator
  - Microsoft 365 または Office 365 グローバル管理者

- まだ実行していない場合は、「Microsoft Teams および Skype for Business Online の通話品質ダッシュボードを有効にして使用する」の説明に従って、[通話品質ダッシュボード] を [オンにしてください](/microsoftteams/turning-on-and-using-call-quality-dashboard)。

- ローカルの LCSCdr データベースと QoEMetrics データベースを使用して、監視のフロントエンド プールを有効にする。 この場合、データ コネクタの呼び出しには、使用する指標データが含まれておりかねない。

> [!IMPORTANT]
> フロントエンド プールで監視が有効になっていない場合、データ コネクタの呼び出しは機能しません。

- サーバー間 [認証が適切に構成されています](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md)。 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>オンプレミスおよびオンライン通話品質ダッシュボード (CQD) レポートの比較

| 機能レポート | Skype for Business Online | Skype for Business Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| アプリケーション共有メトリック |はい | 制限付き |
| 顧客の構築情報| はい | はい |
| ドリルダウン分析 | はい | いいえ |
| メディアの信頼性の指標 | はい | 制限付き |
| アウトオブザボックス レポート | はい | はい |
| 概要レポート | はい | いいえ |
| ユーザーごとのレポート | はい | はい |
| レポート セットのカスタマイズ <br> (レポートの追加、削除、変更) | はい | はい |
| ビデオベースの画面共有の指標 | はい | いいえ |
| プログラムによるアクセス用のデータ API <br> CQD | いいえ | はい |
||||