---
title: Skype for Business Server 2015 リソース キット ツールのドキュメント
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/20/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: このトピックでは、各ツール、およびその使用方法の例の目的を含む、ビジネス サーバー 2015 リソース キットの Skype では、ツールについて説明します。 ビジネス 2015 リソース キットの Skype は、展開およびビジネス サーバー 2015 の Skype を管理する IT 管理者の日常的なタスクを容易に役立ちます。 たとえば、Web Conf Data ツールを使用すると、オンライン会議中にユーザーによってアップロードされたデータを簡単に制御できます。 SEFAUtil ツールを使用すると、ユーザーの問い合わせに対して自動転送や自動応答を設定できます。 IT 管理者は、ビジネス サーバー 2015 の Skype をより効果的に管理するためにこれらのツールを使用することをお勧めします。
ms.openlocfilehash: e6ff130d403c83a898c2598dc9971079cb912d56
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906628"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a>Skype for Business Server 2015 リソース キット ツールのドキュメント

このトピックでは、各ツール、およびその使用方法の例の目的を含む、ビジネス サーバー 2015 リソース キットの Skype では、ツールについて説明します。 ビジネス 2015 リソース キットの Skype は、展開およびビジネス サーバー 2015 の Skype を管理する IT 管理者の日常的なタスクを容易に役立ちます。 たとえば、**Web Conf Data** ツールを使用すると、オンライン会議中にユーザーによってアップロードされたデータを簡単に制御できます。 **SEFAUtil** ツールを使用すると、ユーザーの問い合わせに対して自動転送や自動応答を設定できます。 IT 管理者は、ビジネス サーバー 2015 の Skype をより効果的に管理するためにこれらのツールを使用することをお勧めします。

## <a name="installation-of-the-resource-kit-tools"></a>リソース キット ツールのインストール

ビジネス 2015 リソース キットは、Skype をインストールするには、ダウンロード センターから[OCSReskit.msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631)をダウンロードします。

**OCSResKit.msi** を実行すると、簡易インストールが行われます。.msi によって、**%Program Files%\Skype for Business Server 2015\ResKit** のパスにすべてのツールがインストールされます。このフォルダーには、自己完結型のツールの実行可能ファイルが格納されます。各ツールのサポート ファイルは、それぞれのサブフォルダーに格納されます。

## <a name="supported-environments"></a>サポートされる環境

ビジネス 2015 リソース キットの Skype は、Skype ビジネス サーバー 2015、通常 1 つのビジネス サーバー 2015 の Skype を実行に使用するのに必要な要件を満たすサーバーにインストールしてください。

## <a name="resource-kit-tools-overview"></a>リソース キット ツールの概要

ビジネス 2015 リソース キットは、Skype で提供されているツールの一覧を次に示します。 各ツールの要件や使用例については、以下のセクションで説明します。

