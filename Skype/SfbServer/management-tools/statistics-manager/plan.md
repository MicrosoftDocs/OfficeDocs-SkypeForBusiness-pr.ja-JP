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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: '概要: このトピックでは、Skype for Business Server の Statistics Manager について説明します。'
ms.openlocfilehash: cdc536abcbd1bd98c4a3c7ce974247a716865582
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821827"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>Skype for Business Server の統計情報マネージャーの計画

**概要:** このトピックでは、Skype for Business Server の Statistics Manager について説明します。

 Skype for Business Server の Statistics Manager は、Skype for Business Server の正常性とパフォーマンスのデータをリアルタイムで表示できる強力なツールです。 数秒ごとに数百のサーバーでパフォーマンス データをポーリングし、統計情報マネージャー Web サイトで即座に結果を表示できます。

Statistics Manager を使用すると、継続的なパフォーマンスの問題の特定、環境に対する計画された変更の結果の表示、停止の解決の追跡、その他の機能停止の追跡を行えます。 統計マネージャーはキー正常性インジケーター (KHI) のしきい値で構成され、展開固有のニーズに合わせてカスタマイズできます。

1 台のサーバーがすべてのサーバー側の Statistics Manager コンポーネントをホストするオンプレミス展開で Statistics Manager を展開できます。 Statistics Manager の展開の詳細については [、「Deploy Statistics Manager for Skype for Business Server」を参照してください](deploy.md)。 Statistics Manager の既存の展開があるが、リリース 2.0 にまだアップグレードしていない場合は、「リリース [2.0](plan.md#BKMK_WhatsNew) の新機能」および [「Skype for Business Server](upgrade.md)用の Statistics Manager のアップグレード」を参照してください。

このトピックは、以下のセクションで構成されています。

- [機能](plan.md#BKMK_Features)

- [リリース 2.0 の新機能](plan.md#BKMK_WhatsNew)

- [コンポーネント](plan.md#BKMK_Components)

- [オンプレミス展開](plan.md#BKMK_DeploymentOptions)

- [要件](plan.md#BKMK_Requirements)

- [セキュリティに関する検討事項](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>機能
<a name="BKMK_Features"> </a>

統計情報マネージャーでは、次の機能を使用できます。

- すべてのサーバーの生データをリアルタイムで表示します。 (データは非常に高い速度でサンプリングされ、1 秒未満で Web サイトに送信されます)。

- 特定のロールについて集計されたデータを表示する。たとえば、フロントエンド サーバー、仲介サーバー、エッジ サーバーなどです。

- ドリルダウンして、特定のサイト、サイト内の特定のプール、およびプール内の特定のサーバーのデータを表示します。

- 選択したカウンターが既定で表示されるカスタム グラフを作成します。

- x 軸と y 軸の両方、または x 軸でのみズームとパンを行います。

- データをフィルター処理するには、日付範囲またはポイントインタイムを使用します。

- 確立されたキー正常性インジケーター (KHIs) に基づいてサーバーのパフォーマンスを表示します。 KHIs は、定義された正常な範囲を持つパフォーマンス カウンターのコレクションを表します。

- 各カウンターの詳細な測定基準を表示します。

- 複数の母集団またはサーバー間でデータを比較します。

- 潜在的なカウンター レポートを表示して、現在のデータをダッシュボード サービスに報告していないエージェントを特定します。

- グラフ データの特定のインスタンスをファイルに保存します。

- 更新プログラムを含め、リアルタイムで KHIs を表示します。 履歴ビューが有効になっている場合は、新しいエラーだけが表示されます。

  - すべての KHIs を一度に表示する

  - サーバー別に KHIs を表示する (横向き表示)

  - KHI の定義を表示する

## <a name="whats-new-in-release-20"></a>リリース 2.0 の新機能
<a name="BKMK_WhatsNew"> </a>

以下では、リリース 2.0 の新機能について説明します。 Statistics Manager の既存の展開があるが、まだアップグレードしていない場合は [、Skype for Business Server](upgrade.md)の Upgrade Statistics Manager を参照してください。

- エッジ メディア、ファブリックの正常性、プールのフェールオーバーと登録のシナリオに関するシナリオ ビューが追加されました。

- 新しいカウンターの多くは、SQL Skype for Business の使用状況カウンターなどのために追加されました。

- Statistics Manager エージェントの監視ノード統合 - エージェントが監視ノードにインストールされている場合、代理トランザクション統計はカウンターとして統計情報マネージャーに報告されます。

- 信頼性とパフォーマンスの多数の向上。

実行している統計情報マネージャー Web サイトのバージョンを確認するには、次の手順を実行します。

- エクスプローラーで、C:\Program Files\Skype for Business Server StatsMan WebSite\bin を開きます (既定のディレクトリ)

- ビューを右クリックしてStatsManHubWebSite.dllプロパティを表示する

- 製品バージョンが説明の詳細に表示されます。

## <a name="components"></a>コンポーネント
<a name="BKMK_Components"> </a>

統計情報マネージャーは、次のコンポーネントで構成されます。

- **エージェント。** 監視対象の各サーバーで実行される軽量なエージェント。 エージェントを使用すると、ローカル集約を使用してパフォーマンス カウンターの構成可能な高レート ポーリングを実行できます。

- **リスナー。** すべてのエージェントからデータを受信し、母集団全体のデータを集計するサーバー側 API。

- **ハブ。** システムのクライアント API として機能し、Web サーバー上で実行され、Web サイト経由で接続されたクライアントにリアルタイムのデータ更新を提供します。 (ハブは Web サイト msi の一部として自動的にインストールされます)。

- **Web サイト。** システムで利用可能なすべての機能をまとめるユーザー インターフェイス。

さらに、Statistics Manager には、メモリ内キャッシュ用のオープン ソース データ構造サーバーである **Redis** が必要です。 Redis のダウンロードの詳細については、「Statistics Manager の展開 [」を参照してください](deploy.md#BKMK_Deploy) 。

## <a name="on-premises-deployment"></a>社内への展開
<a name="BKMK_DeploymentOptions"> </a>

オンプレミス展開では、1 台のサーバーがすべてのサーバー側の Statistics Manager コンポーネントをホストします。

次の図は、Statistics Manager Web サイト、ハブ、リスナー、および Redis キャッシュ システムが 1 台のコンピューターでホストされているオンプレミス展開を示しています。 Statistics Manager は 3 台の Skype for Business サーバーを監視しています。各サーバーには、リスナーにデータを送信する 1 つのエージェントがあります。 ユーザーは 1 つの Web サイトに接続して、統計情報マネージャーによって集計されたデータを表示します。

![Stats Manager のオンプレミス展開](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>要件
<a name="BKMK_Requirements"> </a>

Statistics Manager を展開する前に、次のソフトウェア、ネットワーク、およびハードウェアの要件を考慮する必要があります。

### <a name="software-requirements"></a>ソフトウェア要件

- Windows Server 2016 および Windows Server 2019

- IIS (自動インストール)

- Redis

- Statistics Manager サービス (自動的にインストール)

- PSExec - リモート エージェントの展開に必要

- .NET 4.5 (2012 R2 に付属) - エージェントとサーバー側コンポーネントに必要
- Skype [for Business Server、Real-Time Statistics Manager (64 ビット) をダウンロードする](https://www.microsoft.com/en-in/download/details.aspx?id=57518)

### <a name="networking-requirements"></a>ネットワークの要件


|**ホスティング サーバー**|**Agents**|**リスナー**|
|:-----|:-----|:-----|
|最小ギガビット全二重ネットワーク。  <br/> |リスナーと通信するための送信 TCP ポート 8443 (カスタマイズ可能なポート番号)。  <br/> |リスナーポートは、すべてのサーバーで同じである必要があります。  <br/> |
|Web サイトをホストするために開いている受信 TCP ポート 80 または 443。  <br/> |||
|エージェントが通信するための受信 TCP ポート 8443 (カスタマイズ可能なポート番号)。  <br/> |||

インストール時に、リスナーと Web サイトのファイアウォール ポートが自動的に作成されます。 エージェントの場合、インストールでは、既定で送信 TCP 接続が許可されている必要があります。

### <a name="hardware-requirements"></a>ハードウェア要件

1 台のサーバーがすべてのサーバー側の Statistics Manager コンポーネントをホストするオンプレミス展開では、16 GB の RAM と 4 つの CPU を持つサーバーが、平均で 1 秒あたり約 150 サンプルをサポートできる必要があります。 サポートできるカウンター/エージェントの数を確認するには、次の計算を使用します。

各エージェントから 1 分あたり 100 台のサーバー 80 カウンター 1 サンプル \* / \* 60 秒 = 1 秒あたり 133 サンプル。

## <a name="security-considerations"></a>セキュリティに関する考慮事項
<a name="BKMK_Security"> </a>

サーバー間のすべてのトラフィックが暗号化されます。

- 暗号化された HTTPS トラフィックは、(既定では) ポート 8443 を経由してエージェントからリスナー サーバーに送信されます。

- エージェントは、サーバー上の SSL 拇印を確認して、リスナー サーバーが想定される受信者である必要があります。 エージェントは(チェーン検証ではなく) 証明書の拇印検証を使用します。 自己署名証明書を使用する可能性が高いので、証明書の完全な検証は実行しません。

- エージェントが満たされた後、リスナーが認証を行った後、エージェントによってパスワードが提示され、そのパスワードがリスナーによって検証されます。

- エージェントは、接続を介してリスナーへのパフォーマンス データの送信を開始します。

## <a name="for-more-information"></a>関連情報
<a name="BKMK_Security"> </a>

詳細については、次のトピックを参照してください。

- [Skype for Business Server の Statistics Manager の展開](deploy.md)

- [Skype for Business Server の Statistics Manager のアップグレード](upgrade.md)

- [Skype for Business Server の Statistics Manager のトラブルシューティング](troubleshoot.md)
