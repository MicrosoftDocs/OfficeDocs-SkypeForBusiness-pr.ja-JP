---
title: 通話データコネクタを計画する |通話品質ダッシュボードのハイブリッド分析の監視
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Skype for Business Online テレメトリツールを使用した、ハイブリッドシナリオでのオンプレミスの実装の監視の概要。
ms.openlocfilehash: dc129ed99e1ed69e3faf5d2a7b6923f818c482eb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160655"
---
# <a name="plan-call-data-connector"></a>通話データコネクタを計画する

## <a name="overview"></a>概要

このトピックでは、Skype for Business Server Call Data Connector を実装する場合の利点、計画に関する考慮事項、および要件について説明します。 通話データコネクタの構成の詳細については、「 [Configure Call Data connector](configure-call-data-connector.md)」を参照してください。

> [!NOTE]
> パブリックプレビューリリースでは、通話分析のダッシュボードのみを使用できます。

通話データコネクタを使用すると、ユーザーの通話品質をすべて監視するためにオンプレミスとオンラインツールの異なるセットを使用する必要がなくなるため、ハイブリッド環境での通話監視が大幅に簡素化されます。 ユーザーがオンプレミスまたはオンラインに所属しているかどうかにかかわらず、組織全体の通話品質をオンラインで表示するように選択できます。

Call Data Connector を使用すると、1つのツールセットを使用して次のタスクを実行できます。

- Microsoft Teams、Skype for Business Online、Skype for Business Server でのユーザーの作業状況を監視します。

- ネットワーク全体の問題を表示し、トラブルシューティングを行います。

- ヘルプデスクおよび管理者の役割を呼び出し分析に割り当てて、ヘルプデスクの作業者が自分の責任範囲を表示およびトラブルシューティングできるようにします。

通話データコネクタを使用すると、Skype for business Server は、次の図に示すように、Skype for Business Online Call Analytics (CA) と通話品質ダッシュボード (CQD) ツールを利用できるように、クラウドサービスに呼び出しデータをプッシュします。

![SfB クラウドボイスメール](../../sfbserver2019/media/call-data-connector-plan-1.png)

サーバーは、QoE (Quality of Experience) データと通話詳細記録 (CDR) データの両方をオンラインサービスにプッシュします。

Call Analytics and CQD tools を使用すると、次のように、通話の品質を監視し、Microsoft Teams および Skype for Business サービスとの接続の問題のトラブルシューティングを行うことができます。

- 通話分析は、特定の通話の品質の問題に焦点を当てます。 ここには、Skype for Business アカウントの各ユーザーの通話と会議に関する詳細な情報が表示されます。  通話分析を使用すると、ヘルプデスクオペレーターにアクセス許可を割り当てることができます。これにより、他の Skype for Business 管理センターにアクセスすることなく、通話を監視することができます。

- 通話品質ダッシュボードは、組織全体のネットワークパフォーマンスと問題に重点を置いています。 Skype for Business 管理者とネットワークエンジニアは、このツールを使用して、ネットワークパフォーマンスのトラブルシューティングと最適化を行います。

詳細については、「[通話分析と通話品質ダッシュボード](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)」を参照してください。

もちろん、一部の通話品質データをオンプレミスで保持することをお勧めします。 これは、たとえば、カスタマイズされたレポートとワークフローを使用してサードパーティ製のソリューションを使用している場合などに該当します。  Call Data Connector を使用すると、次の図に示すように、オンプレミスサーバーにデータのコピーを保持しながら、オンラインサービスへのデータ送信を構成することができます。

![SfB クラウドボイスメール](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>要件

次の要件は、サポートされているトポロジで Skype for Business Server を既に展開していることを前提としています。  Skype for Business Server およびサポートされているトポロジの展開の詳細については、「[トポロジの基本](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics)」を参照してください。 通話データコネクタを構成するには、次のことを行う必要があります。

- ハイブリッド接続を有効にします。 Skype for Business Server を既に展開している場合に、通話データコネクタを有効にするには、オンプレミスの環境とオンライン環境の間でハイブリッド接続が設定されていることを確認する必要があります。 これは、分割ドメイン構成と呼ばれることがあります。

   詳細については、「skype for business [server と office 365 の間のハイブリッド接続を計画](plan-hybrid-connectivity.md)する」および「 [Skype for Business server と office 365 の間のハイブリッド接続を構成する](configure-hybrid-connectivity.md)」を参照してください。

- Office 365 テナントに対して認証を行い、次の役割が有効になっていることを確認します。

  - Skype for Business Server 管理者
  - Office 365 グローバル管理者

- まだ行っていない場合は、 [Microsoft Teams および Skype For Business Online の通話品質ダッシュボードの有効化と使用](/microsoftteams/turning-on-and-using-call-quality-dashboard)に関する説明に従って、通話品質ダッシュボードを有効にします。

- ローカルの LCSCdr および QoEMetrics データベースを使用して、監視用のフロントエンドプールを有効にします。 この操作を行わないと、呼び出しデータコネクタは、使用する指標データを持っていません。

> [!IMPORTANT]
> フロントエンドプールで監視が有効になっていない場合、Call Data Connector は機能しません。

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>オンプレミスとオンライン通話品質ダッシュボード (CQD) レポートの比較

| 機能レポート | Skype for Business Online | Skype for Business Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| アプリケーション共有メトリック |はい | いう |
| 顧客の建物情報| はい | はい |
| ドリルダウン分析 | はい | いいえ |
| メディアの信頼性の指標 | はい | いう |
| すぐに使えるレポート | はい | はい |
| 概要レポート | はい | いいえ |
| ユーザーごとのレポート | はい | はい |
| レポートセットのカスタマイズ <br> (レポートの追加、削除、変更) | はい | はい |
| ビデオベースの画面共有指標 | はい | いいえ |
| プログラムによるアクセス用のデータ Api <br> CQD | いいえ | はい |
||||