- [ABSConfig](resource-kit-tools.md#ABSConfig)

- [Bandwidth Policy Service Monitor](resource-kit-tools.md#bpsm)

- [Bandwidth Utilization Analyzer](resource-kit-tools.md#bua)

- [Call Parkometer](resource-kit-tools.md#callpark)

- [DBAnalyze](resource-kit-tools.md#dba)

- [Import Storage Service Data](resource-kit-tools.md#Issd)

- [LCSSync](resource-kit-tools.md#LCSSync)

- [Lookup User Console](resource-kit-tools.md#LUC)

- [MsTurnPing](resource-kit-tools.md#MsTurnPing)

- [Network Configuration Viewer](resource-kit-tools.md#NCV)

- [Response Group Agent Live](resource-kit-tools.md#RGAL)

- [SEFAUtil](resource-kit-tools.md#SEFAUtil)

- [SYSPrep.ps1](resource-kit-tools.md#SYSPrep)

- [Unassigned Number Announcements Migration](resource-kit-tools.md#UNAM)

- [Web Conf Data](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a>ABSConfig
<a name="ABSConfig"> </a>

アドレス帳サービスの構成ツール (ABSConfig) は、ビジネス サーバー 2015 の Skype のアドレス帳サービスの構成をカスタマイズする管理者を支援する管理ツールです。 このツールでは、既定のアドレス帳サービスの設定を復元するサーバー 2015 のビジネス管理者のための Skype も使用できます。

### <a name="description"></a>説明

ABSConfig は、アドレス帳サービスに関連する属性を Active Directory ドメイン サービスを構成する管理者を有効にするグラフィカル ユーザー インターフェイス アプリケーションです。

このツールを使用する主なシナリオは、次のとおりです。

- ビジネス サーバー 2015 の Skype の Active Directory ドメイン サービス内の属性を属性にマップするのには管理者を有効にします。

- 管理者が Active Directory ドメイン サービスの属性をアドレス帳サービスのファイルに含めるか、ファイルから除外できるようにする。

- 管理者がアドレス帳サービスの既定の設定を復元できるようにする。

ABSConfig ツールは、absConfig.exe ファイルから起動できます。 ツールは、[**属性の構成**] タブを開きます。このテーブルには、ビジネス サーバー 2015 の Skype の Active Directory ドメイン サービスの属性を属性フィールドにマップしてフィルターの特定の属性に基づいてアドレス帳サービスのファイルに含めたり除外したりできるユーザーを指定するオプションがあります。 また、アドレス帳ファイルに含める電話番号の値をカスタマイズできます。 [**Restore Defaults**] オプションを使用すると、アドレス帳サービスの設定を既定の値に復元できます。

> [!NOTE]
> OC フィールド名を別の AD 属性の再マッピングして、アドレス帳ファイルをダウンロードするための作業だけでは、アドレス帳 Web クエリではサポートされていません。

### <a name="output"></a>出力

ABSConfig は、アドレス帳サービスの構成をデータベースに格納します。

```
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a>用途

ABSConfig は、ビジネス サーバー 2015 のアドレス帳サービスの Skype をカスタマイズするのには迅速で簡単な方法を提供します。

### <a name="requirements"></a>要件

#### <a name="computer"></a>コンピューター

ABSConfig は、Skype をビジネス サーバー 2015 がインストールされているのドメインに参加しているコンピューターからのみ実行できます。 ビジネス サーバー 2015、Enterprise Edition の場合は、Skype の場合は、セットアップ中に有効なアドレス帳サービスを使用するフロント エンド サーバーでこのツールを実行できます。

#### <a name="network"></a>ネットワーク

コンピューターは、フロントエンド プールとバックエンド データベースに接続できる必要があります。

#### <a name="software"></a>ソフトウェア

ABSConfig ツールを実行する前に、次のソフトウェア コンポーネントをインストールしておく必要があります。

- Skype for Business Server 2015

#### <a name="users"></a>ユーザー

サーバー 2015 のビジネス展開に Skype を更新するために必要なアクセス許可を持つ管理者。

### <a name="examples"></a>例

ABSConfig は、コマンド プロンプトで **ABSConfig.exe** と入力して起動することができます。ABSConfig ツールのユーザー インターフェイスを以下に示します。

![ABSConfig.exe ツール](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a>概要

ABSConfig ツールは、ビジネス サーバー 2015 のアドレス帳サービスの Skype をカスタマイズするのには短時間で使いやすいツールを管理者に提供します。

## <a name="bandwidth-policy-service-monitor"></a>Bandwidth Policy Service Monitor
<a name="bpsm"> </a>

Bandwidth Policy Service Monitor ツールを使用すると、管理者は以下のリストを表示することができます。

1. ビジネス サーバー 2015 の帯域幅ポリシー サービス (認証とコア) トポロジで構成されているすべての Skype

2. 各サービスの帯域幅ポリシー サービスとエッジ サーバーへの接続状況

3. ネットワーク構成ドキュメントで構成されたすべてのリンクと、各帯域幅ポリシー サービスから報告されたリアルタイムの帯域幅の使用状況

### <a name="description"></a>説明

Bandwidth Policy Service Monitor ツールは、GUI ベースのアプリケーションとして実装されています。管理者は、PDPMonUI.exe を実行してツールを起動します。

ツールを起動すると、ツールはトポロジ内の帯域幅ポリシー サービスの一覧を検索します。初期アップデートが完了すると、ウィンドウの左ペインに、所属するクラスターによってグループ分けされたサービスの一覧が表示されます。

管理者が特定の帯域幅ポリシー サービスを選ぶと、右ペインにそのサービスの情報が表示されます。次の 2 つのメイン タブにそれぞれ情報が表示されます。

#### <a name="machine-info-tab"></a>[Machine Info] タブ

[**Machine Info**] タブには、選択した帯域幅ポリシー サービスの詳細と、選択した帯域幅ポリシー サービスから別のサービスへの接続の一覧と状態が表示されます。

#### <a name="topology-info-tab"></a>[Topology Info] タブ

[**Topology Info**] タブには、ネットワーク構成設定で構成されたすべてのリンクの一覧が表示されます。各リンクには、音声とビデオの帯域幅容量が表示されます。さらに、現在使用されている帯域幅が、Kbps と容量に対する割合で表示されます。ツールでは色分けが使用され、容量の上限に近づいているリンクが強調表示されます。これにより、管理者は対象のリンクをすばやく分離できます。

> [!NOTE]
>  場合は、帯域幅ポリシー サービス監視ツールに障害が発生したは、構成されている帯域幅ポリシー サービスのいずれかに接続するとき、**マシン情報**および**トポロジー情報**のタブ内の情報を設定しません。 ただし、最初は接続されたにもかかわらず、後にサービスへの接続が途切れることもあります。 このような場合、管理者に古い情報が表示されることがあります。 各タブには [**Last Updated**] タイムスタンプが用意されているため、管理者は特定の帯域幅ポリシー サービスのデータが最後に更新された時間を確認できます。

### <a name="output"></a>出力

コマンドラインの出力はありません。プログラムの出力は、メインのグラフィカル ユーザー インターフェイス (GUI) に含まれています。

### <a name="purpose"></a>用途

Bandwidth Policy Service Monitor ツールを使用すると、管理者はトポロジに定義された各帯域幅ポリシー サービスの詳細を確認できます。さらに、管理者はネットワーク構成ドキュメントに定義されたすべてのリンクの帯域幅の使用状況を、リアルタイムで確認できます。

### <a name="requirements"></a>要件

帯域幅ポリシー サービス監視ツールは、ビジネスのサーバー トポロジの Skype の一部であるコンピューター上で実行する必要があります。

### <a name="summary"></a>概要

Bandwidth Policy Service Monitor ツールを使用すると、トポロジ内の帯域幅ポリシー サービスの状態を確認できます。さらに、ネットワーク構成設定で定義されたリンクの帯域幅のリアルタイムの使用状況を把握できるため、管理者にとって非常に重要なリソースです。

## <a name="bandwidth-utilization-analyzer"></a>Bandwidth Utilization Analyzer
<a name="bua"> </a>

Bandwidth Utilization Analyzer は、エンタープライズ ネットワークの WAN リンク全体の UC エンドポイントで消費される帯域幅を、さまざまな観点から確認できるレポートを作成するツールです。これらのレポートを使用すると、現在の帯域幅の消費パターンを把握して、帯域幅の容量計画に活用できます。

### <a name="description"></a>説明

Bandwidth Utilization Analyzer は、GUI ベースのアプリケーションとして実装されます。このツールは、ネットワーク全体音声に限定した使用状況に関するレポートを作成し、容量の計画に活用できます。また、さまざまなリンクに割り当てられた帯域幅容量を反復処理します。

### <a name="output"></a>出力

Bandwidth Utilization Analyzer には、システムで構成されたすべての WAN リンクにおける、音声の帯域幅容量と使用状況に関するグラフィカル プロットが用意されています。

### <a name="purpose"></a>用途

任意の音声とビデオの展開では、監視し、企業ネットワーク全体でメディア トラフィックの帯域幅使用率の傾向を理解するが重要です。 Bandwidth Utilization Analyzer ツールを使用すると、管理者はそれを把握できます。 このツールでは、次の操作を実行できます。

- ネットワーク全体にわたる音声の使用状況に関するレポートを生成する

- より効果的な容量計画の立案と、さまざまなリンクに割り当てられた帯域幅容量の反復処理をサポートする

Bandwidth Utilization Analyzer では、帯域幅容量のグラフィカル プロットと使用状況レポートを作成できます。その範囲と実行可能な操作は次のとおりです。

- エンタープライズ ネットワーク内のすべての WAN リンク

- 事前に指定した WAN リンクでフィルター処理

- リンク容量を超過した WAN リンクでフィルター処理

- 帯域幅の使用率が予測を下回る WAN リンクでフィルター処理

- 重大レベル (WAN リンクの帯域幅使用率が容量の 90% を超過している) に達している WAN リンクでフィルター処理

- WAN リンクの種類 (ネットワーク サイト リンク、地域間リンク、サイト内リンク) でフィルター処理

- ネットワーク地域でフィルター処理

#### <a name="applications"></a>アプリケーション

Bandwidth Utilization Analyzer には、次の 2 つのアプリケーション (ツール) が用意されています。

- **WanLinkLogCollector.exe**このツールは、必要な情報を入力するには、そのユーザーを使用します。

- **BandwidthUtilizationAnalyzer.xlsm** WanLinkLogCollector.exe で A Microsoft Excel スプレッドシート ソフトウェア レポートが自動的に起動されます。 このアプリケーションでは、レポートにフィルターを適用できます (この記事の後半で説明します)。

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a>Bandwidth Utilization Analyzer の使用フェーズ

Bandwidth Utilization Analyzer の使用は、次の 2 つのフェーズに分けられます。

- ログの収集 (WanLinkLogCollector.exe を使用)

- レポートのカスタマイズ (BandwidthUtilizationAnalyzer.xlsm を使用)

> [!IMPORTANT]
> BandwidthUtilizationAnalyzer.xlsm はエンド ユーザーが手動で起動できないようにすることを強くお勧めします。

#### <a name="starting-bandwidth-utilization-analyzer"></a>Bandwidth Utilization Analyzer の起動

コマンド プロンプトで WanLinkLogCollector.exe を実行するか、Windows エクスプローラーを使用して起動します。

 **WanLinkLogCollector.exe の使用**

WanLinkLogCollector.exe を使用するには、次の 3 つの手順を実行します。

1. **タイムラインのログ**レポートを生成する必要があるタイムラインを提供します。

2. **ファイルのディレクトリを指定します。** ファイルの場所に関する情報を提供します。

3. **ログを収集しレポート ビューアーを起動します。** レポートを生成するコマンドを実行します。

#### <a name="step-1---log-the-timeline"></a>手順 1 - ログのタイムラインを指定する

タイムラインのログを記録するには、以下の図に示すように、次の項目を指定します。

1. **Start date** レポートを生成するタイムラインの開始日 (例: 2010 年 8 月 1 日)。

2. **End date** レポートを生成するタイムラインの終了日 (例: 2010 年 9 月 30 日)。

     ![Bandwidth Utilization Analyzer の開始日/終了日](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a>手順 2 - ファイルのディレクトリを指定する

図に示すように、以下のファイル ディレクトリを指定することができます。

- **サーバー ログ ファイルの場所**帯域幅ポリシー サーバーのログが保存されているフォルダーの場所。 これは、通常の\<ファイル ・ サーバ\>\\FE の <choice\>\AppServerFiles\PDP。

- **一時ファイルの格納場所**レポートの中に中間ファイルが格納される一時ファイルの場所を生成しています。

![Bandwidth Utilization Analyzer のファイル ディレクトリ](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

> [!NOTE]
> サーバー ログや一時ファイルを格納するフォルダーにアクセスできる十分な権限をツールのユーザーに割り当てるようにしてください。

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>手順 3 - ログを収集してレポート ビューアーを起動する

ログを収集してレポート ビューアーを起動するには、以下の図に示す [**Execute**] をクリックします。この手順により、必要なデータが収集されます。

![Bandwidth Utilization Analyzer でのデータの収集](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

入力の検証が正常に行われると、以下のメッセージが表示されます。

![BandwidthUtilizationAnalyzer でログに収集された通知](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

[**OK **] をクリックします。BandwidthUtilizationAnalyzer.xlsm は自動的に起動します。メッセージ ボックスの指示に従います。詳細については、次のセクション「**BandwidthUtilizationAnalyzer.xlsm の使用**」を参照してください。


### <a name="using-bandwidthutilizationanalyzerxlsm"></a>BandwidthUtilizationAnalyzer.xlsm の使用

1. BandwidthUtilizationAnalyzer.xlsm が自動的に起動したら、以下の図に示す [**Refresh**] をクリックします。

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. ファイルのフォルダーが開いたら、メッセージ ボックスで指定した場所にある consolidated.csv を選びます。以下に示すように、場所は **C:\Temp** です。

     ![BandwidthUtilizationAnalyzer でフォルダーを開く](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. [**Import**] をクリックします。

4. グラフィカル プロットが自動的に生成されます。バックグラウンドで作業中のポインターが表示されなくなると、使用できます。

     ![レポート ビューでのフィルターの適用](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a>レポート ビューにフィルターを適用する

レポート ビューに適用できるフィルター (以下の図を参照) は、次のとおりです。

![レポート ビューでのフィルターの適用](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. **Name** WAN リンクでフィルター処理 (グラフの右側のフィルター)。プレフィックス (縦長の青いボックスを参照) は、次のようなリンクの種類を示します。

   - **S: Site** ネットワーク サイトからネットワーク地域への WAN リンク

   - **IS Inter-Site** 2 つのネットワーク サイト間の WAN リンク

   - **R Inter-Region** 2 つのネットワーク地域間の WAN リンク

2. **Exceeded limit** 帯域幅の使用率が帯域幅容量を超過している WAN リンクでフィルター処理

3. **Critical levels** 帯域幅の使用率が帯域幅容量の 90% 以上に達した WAN リンクでフィルター処理

4. **Under-utilized** 帯域幅の使用率が帯域幅容量の 25% に達していない WAN リンクでフィルター処理

5. **Link type** 次に示す WAN リンクの種類でフィルター処理します。

   - **Network site** タイプ

   - **Inter-site** タイプ

   - **Inter-Region link** タイプ

6. **Region** ネットワーク地域でフィルター処理

次の図は、これまでに紹介したフィルターを示します。

[**Name**] でフィルター処理します。グラフに表示するリンクのリストを選びます。

![BandwidthUtilizationAnalyzer での [Name] でのフィルター処理](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

[**Exceeded limit**] でフィルター処理します。 フィルターを適用するには、[**True**] を選びます。

![[Exceeded Limit] でのフィルター処理](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

[**Critical levels **] でフィルター処理します。 フィルターを適用するには、[**TRUE **] を選びます。

![[Critical Levels] でのフィルター処理](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

[**Under-utilized **] でフィルター処理します。 フィルターを適用するには、[**TRUE **] を選びます。

![[Under Utilized] でのフィルター処理](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

[**Link Type**] でフィルター処理します。 表示する種類を 1 つ以上選びます。

![[Link Type] でのフィルター処理](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

[**Region**] でフィルター処理します。 リンクを表示する地域のリストを選びます。

![[Region] でのフィルター処理](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a>要件

- .NET Framework 3.5

- Microsoft Excel 2010 または Excel 2007

### <a name="summary"></a>概要

Bandwidth Utilization Analyzer は、ネットワーク全体の UC トラフィックにおける音声の帯域幅の使用状況をプロットするために使用します。このツールは、ビデオの帯域幅の使用状況を報告する場合にも同様に使用できます。

## <a name="call-parkometer"></a>Call Parkometer
<a name="callpark"> </a>

Call Parkometer は、コール パーク オービット デバイスに簡単にアクセスできるコマンドライン アプリケーションです。

### <a name="description"></a>説明

Call Parkometer は、現在パークされている通話を追跡するツールです。 オービットやコール パーク サーバー (CPS) の使用状況に関する統計情報も収集します。 このコマンド ライン ツールは読み取りと書き込みアクセスの両方をローカルまたはリモートで接続されたコンピューターから CPS 回り込み SQL Server データベースに提供します。

すべてのオプションは同時に使用できません。 コマンドライン構文は次のとおりです。

- パラメーター**と-o**パラメーター、このプールに対して構成されている範囲をオービットのすべてのリストです。

- **-n**パラメーター: このプールに軌道を使用しているすべてのリストです。 情報は次のように表示されます。

  - パーク元とパーク先の SIP Uniform Resource Identifier (URI)。

  - 通話のパーク先の CPS のホスト名。

  - 通話がパークされた時点のタイムスタンプ。

- **-f**パラメーター-プール内の現在の空きの軌道の数を一覧表示します。

- **-r \<n\>** パラメーターなどの一覧が表示、 \<n\>最後の呼び出しを保持します。 情報は次のように表示されます。

  - パーク先の SIP URI。

  - パーク元の SIP URI。

  - 通話のパーク先の CPS のホスト名。

  - 通話が保留解除または切断された時点のタイムスタンプ。

- **-t\<n\>** パラメーターのテストを軌道が割り当てられている番号のランダム性を表示するのにはデータベースの軌道を確保します。

### <a name="output"></a>出力

コマンド プロンプトで指定された入力パラメーターによっては、Call Parkometer に次の出力が表示されます。

- このプールで構成されたすべてのオービット範囲

- 現在パークされている通話

- 有効な (使用可能な) オービットの数

- 最近パークされた通話

- 一定およびランダムなオービットの値をテストするために予約されたオービット

### <a name="purpose"></a>用途

CPS ツールを使用すると、CPS データベースへのコマンドライン アクセスを確立できます。管理者は、CPS の使用状況を確認して、プールに割り当てられているオービットの数を把握できます。

### <a name="requirements"></a>要件

CPS が実行されている同じコンピューターで実行する場合、このツールの使用に必要な条件はありません。 このツールがリモート コンピューターで実行する場合は、リモート アクセスを許可するビジネス サーバー 2015 Skype で使用する SQL Server データベースを構成しなければなりません。 Parkometer の呼び出しは、プールの SQL Server に接続する SQL Server データベースの接続文字列で構成しなければなりません。 この SQL Server データベースの接続文字列は、 **parkometer.exe.config**の構成ファイルで定義されます。置く必要がある同じディレクトリに parkometer.exe が置かれています。 次の XML ファイルは、parkometer.exe.config の例です。構成する必要があるパラメーターには、ユーザー名 (たとえば、mydomain\Administrator)、パスワード (たとえば、mypassword)、およびホスト名 (たとえば、myserver) がいます。

```
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <appSettings>
   <add key="SQL" value="server=myserver\RTC;
database=cpsdyn;
User Id=mydomain\Administrator;
Password=mypassword.;
Integrated Security=false;"/>
  </appSettings>
</configuration>
```

### <a name="examples"></a>例

軌道の範囲の展開:-o パラメーターの一覧のように、このプールに対して構成されているすべての軌道の範囲

![Call Parkometer のオービット範囲](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

現在の呼び出しを保持: のように、-n のパラメーターがこのプールで現在使用されているすべての軌道を一覧表示

![Call Parkometer で現在保留されている通話](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

自由軌道の数:-f パラメーターのように、プール内の現在の空きの軌道の数を一覧表示

![Call Parkometer の使用されていないオービット](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

最近の呼び出しを保持:-r \<n\>パラメーターのリスト、 \<n\>のように、最後の呼び出しを駐機しています。

![Call Parkometer で最近保留された通話](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

軌道予約のテスト:-t \<n\>パラメーターのテストのようにデータベースの軌道を予約します。

![Call Parkometer のオービット予約のテスト](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a>概要

Call Parkometer は、コール パーク サーバーに関する詳しい情報を提供するコマンドライン ツールです。

## <a name="dbanalyze"></a>DBAnalyze
<a name="dba"> </a>

### <a name="description"></a>説明

DBAnalyze は、データベースのビジネス サーバー 2015 Skype に関する分析レポートを収集するために管理者に役立つコマンド ライン ツールです。 DBAnalyze には、診断モード、ユーザー データ モード、会議モード、MCU モード、ディスク断片化モードが用意されています。

- **診断モード**テーブル (レコード、断片化、データ サイズ、およびインデックスのサイズの数)、データとログ ファイルのサイズ、最後のバックアップに、Microsoft Office Communications Server を実行しているサーバー間での連絡先の配布に関する情報を含むレポートを作成しますユーザー、会議のスケジュール設定された、アクティブな会議は、アクセス許可、連絡先、コンテナー、サブスクリプション、パブリケーション、エンドポイント ユーザー、不適切なホーム ユーザー、ルーティングすることはできませんが、ユーザーごとの平均数は、会議の平均数の構成データベース バージョンを選択します。

    > [!NOTE]
    > 診断モードを実行すると、サーバーのパフォーマンスに影響を与えることがあります。

- **ユーザー データ モード**レポート連絡先、コンテナー、サブスクリプション、パブリケーション、アクセス許可、および連絡先グループのデータや、連絡先とアクセス許可の一覧にそのユーザーを持つユーザーに対して、指定したユーザーです。 このモードでは、ユーザーの編成またはに招待された会議の要約データをレポートします。

- **会議モード**Mcu (マルチポイント コントロール ユニット)、アクティブな参加者のリスト、および各会議、作業中の会議、出席者リスト、メディアの種類の一覧のすべてのスケジュールに詳細を含む、特定の会議のレポートの詳細なデータが許可されます。参加者の信号の状態です。

- **ミーティング ID をデコードします。** ミーティングの ID を **/pstnid**スイッチで指定されていますが、詳細については、バック エンドに接続していない公衆交換電話網 (PSTN) をデコードします。

- **会議を解決するには****/Pstnid**スイッチで指定された ID で示されている会議についての情報を表示する PSTN 会議 ID をデコードします。

- **Mcu モード**プール内の各 MCU の ID、メディアの種類、URL、ハートビートの状態、会議の負荷、および参加者の負荷を報告します。

- **ディスクの断片化のモード**すべてのディスクの断片化の状態を表示します。

このツールは、さまざまな問題を診断し、管理者の容量計画を支援するために使用できます。たとえば、サーバー A に所属する大多数のユーザーが、サーバー B に所属するユーザーを連絡先として選択した場合、管理者はサーバー A のユーザーをサーバー B に移動して、サーバー間のトラフィックを削減できます。

### <a name="output"></a>出力

このツールは、ビジネス サーバー 2015 データベースの Skype に関する定義済みのレポートを出力します。 **パス**: %ProgramFiles%\Skype for Business Server 2015\Reskit

### <a name="purpose"></a>用途

Dbanalyze.exe をインストールするには、ローカル フォルダーにコピーし、ツールを実行します。 ツールを使用するには、コマンド ・ ラインから次のコマンドを実行します。 `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`コマンド ライン オプションの説明を以下に示します。

![Dbanalyze.exe のコマンド ライン オプション](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a>要件

 **コンピューター**DBAnalyze は、ビジネス サーバー 2015 がインストールされている Skype が含まれるドメインに参加しているコンピューターからのみ実行できます。

 **ネットワーク** コンピューターは、バックエンド データベースに接続できる必要があります。

 **ソフトウェア**Skype ビジネス サーバー 2015 ソフトウェア ・ コンポーネントは、DBAnalyze を実行する前にインストールしなければなりません。

 **ユーザー**Skype ビジネス サーバー 2015 のデータベースにアクセスするために必要なアクセス許可があるユーザー、管理者を次の表に示します。

![Dbanalyze.exe の権限のテーブル](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> **/report:disk** モードでは、ローカル管理者のアカウントが必要です。

### <a name="examples"></a>例

次に、有効な Dbanalyze.exe コマンドの例を示します。

```
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a>概要

DBAnalyzer には、クイックと Skype をビジネス サーバー 2015 データベースの分析を簡単に、管理者が用意されています。

## <a name="import-storage-service-data"></a>Import Storage Service Data
<a name="Issd"> </a>

ImportStorageServiceData リソース キット ツールを使用すると、Storage Service (LYSS) からフラッシュされたキューやエンドポイントのデータを、ストレージ サービスに再インポートできます。

### <a name="description"></a>説明

Storage Service からのデータのフラッシュは、キュー アイテムの状態やデータベースのサイズに基づいて自動的 (定期的) に行われた可能性があります。 また、プール フェールオーバー コマンドレット、またはそれによって呼び出される StorageServiceFullFlush コマンドレットの手動呼び出しによって行われた可能性もあります。 データ理想的には再インポートしない通常のレベルでは、上のフロント エンドのストレージ ・ サービス (LYSS) データベースのサイズのいずれかの場合これを行う可能性がありますだけより多くのデータを元に戻すにエクスポートするために注意してください。さらに、問題を拡張するストレージ ・ サービスのキューの原因となったエラーを提供したことがまず必要があります (Exchange エンドポイントのエラーの例、ネットワークの問題、またはその他の問題) の解決。

 **シナリオ 1:** プールのフェールオーバー中に、各フロントエンドのストレージ サービスからファイルがフラッシュされる場合があります。 フェールオーバーが完了したら、ツールを実行してデータを再インポートする必要があります。

 **シナリオ 2:** データがフラッシュされて自動的に 1 日または記憶域サービスへの応答としてデータベース (たとえば 60%、80%、90%) に特定のサイズのしきい値を超えます。 この自動的にフラッシュされたデータ インポートしてください再日常的に、管理者によって。 上の状況では、監視、SCOM パックが展開されない場合があります Skype ビジネス サーバー ・ ストレージ ・ サービスがストレージ ・ サービスからフラッシュされるデータに関連のイベント。 32075 のイベント Id (完全にフラッシュ操作の開始)、32076 (全体がフラッシュが完了したら)、32082 (保守レベル フラッシュの開始)、32083 (メンテナンス ・ レベルに完全なフラッシュ)、(フラッシュのデータベースがいっぱいのためが発生しました) 32089。 これらのイベント Id は、rtm 版のリリースに対応していることを注意してください。 管理者は、これらのイベントを見て、フラッシュされているファイルがあることを意味します。毎週 1 回など、このツールを使ってこのデータをインポートに定期的にする必要があります。

オンライン サービス リリースでは、状態監視の Skype ビジネス サーバーに SCOM パックが展開されている場合は新しいアラートが発生する記憶域サービスにフラッシュされたデータを再インポートするのには管理者に問い合わせてください。 警告の原因に対応するイベントは、フロントエンド サーバーのイベント ログに出されます。 イベントの出力には、フラッシュされたデータ ファイルが置かれている親パスや、警告の条件に一致するファイルの個数などが記述されています。 警告の条件は、指定の親パスに Y 日以上前のファイルが X 個以上あることです (X と Y は StorageService 内に事前設定されていますが、APPCONFIG ファイルを変更して上書きできます)。 状態の警告が出されるイベントで、親パスが異なる場合の例を以下に 2 つ示します。 1 つは Web サービスのファイル共有で、もう 1 つは各フロントエンドのローカルの Application Data ディレクトリ (例: c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService) です。 その後、管理者はこの reskit ツールを実行します。

このツールには、こと、データが所有していないフロント エンドで、ツールが実行される状況で、他のフロント エンドと同様に、それを実行しているがフロント エンドの CPU と I/O の負荷が増加します。 ユーザーがフロント エンドは負荷が高い CPU と IO、ピーク時間外などがない場合このツールを runng お勧めします。 次に、このツールでは、2 ~ 3 分を 1 つのデータ ファイルをインポートすることができます。 実行する時間を見積もる場合は、この点に留意してください。 ツールによって生成された詳細なログ ファイルが既定で表示されますファイル ストアにします。 数十 MB 以上のログ ファイルがあるために、報告されると、エラーがない場合は、それを削除します。

![記憶域サーバーのイベント ログのサンプル イベント](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a>要件

ビジネス 2015 リソース キット ツールの Skype をインストールします。 ツールは、ビジネス サーバーの Skype と Skype ビジネス サーバー管理シェルがインストールされているドメインに参加しているマシンで実行されます。 ツールでは、管理シェルのコマンドレットを使用して、プール内のすべてのフロント エンド サーバーを識別します。 次に、 **RtcLocal**データベースがインストールされているプール内のコンピューターからこのツールを実行してください。 このデータベースは、プールの web サービス ファイル共有の場所を取得するのには、ツールによって使用されます。 さらに、ツールを使用する前に各フロント エンド サーバーする必要があります最初を有効にするから、ツールが実行されるコンピューターと同様に、各フロント エンド サーバーで**有効にする PSRemoting**を使用して Windows PowerShell のリモート処理します。 それ以外の場合、このツールからリモートの Windows PowerShell コマンドは失敗します。 終了後、プール内のすべてのフロント エンド サーバーで Windows PowerShell のリモート処理オフにすることができます。 最後に、取引先企業または資格情報をツールを起動は、このツールを実行するのには、プールの web サービス ファイル共有への読み取り/書き込み権限が必要です。 それ以外の場合、ツールは IO のアクセス許可エラーで失敗します。

> [!NOTE]
> Windows Server 2012 では、[デフォルトでは、Windows Server 2008 オペレーティング システムではなく、Windows PowerShell のリモート処理が有効になります。

### <a name="examples"></a>例

```
>  C:\StorageService>ImportStorageServiceData.exe
Description:
This tool will re-import Storage Service (LYSS) flushed queue data back in.  For a pool: you are required to run this tool on a machine inside the pool which has the Lync Server Management Shell installed.  Additionally, all front end machines need to have Windows Powershell Remoting enabled before executing this tool by executing Enable-PSRemoting.  Also, please ensure that all Storage Service instance DB Size are at the 'Normal' level (verify this by viewing Eventlog events). Otherwise re-importing may cause data to be flushed out again if any Storage Service instance DB size level goes above 'Normal'.
Usage: Default behavior is to Import data from web service file share as well as any files on all Front End machines in pool.
Additional Options:
-Verbose                    : Turn verbose output on.

-StorageServiceHostName     : Host Name of Storage Service WCF endpoint.  ( Default=localhost netnamedpipe binding. )

-FileSharePath              : Import only all data from just under the UNC path specified.

ActivityID: cc3b62ff-bb66-4e61-a6e2-96cb3626315c. <-- Use this to correlate with StorageService trace logs if troubleshooting.
Type Server name (TCP binding) or press <enter> for localhost (NamePipe binding):
Using NetNamedPipeBinding...
OnTopologyChanged Event received
Web Service File Share: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService

Front Ends:
server.vdomain.com
server2.vdomain.com
server1.vdomain.com
server3.vdomain.com
Looking under directory: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService for exported data.
# Files found: 8
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
Items deserialized: 20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml

Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d
3832e4__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c
86684d3832e4__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml

Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server2.vdom
ain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42
287dd6__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2
b46a42287dd6__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml

Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=1

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15
d251e6__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759
e08a15d251e6__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml
Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=1
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346949ff8
17c220__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346
949ff817c220__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml: succeeded: 20, failed: 0
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml

Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=20
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be6
6d5317__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876
749be66d5317__0.xml
Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml: succeeded: 20, failed: 0
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml
Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=20
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda
86b565__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4
657eda86b565__0.xml
Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml: succeeded: 20, failed: 0
All files have been imported into Storage Service for path: \\dc.vdomain.com\OcsFileStore\co1-WebSer
vices-1\StorageService
Importing files for: server.vdomain.com
No files founds.
Importing files for: server2.vdomain.com
No files founds.
Importing files for: server1.vdomain.com
No files founds.
Importing files for: server3.vdomain.com
No files founds.
Writing log: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\ImportStorageServiceData
Log20120910_1609SS
Tool has finished execution.
>  C:\StorageService>
```

## <a name="lcssync"></a>LCSSync
<a name="LCSSync"> </a>

LCSSync ツールは、Skype を複数のフォレスト環境でのビジネス サーバー 2015 通信ソフトウェアの展開に役立ちます。 このツールを使用してユーザーを同期して、中心的なビジネス サーバー 2015 の Skype がインストールされているフォレストにオブジェクトが、Active Directory ドメイン サービスとして別のユーザー フォレストからのグループにお問い合わせください。

### <a name="description"></a>説明

 LCSSync は同期された Active Directory ドメイン サービスは、Skype のビジネス サーバーに対してユーザーを有効にするのには、中心のフォレスト内のオブジェクトを問い合わせてください。 シングル サインインを提供するには、プライマリ ・ ユーザー ・ アカウントする必要がありますマップ中心のフォレストの Active Directory ドメイン サービスの連絡先オブジェクトに Skype のビジネス サーバー 2015 の。 このツールは、そのマッピングを支援します。 このツールには、Microsoft Identity Integration Server で Management Agents を作成するためのテンプレートが用意されています。

### <a name="summary"></a>概要

LCSSync ツールでは、Skype をビジネス サーバー 2015 の複数のフォレスト環境で展開できます。

## <a name="lookup-user-console"></a>Lookup User Console
<a name="LUC"> </a>

LookupUserConsole ツールには、特定のユーザーに関するルーティング情報をビジネスのサーバーの内部に Skype が表示されます。 この情報は、Microsoft のサポート担当者が展開やルーティングの問題を解決するのに役立つ場合があります。

### <a name="description"></a>説明

 LookupUserConsole.exe を実行すると、SIP アドレスを許可し、内部の Skype ビジネス サーバーのルーティング情報が関連するを表示しようとしています。 コマンド プロンプトを開きます。 LookupUserConsole ツールを終了するには、「**exit**」 と入力します。

### <a name="requirements"></a>要件

ビジネス 2015 のサーバー リソース キットの Skype をインストールします。 ツールは、ビジネス サーバーの Skype がインストールされているドメインに参加しているマシンで実行されます。

### <a name="examples"></a>例

ビジネスの C:\Program Files\Skype Server 2015\ResKit\>LookupUserConsole.exe

```
> sip:john.doe@vdomain.com

  Execution time (ms):                            171.094
  Exeuction result:                               Success
  SIP URI:                                        sip:john.doe@vdomain.com
  User info:
    SID:                                          S-1-5-21-2831376166-29632525...    Display name:                                     John Doe
    Grouping ID:                                  00000000-0000-0000-0000-...
    Line URI:                                     <null>
    Policy assignment:                            TenantId={00000000--0000-000....
    SIP enabled:                                  True
    UC enabled:                                   False
    Tenant ID:                                    00000000-0000-0000-0000-...  Cluster info:
    Active cluster:                               pool0.vdomain.com
    Backup registrar cluster:                     <null>
    Deployment location:                          <null>
    Home Front-End FQDN:                          SERVER.vdomain.com
    Primary Registrar cluster:                    pool0.vdomain.com
    Remote Director external SIP FQDN:            <null>
    Remote Director internal SIP FQDN:            <null>
    Remote Director Web FQDN:                     <null>
    Routing group ID:                             4501e04e-ae48-5605-9346...
    Service tag ID:                               1266953005
    User Front-End resolved:                      True
    User in local forest:                         True
    User in remote forest:                        False
    User in split domain:                         False
    User-Services cluster:                        pool0.vdomain.com

> sip:nouser@vdomain.com

  Execution time (ms):                            948.7574
  Exeuction result:                               UserDoesNotExist

> exit
```

## <a name="msturnping"></a>MsTurnPing
<a name="MsTurnPing"> </a>

MSTurnPing ツールにより、管理者は帯域幅のポリシーを実行しているサーバーと同様に、オーディオ/ビデオ エッジおよびオーディオ/ビデオの認証サービスを実行するサーバーの状態を確認するのにはビジネス サーバー 2015 通信ソフトウェアの Skype のトポロジ内のサービスです。

### <a name="description"></a>説明

MSTurnPing ツールにより、管理者は帯域幅のポリシーを実行しているサーバーと同様に、オーディオ/ビデオ エッジおよびオーディオ/ビデオの認証サービスを実行するサーバーの状態を確認するのにはビジネス サーバー 2015 通信ソフトウェアの Skype のトポロジ内のサービスです。

このツールを使用すると、管理者は次のテストを実行できます。

1. 音声ビデオ エッジ サーバー テスト: トポロジ内の音声ビデオ エッジ サーバーに対して次のテストを実行します。

   - ビジネス サーバー オーディオ/ビデオの認証サービスの Skype を起動し、適切な資格情報を発行することを確認しています。

   - ビジネス サーバー オーディオ/ビデオ エッジ サービスの Skype を起動し、正常に外部の境界上のリソースを割り当てることができますを確認します。

2. 帯域幅ポリシー サービス テスト: トポロジ内の帯域幅ポリシー サービスを実行しているすべてのサーバーに対して次のテストを実行します。

   - ビジネス サーバー帯域幅ポリシー サービス (認証) の Skype を起動し、適切な資格情報を発行することを確認しています。

   - ビジネス サーバー帯域幅ポリシー サービス (コア) の Skype が起動され、帯域幅のチェックを正常に実行できることを確認します。

このツールは、トポロジの一部でありローカル ストアがインストールされているコンピューターから実行する必要があります。

### <a name="output"></a>出力

このツールでは、各操作の結果が出力されます。

- **AudioVideoEdgeServer** テストを実行した場合、ツールの出力は次のようになります。

  - トポロジでは、ビジネス サーバー 2015年のオーディオとビデオの認証サービスは、Skype を提供するコンピューターのテストの結果

  - トポロジでは、ビジネス サーバー 2015年のオーディオ/ビデオ エッジ サービスは、Skype を提供するコンピューターのテストの結果

- **BandwidthPolicyServer** テストを実行した場合、ツールの出力は次のようになります。

  - ビジネス サーバー 2015 の帯域幅ポリシー サービス (認証) トポロジでは、Skype を提供するコンピューターのテストの結果

  - ビジネス サーバー 2015 の帯域幅ポリシー サービス (コア) トポロジでは、Skype を提供するコンピューターのテストの結果

### <a name="requirements"></a>要件

- このツールは、トポロジ内のローカル ストアを持つコンピューターから実行する必要があります。

- このツールは、ローカル ストアへのアクセス権のある管理者として実行する必要があります。

### <a name="examples"></a>例

ツールの入力例は、次のとおりです。

```
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a>概要

このツールは、Skype にオーディオとビデオを実行しているサーバーと帯域幅ポリシー サービスの状態を確認するサーバー 2015 のビジネス管理者のための貴重なリソースです。

## <a name="network-configuration-viewer"></a>Network Configuration Viewer
<a name="NCV"> </a>

ネットワーク構成のビューアーは、次のように、リアルタイム通信セッションを許可するようにプロビジョニングされている企業の電話受付制御 (CAC) ネットワーク ・ トポロジーを表示するのにはビジネス サーバー 2015 通信ソフトウェアの管理者のための Skype で使用できます。音声またはビデオ通話の帯域幅の容量に基づきます。 ビジネス サーバー 2015 の管理者のための Skype は、ビジネス サーバー 2015 の Skype がインストールされている帯域幅ポリシー サービスによって適用される、CAC ポリシーを定義します。

### <a name="description"></a>説明

Network Configuration Viewer (NetworkConfigurationViewer.exe) を使用すると、管理者は次のタスクを実行できます。

- 読み込むし、サーバー 2015 のビジネスを展開するため、Skype から CAC のネットワーク トポロジをグラフィカルな形式で表示します。

- 帯域幅ポリシー サーバー ログ ファイルの CAC ネットワーク トポロジを読み込み、図の形式で表示する。

- CAC ネットワーク トポロジを XML 形式でディスクに保存、格納する。

- CAC ネットワーク トポロジ図を JPG または BMP 形式で保存、格納する。

- CAC ネットワーク トポロジ構成データを表示する。

- CAC ネットワーク トポロジをツリー形式で表示する。

- CAC ネットワーク トポロジ リンク (サイトから地域、地域から地域、サイトからサイトの各リンクなど) のカスタム コネクタを定義する。

- CAC ネットワーク トポロジのサイト情報、地域情報、プロビジョニングされた帯域幅ポリシーとネットワーク リンクを表示する。

### <a name="purpose"></a>用途

企業の CAC ネットワーク トポロジ リンクをグラフィカル インターフェイスで表示します。

### <a name="examples"></a>例

 **グラフィカルな形式でサーバー 2015 のビジネス展開に、Skype から CAC のネットワーク トポロジをロードし、表示**します。 ビジネス サーバー 2015 の管理者のための Skype がロードとビジネス サーバー 2015 のコンピューターでは、Skype の CAC ネットワーク トポロジの構成を表示します。次の図に示すように、**ネットワーク構成のダウンロード**] オプションを使用しています。 ツールをダウンロードするか、Skype のビジネス サーバー 2015 構成ストアへの接続がないコンピューターに展開されたときにこのような構成を表示できなくなります。

![ネットワーク構成のダウンロード](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 **グラフィック形式で、帯域幅ポリシー サーバーのログ ファイルから読み込み、ビューの CAC のネットワーク トポロジ:** ビジネス サーバー 2015 の帯域幅ポリシー サーバーの Skype は、Skype のビジネス サーバー 2015 ファイル共有の場所のログ作成メカニズムの一部として CAC ネットワーク トポロジを保存します。 ビジネス サーバー 2015 の管理者のための Skype は、次のように、**開いているネットワークの構成**] オプションを使用して、グラフィカルな形式でこのようなファイルを表示できます。

![帯域幅ポリシー サーバーのログ ファイルを開く](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

保存し、CAC のネットワーク トポロジをディスク上の XML 形式で格納します。 ビジネス サーバー 2015 の管理者のための Skype は以下のように、**ネットワークの構成のコピーを保存する**] オプションを使用して XML 形式で CAC ネットワーク トポロジの構成ファイルを保存することができます。 保存した構成ファイルはオフラインでのグラフィカルな表示に使用できます。

![ネットワーク構成の XML ファイルとしての保存](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

保存し、JPG または BMP 形式でストアの CAC ネットワーク トポロジの図: サーバー 2015 のビジネス管理者のための Skype として**ネットワーク構成の保存のダイアグラムを使用してグラフィカルな形式 (JPG と BMP ファイル形式) で CAC のネットワーク トポロジの構成を保存することができます図**オプションを次のようにします。

![ネットワーク構成の画像としての保存](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <strong>ビュー CAC ネットワーク トポロジの構成データ:</strong>Skype ビジネス サーバー 2015 管理者はようには、ネットワーク構成の表示データのオプションを使用してテキスト形式でネットワーク地域、ネットワーク サイト、帯域幅プロファイル、およびサイトのサブネットの IP アドレスなどの関連するネットワーク構成データを表示することができます。以下に。

![ネットワーク構成データの表示](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 **ツリー ビュー形式で表示の CAC のネットワーク トポロジ:** ビジネス サーバー 2015 の管理者のための Skype は、以下のように、ツール ウィンドウの左側にあるコントロール パネルを使用してグラフィカルなツリー ビューのスタイルに関連のネットワーク構成データを表示できます。

![ネットワーク構成データのツリー ビューでの表示](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 **ネットワーク トポロジのリンク (サイトの地域に、地域の地域、およびサイト間のリンク) などの CAC のカスタム コネクタを定義する:** ビジネス サーバー 2015 の管理者のための Skype は、以下のように [設定] オプションを使用して、CAC ネットワークの構成の WAN リンクにカスタムのグラフィカルなコネクタを定義できます。 これは、ネットワーク構成にプロビジョニングされている各種ネットワーク リンクを区別するのに役立ちます。

![ツール](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 **ビュー CAC ネットワーク トポロジのサイト情報、地域情報、およびプロビジョニングされた帯域幅ポリシー:** ビジネス サーバー 2015 の管理者のための Skype は、CAC ネットワーク地域の関連情報、サイト情報、および次に示すオプションを使用して情報を提供する CAC 帯域幅を表示できます。 (たとえばをクリック ネットワーク地域、ネットワーク サイト オブジェクトの**情報**)

![ネットワークのカスタム コネクタの定義](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a>概要

このツールは、Skype に CAC のネットワーク トポロジの展開をグラフィック形式で表示したいサーバー 2015 のビジネス管理者のための貴重なリソースです。

## <a name="response-group-agent-live"></a>Response Group Agent Live
<a name="RGAL"> </a>

応答グループ アプリケーションによって、エージェントは組み込みの Web サービスを使用してリアルタイムの有効な情報にアクセスできるようになります。 ただし、このデータのグラフィカル表示はアプリケーションの外部では使用できません。 応答グループ エージェント ライブ リソース キット ツールは、ビジネス通信ソフトウェアについては、プレゼンスなどの他のエージェントのリアルタイムの Skype で強化された、この情報にアクセスするためのシンプルでグラフィカルな方法を提供することでこの問題を解決します。

### <a name="description"></a>説明

Response Group Agent Live は、サインインやサインアウト機能、リアルタイム情報 (グループのメンバーシップや現在の通話数など) を応答グループ エージェントに提供する Windows アプリケーションです。 拡張したもので、エージェントのグループ] ページ (ビジネス用の Skype からアクセスできます。

### <a name="purpose"></a>用途

着信通話は応答グループ アプリケーションによってキューに配置されてから、エージェント グループにルーティングされます。どの通話を処理するかについて十分な情報に基づいて判断するために、エージェントは他のエージェントの状態や各キューで待機中の通話数など、エージェント グループに関するリアルタイム情報にアクセスできます。このような情報は、当初は応答グループ サービスからのみアクセスが可能でしたが、Response Group Agent Live によって直感的な方法で利用できるようになりました。

#### <a name="features"></a>機能

ビジネス サーバー 2015 SDK の応答グループ サービスと、Skype で応答グループのエージェントのライブのツールが作成されます。 このツールは応答グループ サービスから利用できる情報や機能 (グループのメンバーシップ、他のエージェントのプレゼンス、待機中の通話数など) を応答グループ エージェントに提供します。

下の図は、Response Group Agent Live のメイン インターフェイスを示しています。

![Response Group Agent Live ツール](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

Response Group Agent Live では、エージェントは次の主な 3 つの機能を使用できます。

- **記号の入力/出力:** エージェントのグループ (ビジネス サーバー 2015 の Skype からアクセス可能)、ページとは対照的応答グループのエージェントの Live にサインインするだけのエージェントでは、を一度にすべてのエージェントのグループ このアプリケーションでは、インポイントまたはアウトに署名するようにエージェントの 3 つのクイック方法を提供します。

  - アプリケーション内でサインイン/サインアウト (緑色と赤色) ボタンをクリックします。

  - システム トレイ アイコンを右クリックし、サインインまたはサインアウトを選択します。

  - 構成可能なキーボード ショートカットを使用します。

- **グループ メンバーシップ:** エージェント グループを選択すると、応答グループのエージェントのライブ一覧が表示されます、エージェントの右側のペインでこのグループに。 ビジネス サーバー 2015 の Skype は、このアプリケーションと同じコンピューターで実行されているは、プレゼンス情報と連絡先のカードが応答グループ エージェント Live で表示されます。 エージェントでは、IM を送信したり、そこから直接他のエージェントを呼び出しすることができます。

- **リアルタイム統計情報:** Response Group Agent Live ではすべてのエージェント グループのリアルタイム統計情報を使用できます。更新間隔は 1 分です。応答グループが通話に応答すると、グループ名の横に視覚的なインジケーターが追加され、キュー内の現在の通話数が表示されます。グループにマウスを合わせると、最長の待機時間も表示されます。

### <a name="requirements"></a>要件

Response Group Agent Live には .NET Framework 4.0 が必要です。 さらに、プレゼンス、連絡先カードの機能を利用する Skype ビジネスのローカルにインストールする必要があります (と実行している)。

#### <a name="configuration"></a>構成

アプリケーションの [Options] ダイアログ ボックスを使用すると、Response Group Agent Live を個人の好みに合わせてカスタマイズできます。また、管理者は RGAgentLive.exe.config ファイルの defaultHostAddress プロパティを直接編集して既定のホスト アドレスを定義できます。

下の図は、エージェントがホスト アドレスやショートカット キーを構成できる [Options] ダイアログ ボックスを示しています。このダイアログを表示するには、メイン インターフェイスの右上にある [Options] ボタンをクリックします。

![[Response Group Agent Live Options] ダイアログ ボックス](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

Response Group Agent Live の構成では次の 3 つの設定をカスタマイズできます。

- ホスト アドレス: これは、通常、web エージェントのホーム プールに属している FQDN をプールします。 この情報から、正確な応答グループ サービス アドレスがバックグラウンドで自動的に取得されます (ホストの後に適切なパスが付加されます)。

- [Shortcuts]: サインイン/サインアウト用の厳密なショートカットをカスタマイズできます。 唯一の制限は、両方のショートカットが、「Windows ロゴ」キー (少なくとも他のキー) を含める必要があります。

- [Start with Windows]: Windows と共に自動的に起動するようにアプリケーションを構成できます。

### <a name="examples"></a>例

下の図は、右側のウィンドウで連絡先を右クリックして、他のエージェントに電話をかけたり IM を送信したりする方法を示しています。

![通話の発信または IM の送信](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

下の図は、Response Group Agent Live に表示されるキュー内の現在の通話数と全着信通話内での最長待機時間を示しています。

![キュー情報の表示](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a>概要

迅速なサインインとサインアウト、グループのメンバーシップ、基本的なリアルタイム統計情報は、アプリケーション外部でのみ利用できる、応答グループ サービスに基づいた便利な応答グループ エージェント機能です。 応答グループ エージェント ライブ リソース キット ツールを使用してサーバー 2015 のビジネス管理者のための Skype は、Windows アプリケーションを利用して高速化し、グラフィカルな方法でタスクを実行すると、エージェントを提供できます。

## <a name="sefautil"></a>SEFAUtil
<a name="SEFAUtil"> </a>

SEFAUtil (セカンダリ拡張機能のアクティブ化) は、代理人着信、通話転送、同時着信を構成するのには、ビジネス サーバー 2015 通信ソフトウェアの管理者とヘルプデスク担当者の Skype を有効にするコマンド ライン ツールチーム呼び出しの設定およびグループは、サーバー 2015 のビジネス ユーザーの Skype のためにピックアップを呼び出します。 ツールは、管理者が特定のユーザーに対して公開されている通話のルーティングの設定を照会するようにできます。SEFAUtil ツールは、管理者がユーザーの代わりに同時に着信の転送または有効化/無効化/変更の呼び出しを使用できます。 管理者では、(SIP URI の形式) で、ターゲットを指定したり、ユーザーが既に公開されているターゲットを使用することができます。 このツールは、管理者を追加またはデリゲートを削除またはチーム呼び出しグループのメンバー ユーザーの代わりにもできます。このツールは、[マイクロソフト ユニファイド コミュニケーション管理 API (UCMA) 3.0 が組み込まれているし、管理者は、SEFAUtil の中央管理ストアの信頼されたアプリケーションを作成する必要があります。

構成代理人着信、通話転送、同時着信、チーム呼び出しの設定および、Skype のための呼び出しのピックアップをグループ化するには、ビジネス サーバー 2015 管理者およびヘルプデスク担当者の Skype を使用する SEFAUtil (第 2 の拡張機能のアクティブ化)ビジネス サーバー 2015 のユーザーです。 また、管理者は特定のユーザー向けに公開されているコール ルーティング設定のクエリを実行できます。

### <a name="description"></a>説明

SEFAUtil の現在のバージョンは、コマンド ライン ツールのみです。グラフィカル ユーザー インターフェイスがサポートされていません。 このツールは、[マイクロソフト ユニファイド コミュニケーション管理 API (UCMA) 3.0 に基づいています。 このツールの機能は、管理者およびヘルプ デスクの担当者には、次を許可します。

- ユーザーのすべてのコール ルーティング設定を表示する (着信転送、代理人、同時呼び出し、チーム呼び出し、グループ通話ピックアップなど)

- 着信転送設定を有効化、無効化、変更する (宛先や無応答タイマーなど)

- 着信転送の即時構成を有効化、無効化、変更する

- 代理人設定を有効化、無効化、変更する

- チーム呼び出しグループ設定を有効化、無効化、変更する

    > [!NOTE]
    > ビジネス サーバー 2015 SEFAUtil ツールの Skype の新しい

- 同時呼び出し設定を有効化、無効化、変更する (宛先など)

    > [!NOTE]
    > ビジネス サーバー 2015 SEFAUtil ツールの Skype の新しい

- グループ通話ピックアップ設定を有効化、無効化、変更する

    > [!CAUTION]
    > ビジネス サーバー 2015 SEFAUtil ツールの Skype の新しい

このツールの制約は次のとおりです。

- Skype のビジネス サーバー プールに置かれているユーザーに対してのみサポートされています。

- 複数ユーザーのコール ルーティング設定の一括編集はサポートされていません。

### <a name="output"></a>出力

ツールの現在のバージョンでは、[コマンド プロンプト] ウィンドウでのみ結果が表示されます。詳しくは、このドキュメント後半の「例」をご覧ください。

### <a name="purpose"></a>用途

このツールを使用するいくつかの主なシナリオを次に示します。

- Bob は経営幹部、ビジネス サーバーのテレフォニーの Skype に移動されました 彼の既存の PBX システムには代理人が設定されています。 ビジネス サーバー 2015 は、Skype への移行の一環として、管理者は、Bob は、既存の委任の構成を反映するようにルーティングを構成することができます。

- 西村さんは旅行中で、顧客からの重要な連絡を待っています。しかし、ホテル滞在中はコンピューターを使うことができません。彼女はヘルプデスクに電話して、勤務先電話番号にかかってきたすべての電話を携帯電話の番号に転送してもらうよう頼みました。ヘルプデスク担当者は、彼女のためにこのような構成を行うことができます。

- 自分の作業時間数のジョーの呼び出ししようとして、モバイルのボイスメール作業では常にただし、他のほとんどの場所で正しく機能していることが表示されます。 レベルのヘルプデスク技術者では、Joe のルーティングの構成を表示することがし、Joe が自分の携帯電話に構成されている同時呼び出しを検出します。 技術者は、彼のオフィスをモバイルのカバレッジに関する Joe が表示され、同時着信ルールであるジョーのモバイルのボイス メールには、ネットワーク ・ カバレッジが低いときに呼び出しの原因を特定することがします。

- Mike は、contoso 社で新しい従業員とすべてのメンバーが構成されているチーム呼び出しには、Skype のビジネス サーバー 2015 に対して有効にすると、新しいチームに参加する彼は、管理者が設定を彼のチーム呼び出しグループに、すべての新しいチーム メンバーを含めること、さらに、管理者が彼のチームのメンバーのそれぞれのチーム呼び出しグループのメンバーとしてマイクを追加します。

- Contoso の人事部門のカスタマー サービス プラクティスとは、すべての発信者に対して最初の電話から個人サービスを提供することです。 部門のメンバー全員がお互いのすぐそばに座っているとすれば、チーム呼び出しで全員の電話が一斉に鳴るのはチームにとって非常に混乱のもとになります。 チームのメンバーを中断することがなく最高のサービスを提供するには、ビジネス サーバー 2015 管理者の Skype 活用グループ コール ピックアップ機能します。 管理者は部門の全員をピックアップ グループに追加して、ピックアップ グループ番号を伝えます。 原田さんが席を外している場合は、彼女の電話が鳴っていることに気付いた松本さんが自分の席から電話に応答します。

### <a name="requirements"></a>要件

SEFAUtil ツールは信頼されたアプリケーション プールに属しているコンピューターでのみ実行できます。このコンピューターには UCMA 3.0 がインストールされている必要があります。ツールを実行するには、SEFAUtil アプリケーション ID を持つ新しい信頼されたアプリケーションをプール内に作成する必要があります。

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a>SEFAUtil ツール用の新しい信頼されたアプリケーションの作成

1. SEFAUTil ツールは信頼されたアプリケーション プールに属しているコンピューターでのみ実行できます。 必要な場合、新しい信頼されたアプリケーション プールとプールを追加する実行できます、Skype 経由でビジネス サーバー管理シェルの次のコマンドレットで。

   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > SEFAUtil ツールを実行するコンピューターには UCMA 3.0 をインストールする必要があります。

2. 信頼されたアプリケーションを SEFAUtil ツールのトポロジ内に定義する必要があります。 SEFAUtil は、新しい信頼されたアプリケーションとして定義するにビジネス サーバー管理シェルには、Skype を使用し、次のコマンドレットを実行します。

   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > 必要に応じて、別のポートを使用できます。
    
    > [!NOTE]
    > プールの FQDN: SEFAUtil アプリケーション (通常は、ビジネスのフロント エンド サーバーの _gt またはプールの Skype) をホストするプールまたはサーバーの FQDN です。
    > プール FQDN をレジストラー: ビジネスのフロント エンド サーバーまたはこのアプリケーション プールに関連付けられているプールの Skype の FQDN です。
    > プール サイト: このプールは、ホーム サーバーをサイトのサイト ID です。

3. トポロジの変更を有効にする必要があります。 トポロジの変更を有効にすることができるよう、Skype を使用してビジネス サーバー管理シェルの次のコマンドレットを実行します。

   ```
   Enable-CsToplogy
   ```

4. 必要な場合、Skype ビジネス サーバー 2015 リソース キット ツールのサーバーにインストールする (サーバーが信頼されたアプリケーション プールの一部である必要があります) SEFAUtil ツールを実行するために使用します。

5. SEFAUtil が正しく実行していることを確認します。 そのためには、Windows コマンド プロンプトから管理者権限でツールを実行し、展開内のユーザーの着信転送設定を表示します。 既定では、ツールが配置されます:「ビジネス サーバー 2015\Reskit の ...\Program Files\Skype」です。 ユーザーの着信転送設定を表示するには、次のコマンドを実行します。

   ```
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    ユーザーの着信転送設定が表示されます。

#### <a name="group-call-pickup"></a>グループ通話ピックアップ

コール ピックアップのグループには、機能を完全に有効にするためのビジネス サーバー 2015 の Skype に追加の構成が必要です。 ユーザーにピックアップ グループを割り当てる前に、この機能の計画と展開の手順について、グループ通話ピックアップの製品ドキュメントを参照してください。

### <a name="examples"></a>例

#### <a name="display-current-call-handling-settings"></a>現在の通話処理設定の表示

次のコマンドでは、ユーザーの通話処理が表示されます。  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> この例では、 **/server**スイッチを使用して、ビジネスのサーバーに接続するための Skype を指定します。

 **出力**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a>着信転送/応答なしの宛先の設定

この例では、着信転送/応答なしの宛先と呼び出しの遅延を設定します。 ここでは、/server スイッチが指定されていません。SEFAUtil しようとすると自動検出、Skype のビジネス サーバー 2015。

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
```

 **出力**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a>着信転送の即時有効化

この例では、別のユーザーへの着信転送をすぐに有効にします。

```
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 **出力**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a>着信転送の即時無効化

この例では、別のユーザーへの着信転送をすぐに無効にします。

```
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com  /disablefwdimmediate
```

 **出力**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>代理人としてのユーザーの追加と代理人の同時呼び出しの設定

この例では、ユーザーを代理人として追加し、代理人の同時呼び出しを設定します。

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 **出力**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a>代理人の同時呼び出しルールの変更

この例では、前の例で設定した代理人の同時呼び出しルールを遅延呼び出しルールに変更します。

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 **出力**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a>代理人の削除

この例では代理人を削除します。

> [!NOTE]
> 最後の代理人が削除されると、代理人着信は自動的に無効になります。

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 **出力**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>代理人の追加と代理人への着信転送ルールの設定

この例では、代理人を追加し、代理人への着信転送ルールを設定します。

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 **出力**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>同時呼び出しの有効化と宛先番号の設定

この例では、同時呼び出しを有効にして、同時呼び出しの宛先番号を設定します。

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> 既に同時呼び出しを有効にしているユーザーの同時呼び出しの宛先番号を変更するには、コマンドに /enablesimulring スイッチを追加します。追加しない場合、宛先番号は変更されません。

 **出力**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a>同時呼び出しの無効化

この例では、同時呼び出しを無効にします。

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 **出力**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>チーム呼び出しのチーム メンバーの追加とチーム呼び出しメンバー グループへの同時呼び出しの設定

この例では、ユーザーのチーム呼び出しグループにチーム メンバーを追加し、チーム呼び出しグループへの同時呼び出しを有効にします。

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> ユーザーのチーム呼び出しグループにチーム メンバーを追加すると、ユーザーの同時呼び出しの設定がチーム呼び出しグループを同時に呼び出すように自動的に切り替わります。

 **出力**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a>チーム呼び出しグループからのメンバーの削除

この例では、ユーザーのチーム呼び出しグループからチーム メンバーを削除します。

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> 削除対象のメンバーがチーム呼び出しグループで唯一のメンバーである場合、チーム呼び出しグループの同時呼び出しは自動的に無効になります。

 **出力**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a>チーム呼び出しグループの遅延呼び出しの設定

この例では、チーム呼び出しグループの時間設定の遅延呼び出しを変更します。

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 **出力**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a>チーム呼び出しの有効化

この例では、ユーザーのチーム呼び出しを有効にします。

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> ユーザーのチーム呼び出しグループにメンバーが存在しない場合は、チーム呼び出しを使用できません。

 **出力**

#### <a name="disable-team-call"></a>チーム呼び出しの無効化

この例では、ユーザーのチーム呼び出しを無効にします。

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 **出力**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>グループ通話ピックアップの有効化とユーザーへのピックアップ グループの割り当て

この例では、ユーザーにピックアップ グループを割り当て、グループ通話ピックアップを有効にします。

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 **出力**

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a>グループ通話ピックアップの無効化

この例では、特定のユーザーのグループ通話ピックアップを無効にします。

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> ユーザーのグループ通話ピックアップを無効にした場合、ユーザーに割り当てられたグループ番号は保持されません。そのユーザーのグループ通話ピックアップを後からもう一度有効にする場合は、/enablegrouppickup スイッチでグループ番号をもう一度割り当てる必要があります。

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a>SYSPrep.ps1
<a name="SYSPrep"> </a>

### <a name="description"></a>説明

SYSPrep.ps1 は、Windows Server 2008 オペレーティング システムのコンピューターに次の Skype ビジネス サーバー 2015 の前提条件をインストールする Windows PowerShell スクリプトです。

- Microsoft .Net Framework 4.5

- Microsoft SQL Server Express

- Windows Powershell バージョン 3.0

- Visual C++ 2010 再頒布可能パッケージ

- Internet Information Server の更新プログラム

- Windows Identity Foundation

- Skype ビジネス サーバー 2015 のコア ファイルの

  このスクリプトは Microsoft Windows オペレーティング システム用のシステム準備ツールと名前は似ていますが、別のツールです。 このスクリプトのみサーバー 2015 のビジネスの Skype の必須コンポーネントがインストールされます。 これらの必須コンポーネントをインストールしたら、Windows SYSPrep ツールを使用して、サーバーのイメージを作成できます。

### <a name="requirements"></a>要件

SYSPrep.ps1 スクリプトを実行する前に、Windows Server 2008 オペレーティング システムのコンピューター上のローカル フォルダーに必須コンポーネントのファイルをコピーする必要があります (たとえば**D:\Setup)**。 このフォルダーが具体的にビジネス サーバー 2015 ファイルでは、Skype のコピーを含めるも必要があります**Setup.exe** 。 必須コンポーネントのファイルは、次の場所からダウンロードできます。


| **必須コンポーネント**                                | **場所**                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| Microsoft .Net Framework 4.5  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| Microsoft SQL Server Express 2008 R2  <br/>     | <https://www.microsoft.com/en-us/download/details.aspx?id=23650>  <br/> |
| Windows Powershell バージョン 3.0  <br/>           | <https://www.microsoft.com/en-us/download/details.aspx?id=34595>  <br/> |
| Visual C++ 2010 再頒布可能パッケージ  <br/>          | <https://www.microsoft.com/en-us/download/details.aspx?id=5555>  <br/>  |
| Internet Information Server の更新プログラム  <br/>      | <https://www.microsoft.com/en-us/download/details.aspx?id=34869>  <br/> |
| Windows Identity Foundation  <br/>              | <https://www.microsoft.com/en-us/download/details.aspx?id=17331>  <br/> |
| ビジネス サーバー 2015 の Setup.exe の Skype  <br/> | Skype ビジネス サーバー 2015 のメディアをコピーします。  <br/>                   |

### <a name="parameter"></a>パラメーター

**- SetupFolder**パラメーターには、引数としての必須コンポーネントのファイル ディレクトリの場所

### <a name="examples"></a>例

SYSPrep.ps1 スクリプトを実行し、ビジネス サーバー 2015 の前提条件の Skype をインストールするには、管理者特権でコマンド プロンプトから次のコマンドを実行します。

```
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a>Unassigned Number Announcements Migration
<a name="UNAM"> </a>

未使用の番号のお知らせ移行ツールにより、ビジネスのサーバーまたはプールの Skype のソースからのお知らせアプリケーションでサービスが割り当てられていない番号構成を移動するのには管理者がビジネス サーバー 2015、Skype、先 Skype ビジネス サーバーまたはプール。

### <a name="description"></a>説明

Unassigned Number Announcements Migration ツールは Windows PowerShell スクリプトであり、アナウンス アプリケーションによるサービスを受けている未使用の番号の構成を移行元のサーバーまたはプールから別のサーバーまたはプールに移行します。

Unassigned Number Announcements Migration スクリプトを実行すると、次の操作が行われます。

1. 移行元のサーバーまたはプールでホストされているアナウンス アプリケーションの未使用の番号のアナウンスが使用しているすべての音声ファイルを、移行先のサーバーまたはプールのファイル ストアに移行します。

    > [!NOTE]
    > オーディオ ファイルは、移動先のプールにコピーしているした後、元のプールから削除されます。

2. 移行元のサーバーまたはプールでホストされているアナウンス アプリケーションに構成されているすべての未使用の番号のアナウンスを、移行先のサーバーまたはプールに移行します。

3. 移行元のサーバーまたはプールでホストされているアナウンス アプリケーションによるサービスを受けているすべての未使用の番号の範囲を、移行先のサーバーまたはプールにもう一度割り当てます。

スクリプトの実行が成功すると、移行元のサーバーまたはプールでホストされているアナウンス アプリケーションによるサービスを受けていたすべての未使用の番号の範囲が、同じ構成を使用して移行先のサーバーまたはプールによるサービスを受けるようになります。

### <a name="output"></a>出力

**移動 CsAnnouncementConfiguration**スクリプトは、移行処理の成否に実行されたビジネス サーバー管理シェル ウィンドウの Skype で示されます。

エラーによって操作の実行が中断した場合、移行に成功した未使用の番号の範囲は稼動状態で移行先に残り、移行する予定の残りの未使用の番号の範囲も稼動状態で移行元に残ります。残りの構成を完全に移行するには、エラーを修正してからもう一度スクリプトを実行します。

### <a name="purpose"></a>用途

Unassigned Number Announcements Migration スクリプトは、次の 3 つのシナリオで使用できます。

- **ビジネス サーバーの Skype の新しいバージョンに、構成設定を移行する:** ビジネス サーバー 2015 の Skype に移行する処理は、contoso 社と、Skype ビジネス サーバーの移行プロセスの一部として管理者には、Lync からのお知らせアプリケーションによって処理された割り当てられていない番号構成を移動します。ビジネス サーバー 2015 展開新しい Skype に server 2013 展開します。 構成の設定を移動するには、ビジネス サーバー管理者のための Skype は、割り当てられていない番号お知らせの移行ツールを使用します。

- **にロールバックするには展開 Skype からビジネス サーバー 2015 の Lync Server 2013:** 予期しない要因は、期日は、Contoso は、ビジネス サーバー 2015 展開新しい Skype に移行をロールバックしています。 サービスの中断を最小限に抑えるには、ビジネス管理者の Skype は構成のロールバック サーバー 2015 のビジネス展開を Skype から Lync Server 2013 の展開に割り当てられていない番号お知らせの移行ツールを使用します。

- **展開間でデータを移動すること:** Contoso 社は、中、1 つのプールのすべてのサーバーを新しいサーバーに置き換えることです。 新しいプールには、以前からのすべてのデータ移動の戦略は、ビジネス サーバー 2015 プールの場合は、新しい Skype を導入して、古いプールを廃止します。 新しいプールを展開した後は、Unassigned Number Announcements Migration ツールを使用して、古いプールから新しいプールに構成を移行します。

#### <a name="requirements"></a>要件

ツールの正常な実行に必要な主な要件は、次のとおりです。

1. ビジネス サーバー管理シェルのインストールされている Skype を搭載したコンピューターからスクリプトを実行する必要があります。

2. アナウンス アプリケーションは、ソースと宛先 Skype ビジネス サーバーまたはプールに正常に展開します。

#### <a name="move-csannouncementconfiguration-script"></a>Move-CsAnnouncementConfiguration スクリプト

Move-CsAnnouncementConfiguration スクリプトでは、下の表に示す 2 つのパラメーターが必要です。

![Move-CsAnnouncementConfiguration のパラメーター](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a>例

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a>ビジネス サーバー 2015 のプールの Lync Server 2013 プールから割り当てられていない番号お知らせの構成を Skype に移動

次の使用例では、未使用の番号のお知らせを (Lync Server 2013) 移動元のプールから移動先のプール (Skype のビジネス サーバー 2015) に移動します。

```
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a>Lync Server 2013 プールに割り当てられていない番号お知らせの構成を Skype からビジネス 2015 のサーバー プールの移動

次の使用例では、未使用の番号のお知らせを (Skype ビジネス サーバー 2015 の) 元のプールから移動先のプール (Lync Server 2013) に移動します。

```
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a>Web Conf Data
<a name="WebConfData"> </a>

Web Conf データ ツールは、Web 会議の開催者が関連付けられたデータをより細かく制御するビジネス サーバー 2015 通信ソフトウェアの Skype の管理者を使用できます。 シナリオには、時刻のスタンプの条件に基づいて特定のユーザーの会議のデータを削除する機能が含まれます。

### <a name="description"></a>説明

このツールを使用すると、管理者は次の操作を実行できます。

1. 1 人のユーザーに関連付けられているすべての Web 会議データを検索する。

2. 1 人のユーザーに関連付けられているすべての Web 会議データを削除する。

3. 特定の日付よりも古い、1 人のユーザーに関連付けられているすべての Web 会議データを削除する。

4. ユーザーがあるプールから別のプールに移行した場合に、その 1 人のユーザーに関連付けられているすべての Web 会議データを移行する。

> [!NOTE]
> Lync Server 2010 のリソース キット ツールには、そのユーザーが別の 1 つのプールに移動した場合に、1 人のユーザーに関連付けられているすべての Web 会議のデータの移動がサポートされています。 このツールでは **MoveConferenceData** パラメーターのほうを優先して、この機能は現在廃止されています。 詳細については、このパラメーターは、[移動 CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps)コマンドレットを参照してください。

このツールでは、非アクティブな会議の会議データのみが削除されます。アクティブな会議 (開催中の会議) は削除できません。

このツールはターゲット ユーザーと同じプール内にあるコンピューターから実行する必要があります。会議コンテンツ データをこのツールで管理しているユーザーは同じユーザー プールに所属している必要があります。

### <a name="output"></a>出力

このツールでは、次の各操作の結果が出力されます。

- クエリを実行した場合は、該当のユーザーを開催者とする、すべての非アクティブな会議のデータ フォルダーの一覧が出力されます。

- 削除を実行した場合は、削除対象のデータがあるすべての会議データ フォルダーの一覧が出力されます。

### <a name="requirements"></a>要件

このツールは、開催者が現在所属しているのと同じプール内で実行する必要があります。

このツールは、コンテンツ ファイル ストアへのアクセス権を持つ管理者特権を使用して実行する必要があります。

### <a name="examples"></a>例

下の表にパラメーターを示します (一部は例で使用されています)。

![Web Conf Data ツールのパラメーター](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

上の例は query コマンドの動作を示しています。このコマンドの出力は、ツールの影響を受けるすべての会議コンテンツ フォルダーの一覧になります。

```
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

上の例は delete コマンドの動作を示しています。delete コマンドにより、このユーザーのすべての非アクティブな会議フォルダーが削除されます。

### <a name="summary"></a>概要

このツールは、会議データをより正確に制御する必要のある管理者にとって役立つツールとなります。


