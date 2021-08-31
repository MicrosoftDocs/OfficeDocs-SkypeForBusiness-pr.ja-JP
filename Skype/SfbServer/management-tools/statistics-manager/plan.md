---
title: Skype for Business Server の統計情報マネージャーの計画
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: '概要: このトピックを参照して、統計マネージャーの概要をSkype for Business Server。'
ms.openlocfilehash: 2ba909e5bcc526a40374f5f9fdbbcf15c1cf7c39
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58730756"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>Skype for Business Server の統計情報マネージャーの計画

**概要:** このトピックを参照して、統計マネージャーの概要をSkype for Business Server。

 統計マネージャー for Skype for Business Serverは、正常性データとパフォーマンス データをリアルタイムSkype for Business Server表示できる強力なツールです。 数百のサーバーでパフォーマンス データを数秒ごとにポーリングし、統計マネージャー Web サイトで即座に結果を表示できます。

Statistics Manager を使用すると、継続的なパフォーマンスの問題を特定し、環境に対する計画的な変更の結果を表示し、停止の解決を追跡できます。 統計マネージャーは、キー正常性インジケーター (KHI) のしきい値で構成され、展開の固有のニーズに合わせてカスタマイズできます。

1 台のサーバーがすべてのサーバー側統計マネージャー コンポーネントをホストするオンプレミス展開に統計マネージャーを展開できます。 統計マネージャーの展開の詳細については、「Deploy [Statistics Manager for](deploy.md)Skype for Business Server」 を参照してください。 統計マネージャーの既存の展開を既に持っているが、リリース 2.0 にまだアップグレードしていない場合は、「リリース[2.0](plan.md#BKMK_WhatsNew)の新機能」および[「upgrade Statistics Manager for Skype for Business Server」を参照してください](upgrade.md)。

このトピックは、以下のセクションで構成されています。

- [機能と機能](plan.md#BKMK_Features)

- [リリース 2.0 の新機能](plan.md#BKMK_WhatsNew)

- [コンポーネント](plan.md#BKMK_Components)

- [オンプレミス展開](plan.md#BKMK_DeploymentOptions)

- [要件](plan.md#BKMK_Requirements)

- [セキュリティに関する検討事項](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>機能と機能
<a name="BKMK_Features"> </a>

統計マネージャーでは、次の機能を使用できます。

- すべてのサーバーの生データをリアルタイムで表示します。 (データは非常に高い速度でサンプリングされ、1 秒未満で Web サイトに送信されます)。

- 特定の役割に対して集計されたデータを表示する。たとえば、フロントエンド サーバー、仲介サーバー、エッジ サーバーなどです。

- ドリルダウンして、特定のサイト、サイト内の特定のプール、およびプール内の特定のサーバーのデータを表示します。

- 選択したカウンターが既定で表示されるカスタム グラフを作成します。

- x 軸と y 軸の両方、または x 軸でのみズームおよびパンします。

- データをフィルター処理するには、日付範囲または時間内のポイントを使用します。

- 確立された主要な正常性インジケーター (KHIs) に基づいてサーバーのパフォーマンスを表示します。 KHIs は、正常な範囲が定義されたパフォーマンス カウンターのコレクションを表します。

- 各カウンターの詳細な指標を表示します。

- 複数の母集団またはサーバー間でデータを比較します。

- 潜在カウンター レポートを表示して、ダッシュボード サービスに現在のデータを報告していないエージェントを特定します。

- グラフ データの特定のインスタンスをファイルに保存します。

- 更新プログラムを含め、リアルタイムで KHIs を表示します。 履歴ビューが有効になっている場合は、新しいエラーだけが表示されます。

  - すべての KHIs を一度に表示する

  - サーバー別に KHIs を表示する (横向き表示)

  - KHI 定義の表示

## <a name="whats-new-in-release-20"></a>リリース 2.0 の新機能
<a name="BKMK_WhatsNew"> </a>

次に、リリース 2.0 の新機能について説明します。 統計マネージャーの既存の展開を持ち、まだアップグレードしていない場合は、「アップグレード統計マネージャー for [Skype for Business Server」 を参照してください](upgrade.md)。

- エッジ メディア、Fabric Health、プール フェールオーバー、および登録シナリオのシナリオ ビューが追加されました。

- 多数の新しいカウンターが、SQL、Skype for Businessカウンターなどのために追加されました。

- Statistics Manager エージェントの監視ノード統合 - エージェントが監視ノードにインストールされている場合、代理トランザクション統計は統計マネージャーにカウンターとして報告されます。

- 多数の信頼性とパフォーマンスの向上。

実行中の統計マネージャー Web サイトのバージョンを確認するには、次の手順を実行します。

- エクスプローラーで開く (既定のディレクトリ) C:\Program Files\Skype for Business Server StatsMan WebSite\bin

- プロパティを右クリックStatsManHubWebSite.dllプロパティを表示する

- 製品のバージョンが [説明] の詳細に表示されます。

## <a name="components"></a>コンポーネント
<a name="BKMK_Components"> </a>

統計マネージャーは、次のコンポーネントで構成されます。

- **エージェント。** 監視対象の各サーバーで実行される軽量エージェント。 エージェントを使用すると、ローカル集約を使用してパフォーマンス カウンターの高レートポーリングを構成できます。

- **リスナー。** すべてのエージェントからデータを受信し、母集団全体でデータを集計するサーバー側 API。

- **ハブ。** システムのクライアント API として機能し、Web サーバー上で実行し、Web サイトを介して接続されたクライアントにリアルタイムのデータ更新を提供します。 (ハブは Web サイト msi の一部として自動的にインストールされます。

- **Web サイト。** システムで使用可能なすべての機能をまとめるユーザー インターフェイス。

さらに、Statistics Manager には、メモリ内キャッシュ用のオープンソースのデータ構造サーバーである **Redis** が必要です。 Redis のダウンロードの詳細については、「Deploy [Statistics Manager」を参照してください](deploy.md#BKMK_Deploy) 。

## <a name="on-premises-deployment"></a>社内への展開
<a name="BKMK_DeploymentOptions"> </a>

オンプレミスの展開では、単一のサーバーがサーバー側の Statistics Manager コンポーネントをすべてホストします。

次の図は、統計マネージャー Web サイト、ハブ、リスナー、および Redis キャッシュ システムが 1 台のコンピューターでホストされるオンプレミス展開を示しています。 Statistics Manager は、3 Skype for Businessサーバーを監視しています。各サーバーには、リスナーにデータを送信する単一のエージェントがあります。 ユーザーは単一の Web サイトに接続して、統計マネージャーによって集計されたデータを表示します。

![Stats Manager オンプレミス展開。](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>要件
<a name="BKMK_Requirements"> </a>

Statistics Manager を展開する前に、次のソフトウェア、ネットワーク、およびハードウェア要件を考慮する必要があります。

### <a name="software-requirements"></a>ソフトウェア要件

- Windows Server 2016と 2019

- IIS (自動的にインストール)

- Redis

- Statistics Manager サービス (自動的にインストール)

- PSExec - リモート エージェントの展開を実行するために必要

- .NET 4.5 (2012 R2 に付属) - エージェントおよびサーバー側コンポーネントに必須
- 統計マネージャー [Skype for Business ServerReal-Timeダウンロードする (64 ビット)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)

### <a name="networking-requirements"></a>ネットワークの要件


|**ホスティング サーバー**|**Agents**|**リスナー**|
|:-----|:-----|:-----|
|最小ギガビット全二重ネットワーク。  <br/> |リスナーと通信するための送信 TCP ポート 8443 (カスタマイズ可能なポート番号)。  <br/> |リスナー ポートは、すべてのサーバーで同じである必要があります。  <br/> |
|Web サイトをホストするために開いている受信 TCP ポート 80 または 443。  <br/> |||
|エージェントがエージェントと通信するための受信 TCP ポート 8443 (カスタマイズ可能なポート番号)。  <br/> |||

インストール時に、リスナーと Web サイトのファイアウォール ポートが自動的に作成されます。 エージェントの場合、インストールでは、既定で送信 TCP 接続が許可されている必要があります。

### <a name="hardware-requirements"></a>ハードウェア要件

1 台のサーバーがすべてのサーバー側統計マネージャー コンポーネントをホストするオンプレミス展開では、RAM が 16 GB で CPU が 4 台のサーバーで、平均で 1 秒あたり約 150 サンプルをサポートできる必要があります。 サポートできるカウンター/エージェントの数を確認するには、次の計算を使用します。

100 サーバー \* 80 カウンター \* 1 サンプル/60 秒 = ~ 133 サンプル/秒

## <a name="security-considerations"></a>セキュリティに関する考慮事項
<a name="BKMK_Security"> </a>

サーバー間のすべてのトラフィックが暗号化されます。

- 暗号化された HTTPS トラフィックは、エージェントからリスナー サーバーにポート 8443 (既定で) 経由で送信されます。

- エージェントは、サーバー上の SSL 拇印を確認して、リスナー サーバーが予想される受信者である必要があります。 エージェントは証明書の拇印検証を使用します (チェーン検証の代わりに)。 自己署名証明書を使用できるので、完全な証明書の検証は実行しません。

- エージェントが満たされた後、リスナーが本物である場合、パスワードはエージェントによって提示され、リスナーによって検証されます。

- エージェントは、接続経由でパフォーマンス データのリスナーへの送信を開始します。

## <a name="for-more-information"></a>関連情報
<a name="BKMK_Security"> </a>

詳細については、次のトピックを参照してください。

- [Skype for Business Server の Statistics Manager の展開](deploy.md)

- [Skype for Business Server の Statistics Manager のアップグレード](upgrade.md)

- [Skype for Business Server の Statistics Manager のトラブルシューティング](troubleshoot.md)
