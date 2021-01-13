---
title: Skype for Business Server 2015 リソース キット ツールのドキュメント
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: このトピックでは、Skype for Business Server 2015 リソース キットのツールについて、各ツールの目的と使用例を含めて説明します。 Skype for Business Server 2015 リソース キットは、Skype for Business Server 2015 を展開および管理する IT 管理者が日常的な作業を容易にするのに役立ちます。 たとえば、Web Conf Data ツールを使用すると、オンライン会議中にユーザーがアップロードしたデータを簡単に制御できます。 SEFAUtil ツールを使用して、ユーザーの代理呼び出しの転送と応答を設定できます。 IT 管理者は、これらのツールを使用して Skype for Business Server 2015 の管理を効果的に行う必要があります。
ms.openlocfilehash: bf1a1d946c998466b118e0ab2038044a48d90970
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822037"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a>Skype for Business Server 2015 リソース キット ツールのドキュメント

このトピックでは、Skype for Business Server 2015 リソース キットのツールについて、各ツールの目的と使用例を含めて説明します。 Skype for Business Server 2015 リソース キットは、Skype for Business Server 2015 を展開および管理する IT 管理者が日常的な作業を容易にするのに役立ちます。 たとえば **、Web Conf Data** ツールを使用すると、オンライン会議中にユーザーがアップロードしたデータを簡単に制御できます。 **SEFAUtil ツールを** 使用して、ユーザーの代理呼び出しの転送と応答を設定できます。 IT 管理者は、これらのツールを使用して Skype for Business Server 2015 の管理を効果的に行う必要があります。

## <a name="installation-of-the-resource-kit-tools"></a>リソース キット ツールのインストール

Skype for Business Server 2015 リソース キットをインストールするには、ダウンロード [ センターから ](https://www.microsoft.com/download/details.aspx?id=52631)OCSReskit.msiをダウンロードします。

この **OCSResKit.msi** を実行して、簡単なインストールを実行します。 .msi は **、%Program Files%\Skype for Business Server 2015\ResKit** というパスのすべてのツールをインストールします。 自己格納型の実行可能ファイルであるツールは、このフォルダーにあります。 サポート ファイルも含むツールは、独自のサブフォルダーに含まれています。

## <a name="supported-environments"></a>サポートされる環境

Skype for Business Server 2015 リソース キットは、Skype for Business Server 2015 (通常は Skype for Business Server 2015 の実行に使用される) に必要な仕様を満たすサーバーにインストールする必要があります。

## <a name="resource-kit-tools-overview"></a>リソース キット ツールの概要

Skype for Business Server 2015 リソース キットに用意されているツールの一覧を次に示します。 要件や使用例など、各ツールの説明については、以下のセクションで説明します。

- [ABSConfig](resource-kit-tools.md#ABSConfig)

- [帯域幅ポリシー サービス モニター](resource-kit-tools.md#bpsm)

- [Bandwidth Utilization Analyzer](resource-kit-tools.md#bua)

- [Call Parkometer](resource-kit-tools.md#callpark)

- [DBAnalyze](resource-kit-tools.md#dba)

- [ストレージ サービス データのインポート](resource-kit-tools.md#Issd)

- [LCSSync](resource-kit-tools.md#LCSSync)

- [ユーザー コンソールを参照する](resource-kit-tools.md#LUC)

- [MsTurnPing](resource-kit-tools.md#MsTurnPing)

- [ネットワーク構成ビューアー](resource-kit-tools.md#NCV)

- [Response Group Agent Live](resource-kit-tools.md#RGAL)

- [SEFAUtil](resource-kit-tools.md#SEFAUtil)

- [SYSPrep.ps1](resource-kit-tools.md#SYSPrep)

- [割り当てられていない番号アナウンスの移行](resource-kit-tools.md#UNAM)

- [Web Conf Data](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a>ABSConfig
<a name="ABSConfig"> </a>

アドレス帳サービス構成ツール (ABSConfig) は、管理者が Skype for Business Server 2015 のアドレス帳サービス構成をカスタマイズするのに役立つ管理ツールです。 また、このツールを使用すると、Skype for Business Server 2015 管理者は既定のアドレス帳サービス設定を復元できます。

### <a name="description"></a>説明

ABSConfig は、管理者がアドレス帳サービスに関連する Active Directory ドメイン サービス属性を構成できるグラフィカル ユーザー インターフェイス アプリケーションです。

このツールの主なシナリオは次のとおりです。

- 管理者が Active Directory ドメイン サービスの属性を Skype for Business Server 2015 の属性にマップできる。

- 管理者がアドレス帳サービス ファイルに含める、または除外する Active Directory ドメイン サービス属性を指定する。

- 管理者が既定のアドレス帳サービスの設定を復元する。

ABSConfig ツールは、次のファイルを使用ABSConfig.exeできます。 ツールが開き、[属性の構成 **] タブが開** きます。この表には、Active Directory ドメイン サービスの属性を Skype for Business Server 2015 の属性フィールドにマップするオプションと、特定の属性フィルターに基づいてアドレス帳サービス ファイルに含めるユーザーまたは除外するユーザーを指定するオプションがあります。 また、アドレス帳ファイルに含める電話番号の値をカスタマイズするオプションも用意されています。 [ **既定値に戻す]** オプションを使用すると、管理者はアドレス帳サービスの設定を既定値に復元できます。

> [!NOTE]
> 異なる OC フィールド名への AD 属性の再マッピングは、アドレス帳ファイルのダウンロードでのみ機能し、アドレス帳 Web クエリではサポートされません。

### <a name="output"></a>出力

ABSConfig は、アドレス帳サービス構成をデータベースに格納します。

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a>用途

ABSConfig は、Skype for Business Server 2015 アドレス帳サービスをカスタマイズするための迅速かつ簡単な方法を提供します。

### <a name="requirements"></a>要件

#### <a name="computer"></a>コンピューター

ABSConfig は、Skype for Business Server 2015 がインストールされているドメインに参加しているコンピューターからのみ実行できます。 Skype for Business Server 2015 Enterprise Edition の場合、このツールは、セットアップ中にアドレス帳サービスが有効になっているフロントエンド サーバーで実行できます。

#### <a name="network"></a>ネットワーク

コンピューターは、フロントエンド プールとバック エンド データベースに接続できる必要があります。

#### <a name="software"></a>ソフトウェア

ABSConfig ツールを実行する前に、次のソフトウェア コンポーネントをインストールする必要があります。

- Skype for Business Server 2015

#### <a name="users"></a>ユーザー

Skype for Business Server 2015 展開の更新に必要なアクセス許可を持つ管理者。

### <a name="examples"></a>例

ABSConfig を開始するには、コマンド プロンプト **でABSConfig.exe** 入力します。 ABSConfig ツールのユーザー インターフェイスを次に示します。

![次ABSConfig.exeツール。](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a>概要

ABSConfig ツールを使用すると、管理者は Skype for Business Server 2015 アドレス帳サービスを迅速かつ簡単にカスタマイズできます。

## <a name="bandwidth-policy-service-monitor"></a>帯域幅ポリシー サービス モニター
<a name="bpsm"> </a>

Bandwidth Policy Service Monitor ツールは、管理者が次の一覧を表示することを目的とします。

1. トポロジで構成済みのすべての Skype for Business Server 2015 帯域幅ポリシー サービス (認証とコア)

2. 各サービスが他の帯域幅ポリシー サービスおよびエッジ サーバーに対して行う接続

3. ネットワーク構成ドキュメントで構成されているリンクすべてと、各帯域幅ポリシー サービスによって報告されるリアルタイムの帯域幅使用量

### <a name="description"></a>説明

Bandwidth Policy Service Monitor ツールは、GUI ベースのアプリケーションとして実装されます。 管理者は、次のコマンドを実行してツールPDPMonUI.exe。

ツールが起動すると、トポロジ内の帯域幅ポリシー サービスの一覧の検出が試行されます。 最初の更新が完了すると、ウィンドウの左側のウィンドウに、属するクラスターによってグループ化されたサービスの一覧が表示されます。

管理者が特定の帯域幅ポリシー サービスを選択すると、右側のウィンドウに特定のサービスに関する情報が表示されます。 このウィンドウには、情報を表示する 2 つのメイン タブがあります。

#### <a name="machine-info-tab"></a>[コンピューター情報] タブ

[ **コンピューター情報** ] タブには、選択されている帯域幅ポリシー サービスの詳細と、選択した帯域幅ポリシー サービスが他のサービスに対して行ったすべての接続の一覧と状態が表示されます。

#### <a name="topology-info-tab"></a>[トポロジ情報] タブ

[ **トポロジ情報] タブ** には、ネットワーク構成設定で構成されているリンクの一覧が表示されます。 各リンクについて、音声とビデオの帯域幅容量が表示されます。 さらに、現在利用されている帯域幅は、Kbps と容量の割合の両方で表示されます。 ツールは、容量に近い使用率を持つリンクを強調表示するために色分け機能を使用します。これにより、管理者はこのようなリンクをすばやく分離できます。

> [!NOTE]
>  帯域幅ポリシー サービス モニター ツールが構成済みの帯域幅ポリシー サービスに接続するときに障害が発生した場合、[コンピューター情報]タブと [トポロジ情報] タブの情報は入力されません。 ただし、ツールが最初に接続した後にサービスへの接続が失われる可能性があります。 このような場合、管理者には古い情報が表示される場合があります。 各タブ **には、** 特定の帯域幅ポリシー サービスのデータが最後に更新された時刻を管理者が確認できる最終更新タイム スタンプがあります。

### <a name="output"></a>出力

コマンド ライン出力はありません。プログラム出力は、メインのグラフィカル ユーザー インターフェイス (GUI) に含まれる。

### <a name="purpose"></a>用途

Bandwidth Policy Service Monitor ツールの目的は、管理者がトポロジで定義されている各帯域幅ポリシー サービスの状態を確認できるようです。 また、管理者は、ネットワーク構成ドキュメントで定義されているリンクすべてについて、リアルタイムの帯域幅の使用状況を確認できます。

### <a name="requirements"></a>要件

Bandwidth Policy Service Monitor ツールは、Skype for Business Server トポロジの一部であるコンピューターで実行する必要があります。

### <a name="summary"></a>概要

帯域幅ポリシー サービス モニター ツールは、管理者がトポロジ内のすべての帯域幅ポリシー サービスの状態を検査し、さらに重要な点として、ネットワーク構成設定で定義されているリンクの帯域幅使用率をリアルタイムで取得できるような、重要なリソースです。

## <a name="bandwidth-utilization-analyzer"></a>Bandwidth Utilization Analyzer
<a name="bua"> </a>

Bandwidth Utilization Analyzer は、エンタープライズ ネットワーク内の WAN リンクを通して UC エンドポイントによる帯域幅消費のさまざまなビューに関するレポートを作成するツールです。 これらのレポートは、現在の帯域幅消費パターンを理解し、帯域幅容量の計画を支援するために使用できます。

### <a name="description"></a>説明

Bandwidth Utilization Analyzer は、GUI ベースのアプリケーションとして実装されます。 このツールは、ネットワーク全体の音声使用率に関するレポートを生成し、容量計画に役立ちます。 また、さまざまなリンクに割り当てられている帯域幅容量に対して反復処理も行います。

### <a name="output"></a>出力

Bandwidth Utilization Analyzer は、システムで構成されている WAN リンクすべてについて、帯域幅容量と音声の使用率のグラフィック プロットを提供します。

### <a name="purpose"></a>用途

音声およびビデオの展開では、エンタープライズ ネットワーク全体のメディア トラフィックの帯域幅使用率の傾向を監視し、把握する必要があります。 Bandwidth Utilization Analyzer ツールを使用すると、管理者はこれを実現できます。 このツールは、次の手順を実行します。

- ネットワーク全体の音声使用率に関する特定のレポートを生成します。

- より効果的な容量計画と、さまざまなリンクに割り当てられた帯域幅容量の反復に役立ちます。

Bandwidth Utilization Analyzer は、帯域幅容量と使用率レポートのグラフィカル プロットを生成できます。これらは次のとおりです。

- エンタープライズ ネットワーク内のすべての WAN リンク

- 選択された WAN リンクでフィルター処理

- リンク容量を超えた WAN リンクでフィルター処理

- プロビジョニングされた帯域幅の利用が低い WAN リンクでフィルター処理

- 重要なレベルに達している WAN リンク (WAN リンクの帯域幅容量の 90% を超える帯域幅使用率) でフィルター処理する

- WAN リンクの種類 (ネットワーク サイト リンク、エリア間リンク、サイト内のリンク) でフィルター処理

- ネットワーク地域でフィルター処理

#### <a name="applications"></a>アプリケーション

Bandwidth Utilization Analyzer には、次の 2 つのアプリケーション (ツール) があります。

- **WanLinkLogCollector.exe** このツールを使用すると、ユーザーは必要な情報を入力できます。

- **BandwidthUtilizationAnalyzer.xlsm** Microsoft Excel スプレッドシート ソフトウェア レポートは、ユーザーが自動的に起動WanLinkLogCollector.exe。 このアプリケーションを使用すると、ユーザーは後で示すようにレポートにフィルターを適用できます。

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a>Bandwidth Utilization Analyzer の使用のフェーズ

Bandwidth Utilization Analyzer を使用する場合、次の 2 つのフェーズがあります。

- ログを収集します。ログは、このログを使用してWanLinkLogCollector.exe

- m を使用して実行されるレポートをBandwidthUtilizationAnalyzer.xlsする

    > [!IMPORTANT]
    > エンド ユーザーが手動BandwidthUtilizationAnalyzer.xls起動しない方法を強く推奨します。

#### <a name="starting-bandwidth-utilization-analyzer"></a>帯域幅使用率アナライザーの開始

コマンド WanLinkLogCollector.exeエクスプローラーを使用して、コマンド を起動します。

 **ユーザー設定WanLinkLogCollector.exe**

この機能を使用するには、次の 3 つのWanLinkLogCollector.exe。

1. **タイムラインをログに記録する** レポートの生成に必要なタイムラインを指定する

2. **ファイル ディレクトリを指定する** ファイルの場所情報を提供する

3. **ログを収集してレポート ビューアーを起動する** コマンドを実行してレポートを生成する

#### <a name="step-1---log-the-timeline"></a>手順 1 - タイムラインをログに記録する

タイムラインをログに記録すると、ツール ユーザーは、次の図に示すように次を指定できます。

1. **開始日** これは、レポートが生成されるタイムラインの開始日です。たとえば、2010 年 8 月 1 日です。

2. **終了日** これは、レポートが生成されるタイムラインの終了日です。たとえば、2010 年 9 月 30 日です。

     ![帯域幅使用率 A の開始日と終了日](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a>手順 2 - ファイル ディレクトリを指定する

次に示すように、ユーザーは次のファイル ディレクトリを指定できます。

- **サーバー ログ ファイルの場所** 帯域幅ポリシー サーバー ログが格納されるフォルダーの場所。 これは通常、FE \<fileserver\> \\ \> \AppServerFiles\PDP<選択する場合に使用します。

- **一時ファイルの保存場所** レポートの生成中に中間ファイルが保存される一時ファイルの場所。

    ![Bandwidth Utilization Utilization Utilization のファイル ディレクトリ](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > サーバー ログと一時ファイル ストア フォルダーへの十分なファイル アクセスがツール ユーザーに提供されます。

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>手順 3 - ログを収集し、レポート ビューアーを起動する

ログを収集してレポート ビューアーを起動するには、次に示すように **[実行** ] をクリックします。 この手順では、必要なデータを収集します。

![Bandwidth Utilization Utilization Utilizationy のデータを収集する](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

入力検証に成功すると、次に示すメッセージが表示されます。

![帯域幅 Utili で収集された通知をログに記録する](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

[**OK**] をクリックします。 BandwidthUtilizationAnalyzer.xlsm が自動的に開始されます。 メッセージ ボックスの指示に従います。 詳細については、次 **のセクションBandwidthUtilizationAnalyzer.xlsm** を使用するを参照してください。


### <a name="using-bandwidthutilizationanalyzerxlsm"></a>BandwidthUtilizationAnalyzer.xlsm の使用

1. m BandwidthUtilizationAnalyzer.xlsが自動的に開始された場合は、次に示すように **[最新** の情報に更新] をクリックします。

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. ファイル フォルダーを開いた後、次consolidated.csvメッセージ ボックスで指定されている場所からファイル フォルダーを選択します。 また、場所は **C:\Temp として表示されます**。

     ![BandwidthUtilizationAnalyzer でフォルダーを開く。](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. [**インポート**] をクリックします。

4. グラフィカル プロットは自動的に生成されます。 これは、バックグラウンドでの作業ポインターが消えたときに使用できます。

     ![レポート ビューでのフィルターの適用。](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a>レポート ビューにフィルターを適用する

以下に示すように、レポート ビューに適用できるフィルターを次に示します。

![レポート ビューでのフィルターの適用。](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. **名前** WAN リンクでフィルター処理します (フィルターはグラフの右側にあります)。プレフィックスは、次のリンクの種類を表します。垂直 (青) ボックスを確認します。

   - **S サイト** ネットワーク サイトからネットワーク地域への WAN リンク

   - **IS Inter-Site** 2 つのネットワーク サイト間の WAN リンク

   - **R 地域間** 2 つのネットワーク地域間の WAN リンク

2. **制限を超えました** 帯域幅の使用率が帯域幅容量を超える WAN リンクでフィルター処理する

3. **重要なレベル** 帯域幅使用率が帯域幅容量の 90% 以上に達した WAN リンクでフィルター処理する

4. **利用が多い** 帯域幅使用率が帯域幅容量の 25% 未満である WAN リンクでフィルター処理する

5. **リンクの種類** 次の WAN リンクの種類でフィルター処理します。

   - **ネットワーク サイトの** 種類

   - **サイト間の** 種類

   - **地域間リンクの** 種類

6. **地域** ネットワーク地域でフィルター処理

次の図は、前述のフィルターを示しています。

名前で **フィルター処理します**。 グラフに表示する必要があるリンクの一覧を選択します。

![BandwidthUtilizationAnalyzer での名前によるフィルター。](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

制限を **超えてフィルター処理します**。 True **を選択** してフィルターを適用します。

![制限を超えてフィルター処理します。](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

クリティカル レベル **でフィルター処理します**。 True **を選択** してフィルターを適用します。

![クリティカル レベルによるフィルター処理。](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

Under で **フィルター処理** True **を選択** してフィルターを適用します。

![Under Utilized によるフィルター。](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

リンクの種類 **でフィルター処理します**。 表示する必要がある種類を選択します。

![リンクの種類によるフィルター。](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

地域で **フィルター処理します**。 リンクを表示する必要がある地域の一覧を選択します。

![地域によるフィルター。](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a>要件

- .NET Framework 3.5

- Microsoft Excel 2010 または Excel 2007

### <a name="summary"></a>概要

Bandwidth Utilization Analyzer は、ネットワーク全体の UC トラフィックの音声帯域幅使用率をプロットするために使用されます。 このツールを使用して、ネットワーク上のビデオ帯域幅の使用状況を報告することもできます。

## <a name="call-parkometer"></a>Call Parkometer
<a name="callpark"> </a>

Call Parkometer は、コール パーク オービット データベースに簡単にアクセスできるコマンドライン アプリケーションです。

### <a name="description"></a>説明

Call Parkometer は、現在パークされている通話を追跡するツールです。 また、オービットとコール パーク サーバー (CPS) の使用状況に関する統計情報も収集します。 このコマンド ライン ツールは、ローカルまたはリモート接続されたコンピューターから CPS オービット SQL Serverに対する読み取りおよび書き込みアクセスの両方を提供します。

すべてのオプションは相互に排他的です。 コマンド ライン構文は次のとおりです。

- **-o パラメーター** - このプールに構成されているオービット範囲の一覧を表示します。

- **-n パラメーター** - このプールで現在使用されているオービットの一覧を表示します。 表示される情報は次のとおりです。

  - パークインとパークの SIP Uniform Resource Identifier (URI)。

  - 通話がパークされる CPS のホスト名。

  - 通話がパークされた時刻のタイム スタンプ。

- **-f パラメーター** - プール内の現在空きオービットの数を一覧表示します。

- **-r \<n\>** パラメーター — 最後にパーク \<n\> された通話を一覧表示します。 表示される情報は次のとおりです。

  - パーク先 SIP URI。

  - Parker SIP URI。

  - 通話がパークされた CPS のホスト名。

  - 呼び出しが取得または破棄された時刻のタイム スタンプ。

- **-t \<n\>** パラメーター - 割り当てられたオービット番号のランダム性を示す、データベース内のオービットの予約をテストします。

### <a name="output"></a>出力

Call Parkometer は、コマンド プロンプトで指定された入力パラメーターに応じて、次の出力を表示します。

- このプールに対して構成されているオービット範囲すべて

- 現在パーク中の通話

- 空き (使用可能な) オービットの数

- 最近パークされた通話

- 均一なオービット値とランダム オービット値をテストする目的で予約されたオービット

### <a name="purpose"></a>用途

CPS ツールの目的は、CPS データベースへのコマンド ライン アクセスを提供します。 管理者は、CPS の使用状況を表示し、プールに割り当てられているオービットの数を確認できます。

### <a name="requirements"></a>要件

CPS を実行しているのと同じコンピューターでこのツールを実行する場合、要件はありません。 このツールをリモート コンピューターで実行する場合は、Skype for Business Server 2015 で使用される SQL Server データベースがリモート アクセスを許可するように構成されている必要があります。 Call Parkometer は、プールのSQL Server接続するためのデータベース接続文字列を使用して構成する必要SQL Server。 このSQL Serverデータベース接続文字列は、構成ファイルで定義されています。parkometer.exe.config。 **** このディレクトリは、このディレクトリと同じディレクトリparkometer.exe配置する必要があります。 次の XML ファイルは、次の例parkometer.exe.config。構成する必要があるパラメーターは、ユーザー名 (mydomain\Administrator など)、パスワード (mypassword など)、ホスト名 (myserver など) です。

```xml
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

展開されたオービット範囲: -o パラメーターは、次に示すように、このプールに構成されているオービット範囲の一覧を表示します。

![Call Parkometer のオービット範囲。](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

現在パークされている通話: -n パラメーターは、次に示すように、このプールで現在使用されているオービットの一覧を表示します。

![Call Parkometer で現在パークされている通話。](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

空きオービットの数: -f パラメーターは、プール内で現在空きオービットの数を次のように一覧表示します。

![Call Parkometer のフリー オービット。](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

最近パークされた通話: -r パラメーターは、次に示すように、最後にパーク \<n\> \<n\> された通話を一覧表示します。

![Call Parkometer で最近パークされた通話。](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

オービット予約のテスト: -t パラメーターは、次に示すようにデータベース内のオービット \<n\> の予約をテストします。

![Call Parkometer でオービット予約をテストします。](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a>概要

Call Parkometer は、コール パーク サーバーに関する詳細情報を提供するコマンドライン ツールです。

## <a name="dbanalyze"></a>DBAnalyze
<a name="dba"> </a>

### <a name="description"></a>説明

DBAnalyze は、管理者が Skype for Business Server 2015 データベースに関する分析レポートを収集するのに役立つコマンドライン ツールです。 DBAnalyze には、診断、ユーザー データ、会議、MCUs、ディスク断片化のモードがあります。

- **診断モード** テーブルに関する情報を含むレポートを作成します (レコード数、 断片化、データ サイズ、およびログ ファイルのサイズ、データとログ ファイルのサイズ、最後のバックアップ時間、Microsoft Office Communications Server を実行しているサーバー間の連絡先の分散、アクセス許可の平均数、連絡先、コンテナー、サブスクリプション、公開、ユーザーごとのエンドポイント、不適切にホームに入っているユーザー、ルーティングできないユーザー、ユーザーごとに開催された会議の平均数、スケジュールされた会議、アクティブな会議、およびデータベース のバージョン。

    > [!NOTE]
    > 診断モードを実行すると、サーバーのパフォーマンスに影響を与える可能性があります。

- **ユーザー データ モード** 指定したユーザーの連絡先、コンテナー、サブスクリプション、発行、アクセス許可、および連絡先グループのデータ、または連絡先リストとアクセス許可リストにそのユーザーを持つユーザーのデータを報告します。 このモードでは、ユーザーが開催または招待された会議の概要データも報告されます。

- **会議モード** 特定の電話会議の詳細データを報告します。たとえば、会議のすべてのスケジュール時の詳細、招待者リスト、会議で許可されるメディアの種類のリスト、アクティブな MCUs (マルチポイントコントロール ユニット)、アクティブな参加者リスト、各参加者の信号状態が含されます。

- **会議 ID のデコード****/pstnid** スイッチで指定されているが、詳細情報についてはバック エンドに接続しない公衆交換電話網 (PSTN) 会議 ID をデコードします。

- **会議を解決する****/pstnid** スイッチで指定された PSTN 会議 ID をデコードし、ID で示される会議に関する情報を表示します。

- **MCUs モード** プール内の各 MCU の ID、メディアの種類、URL、ハートビートの状態、会議の負荷、および参加者の負荷を報告します。

- **ディスク断片化モード** すべてのディスクの断片化状態を表示します。

このツールは、さまざまな問題を診断したり、管理者が容量計画を行うのを支援したりするために使用できます。 たとえば、サーバー A にホームを持つユーザーのほとんどが、サーバー B にホームのユーザーを連絡先として選択した場合、管理者はサーバー A のユーザーをサーバー B に移動して、サーバー間のトラフィックを削減できます。

### <a name="output"></a>出力

このツールは、Skype for Business Server 2015 データベースに関する定義済みのレポートを出力します。 **パス**: %ProgramFiles%\Skype for Business Server 2015\Reskit

### <a name="purpose"></a>用途

このファイルDbanalyze.exeローカル フォルダーにコピーし、ツールを実行します。 ツールを使用するには、コマンド ラインから次のコマンドを実行します。 `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` コマンド ライン オプションの説明を以下に示します。

![コマンド ライン オプションDbanalyze.exe。](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a>要件

 **コンピューター** DBAnalyze は、Skype for Business Server 2015 がインストールされているドメインに参加しているコンピューターからのみ実行できます。

 **ネットワーク** コンピューターは、バック エンド データベースに接続できる必要があります。

 **ソフトウェア** DBAnalyze を実行する前に、Skype for Business Server 2015 ソフトウェア コンポーネントをインストールする必要があります。

 **ユーザー** 次の表に、Skype for Business Server 2015 データベースにアクセスするために必要なアクセス許可を持つ管理者を示します。

![アクセス許可の表Dbanalyze.exe。](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> **/report:disk モードにはローカル管理者アカウントが必要** です。

### <a name="examples"></a>例

有効なコマンドの例を次Dbanalyze.exeします。

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a>概要

DBAnalyzer を使用すると、管理者は Skype for Business Server 2015 データベースを迅速かつ簡単に分析できます。

## <a name="import-storage-service-data"></a>ストレージ サービス データのインポート
<a name="Issd"> </a>

ImportStorageServiceData リソース キット ツールを使用すると、記憶域サービス (LYSS) からフラッシュされたキューとエンドポイントのデータをストレージ サービスに再インポートできます。

### <a name="description"></a>説明

記憶域サービスからフラッシュされたデータは、キュー アイテムの状態またはデータベース サイズに基づいて自動 (定期的) に実行された可能性があります。 これは、プール フェールオーバー コマンドレットの手動呼び出し、または StorageServiceFullFlush コマンドレット (プール フェールオーバー コマンドレットが呼び出すコマンドレット) が原因で発生した可能性があります。 フロントエンドのストレージ サービス (LYSS) データベース のサイズが通常のレベルを超える場合は、データを再インポートしない方が理想的です。そうすると、エクスポートされるデータが多いだけなので注意してください。さらに、記憶域サービス キューの拡大の原因となるエラーの原因となる可能性がある問題は、最初に解決する必要があります (Exchange エンドポイントエラー、ネットワークの問題、その他の問題など)。

 **シナリオ 1:** プールのフェールオーバー中に、各フロントエンドのストレージ サービスからファイルがフラッシュされる場合があります。 フェールオーバーが完了したら、ツールを実行してデータを再インポートする必要があります。

 **シナリオ 2:** データが毎日自動的にフラッシュされる、または記憶域サービス データベースが特定のサイズしきい値を超えた場合 (たとえば、60%、80%、90% いっぱい)。 この自動フラッシュされたデータは、管理者が定期的に再インポートする必要があります。 上記の状況では、監視 SCOM パックが展開されていない場合、ストレージ サービスからフラッシュされるデータに関連する Skype for Business Server Storage Service のイベントがあります。 32075 (フル フラッシュ操作が開始)、32076 (完全フラッシュが完了)、32082 (メンテナンス レベルフラッシュが開始)、32083 (メンテナンス レベルフラッシュが完了)、32089 (データベースの満たのためにフラッシュが発生しました) のイベント ID。 これらのイベント ID は RTM リリースに対応しています。 管理者がこれらのイベントを見た場合、フラッシュされたファイルがあるという意味です。このデータは、このツールを使用して定期的にインポートし戻す必要があります (たとえば、1 週間に 1 回)。

Online Service リリースでは、Skype for Business Server の正常性監視 SCOM パックが展開されている場合、フラッシュされたデータを記憶域サービスに再インポートする必要がある新しいアラートが発生する可能性があります。 通知をトリガーしたフロントエンド サーバーのイベント ログに、対応するイベントがあります。 このイベントには、フラッシュされたデータ ファイルが置かれる親パスの説明と、警告条件を満たすファイルの数が示されます。 警告の条件は、特定の親パスの下に、少なくとも Y 日間の古い X 以上のファイルが含まれます (ここで、X と Y は StorageService 内で事前に設定されますが、APPCONFIG ファイルを変更することで上書きできます)。正常性アラートをトリガーできるイベントの 2 つの例を以下に示します。違いは親パスです。 1 つの可能性は Web サービス ファイル共有の下にありますが、もう 1 つの可能性は各フロントエンドのローカル アプリケーション データ ディレクトリです。 ( c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService など)。 管理者は、この再キット ツールを実行します。

このツールは、ツールが実行されるフロントエンドによってデータが所有されていない場合に、実行中のフロントエンドと他のフロントエンドの CPU と IO の負荷を増加します。 このツールは、フロントエンドの CPU 負荷と IO 負荷が高くない場合 (ピーク時間外など) に実行することをお勧めします。 2 番目に、このツールは 2 ~ 3 分で 1 つのデータ ファイルをインポートできます。 ツールの実行時間を見積もる場合は、この問題に念頭に置いておきます。 ツールによって生成された詳細ログ ファイルは、既定でファイル ストアに表示されます。 ログ ファイルには数十 MB 以上のエラーが報告されていない場合に削除します。

![記憶域サーバーのイベント ログ イベントのサンプル。](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a>要件

Skype for Business Server 2015 リソース キット ツールをインストールします。 このツールは、Skype for Business Server と Skype for Business Server 管理シェルがインストールされているドメインに参加しているコンピューターで実行されます。 このツールは、管理シェルのコマンドレットを使用して、プール内のすべてのフロントエンド サーバーを識別します。 次に **、RtcLocal** データベースがインストールされているプール内のコンピューターからツールを実行する必要があります。 このデータベースは、プールの WEBSERVICE ファイル共有の場所を取得するためにツールによって使用されます。 さらに、このツールを使用する前に、各フロントエンド サーバーは、まず、各フロントエンド サーバーと、ツールの実行に使用するコンピューターで **Enable-PSRemoting** を使用して Windows PowerShell リモート処理を有効にする必要があります。 そうしないと、このWindows PowerShellのリモート コマンドは失敗します。 Windows PowerShell後、プール内のすべてのフロントエンド サーバーでリモート処理をオフにできます。 最後に、ツールを呼び出すアカウントまたは資格情報に、このツールを実行しているプールの Web サービス ファイル共有に対する読み取り/書き込みアクセス許可が必要です。 そうしないと、ツールは IO アクセス許可エラーで失敗します。

> [!NOTE]
> Windows Server 2008 Windows Server 2012ではWindows PowerShellリモート処理は既定で有効になっていますが、Windows Server 2008 オペレーティング システムでは有効になっていません。

### <a name="examples"></a>例

```console
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

LCSSync ツールは、複数フォレスト環境に Skype for Business Server 2015 通信ソフトウェアを展開するのに役立ちます。 このツールは、Active Directory ドメイン サービス連絡先オブジェクトとして、異なるユーザー フォレストのユーザーとグループを、Skype for Business Server 2015 がインストールされている中央フォレストに同期するために使用されます。

### <a name="description"></a>説明

 LCSSync は、中央フォレスト内の同期された Active Directory ドメイン サービス連絡先オブジェクトを使用して、Skype for Business Server のユーザーを有効にします。 シングル サインインを提供するには、プライマリ ユーザー アカウントを、Skype for Business Server 2015 の中央フォレストの Active Directory ドメイン サービス連絡先オブジェクトにマップする必要があります。 このツールは、そのマッピングの実行に役立ちます。 このツールは、Microsoft Identity Integration Server で管理エージェントを作成するためのテンプレートを提供します。

### <a name="summary"></a>概要

LCSSync ツールは、複数フォレスト環境に Skype for Business Server 2015 を展開するのに役立ちます。

## <a name="lookup-user-console"></a>ユーザー コンソールを参照する
<a name="LUC"> </a>

LookupUserConsole ツールは、特定のユーザーに関する内部 Skype for Business Server ルーティング情報を表示します。 この情報は、展開とルーティングの問題を診断する際に、Microsoft が個人をサポートする際に役立つ場合があります。

### <a name="description"></a>説明

 このLookupUserConsole.exe、SIP アドレスを受け入れ、関連する内部 Skype for Business Server ルーティング情報の表示を試みるコマンド プロンプトを開きます。 Exit **と入力** して LookupUserConsole ツールを終了します。

### <a name="requirements"></a>要件

Skype for Business Server 2015 リソース キットをインストールします。 このツールは、Skype for Business Server がインストールされているドメインに参加しているコンピューターで実行されます。

### <a name="examples"></a>例

C:\Program Files\Skype for Business Server 2015\ResKit \>LookupUserConsole.exe

```console
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

MSTurnPing ツールを使用すると、Skype for Business Server 2015 通信ソフトウェアの管理者は、音声ビデオ エッジサービスと音声ビデオ認証サービスを実行しているサーバー、およびトポロジ内で帯域幅ポリシー サービスを実行しているサーバーの状態を確認できます。

### <a name="description"></a>説明

MSTurnPing ツールを使用すると、Skype for Business Server 2015 通信ソフトウェアの管理者は、音声ビデオ エッジサービスと音声ビデオ認証サービスを実行しているサーバー、およびトポロジ内で帯域幅ポリシー サービスを実行しているサーバーの状態を確認できます。

このツールを使用すると、管理者は次のテストを実行できます。

1. A/V エッジ サーバー テスト: このツールは、次の手順を実行して、トポロジ内のすべての A/V エッジ サーバーに対してテストを実行します。

   - Skype for Business Server 音声ビデオ認証サービスが開始され、適切な資格情報を発行できるの確認。

   - Skype for Business Server 音声ビデオ エッジ サービスが開始され、外部エッジにリソースを正常に割り当て可能な場合の確認。

2. 帯域幅ポリシー サービス のテスト: このツールは、トポロジ内で帯域幅ポリシー サービスを実行しているすべてのサーバーに対して、次の操作を実行してテストを実行します。

   - Skype for Business Server 帯域幅ポリシー サービス (認証) が開始され、適切な資格情報を発行できる確認。

   - Skype for Business Server 帯域幅ポリシー サービス (コア) が開始され、帯域幅チェックが正常に実行されたことを確認します。

このツールは、トポロジの一部であり、ローカル ストアがインストールされているコンピューターから実行する必要があります。

### <a name="output"></a>出力

ツールは、各操作の結果を出力します。

- **AudioVideoEdgeServer テストを実行** すると、ツールの出力は次のようになります。

  - トポロジで Skype for Business Server 2015 音声ビデオ認証サービスを提供するコンピューターのテスト結果

  - トポロジで Skype for Business Server 2015 音声ビデオ エッジ サービスを提供するコンピューターのテスト結果

- **BandwidthPolicyServer テストを実行** すると、ツールの出力は次のようになります。

  - トポロジで Skype for Business Server 2015 帯域幅ポリシー サービス (認証) を提供するコンピューターのテスト結果

  - トポロジで Skype for Business Server 2015 帯域幅ポリシー サービス (コア) を提供するコンピューターのテスト結果

### <a name="requirements"></a>要件

- このツールは、トポロジ内にローカル ストアがあるコンピューターから実行する必要があります。

- このツールは、ローカル ストアにアクセスできる管理者として実行する必要があります。

### <a name="examples"></a>例

ツール入力の例を次に示します。

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a>概要

このツールは、音声/ビデオおよび帯域幅ポリシー サービスを実行しているサーバーの状態を確認する Skype for Business Server 2015 管理者にとって有益なリソースです。

## <a name="network-configuration-viewer"></a>ネットワーク構成ビューアー
<a name="NCV"> </a>

ネットワーク構成ビューアーは、Skype for Business Server 2015 通信ソフトウェア管理者が、指定された帯域幅容量に基づく音声通話やビデオ通話などのリアルタイム通信セッションを許可するためにプロビジョニングされた企業の通話受付管理 (CAC) ネットワーク トポロジを表示するために使用できます。 Skype for Business Server 2015 管理者は CAC ポリシーを定義します。CAC ポリシーは、Skype for Business Server 2015 と一緒にインストールされる帯域幅ポリシー サービスによって適用されます。

### <a name="description"></a>説明

ネットワーク構成ビューアー (NetworkConfigurationViewer.exe) を使用すると、管理者は次のタスクを実行できます。

- Skype for Business Server 2015 展開の CAC ネットワーク トポロジをグラフィカル形式で読み込み、表示します。

- 帯域幅ポリシー サーバー ログ ファイルから CAC ネットワーク トポロジを読み込み、グラフィカル形式で表示します。

- CAC ネットワーク トポロジを XML 形式でディスクに保存して保存します。

- CAC ネットワーク トポロジ図を JPG または BMP 形式で保存および保存します。

- CAC ネットワーク トポロジ構成データを表示します。

- CAC ネットワーク トポロジをツリー ビュー スタイルで表示します。

- CAC ネットワーク トポロジ リンク (サイト間、地域間、サイト間リンクなど) のカスタム コネクタを定義します。

- CAC ネットワーク トポロジ サイト情報、地域情報、プロビジョニングされた帯域幅ポリシーとネットワーク リンクを表示します。

### <a name="purpose"></a>用途

エンタープライズ CAC ネットワーク トポロジ リンクをグラフィカル インターフェイスで表示します。

### <a name="examples"></a>例

 **Skype for Business Server 2015** 展開からの CAC ネットワーク トポロジの読み込みと表示をグラフィカル形式で行います。Skype for Business Server 2015 管理者は、次の図に示すように、[ネットワーク構成のダウンロード] オプションを使用して、任意の Skype for Business Server 2015 コンピューターに CAC ネットワーク トポロジ構成を読み込み、表示できます。 Skype for Business Server 2015 構成ストアに接続できないコンピューターに展開すると、ツールはこのような構成をダウンロードまたは表示できません。

![ネットワーク構成のダウンロード。](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 帯域幅ポリシー サーバー ログ ファイルから CAC ネットワーク トポロジを読み込み **、グラフィカル形式で表示します。** Skype for Business Server 2015 帯域幅ポリシー サーバーは、CAC ネットワーク トポロジを Skype for Business Server 2015 ファイル共有の場所の下のログ メカニズムの一部として保存します。 Skype for Business Server 2015 の管理者は、次に示すように [Open **Network Configuration]** オプションを使用して、このようなファイルをグラフィカル形式で表示できます。

![帯域幅ポリシー サーバー ログ ファイルを開く。](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

CAC ネットワーク トポロジを XML 形式でディスクに保存して保存します。Skype for Business Server 2015 管理者は、以下に示すように [ネットワーク構成のコピーを保存する] オプションを使用して、CAC ネットワーク トポロジ構成ファイルを XML 形式で保存できます。 保存した構成ファイルは、グラフィカル表示のためにオフラインで使用できます。

![ネットワーク構成を XML ファイルとして保存する。](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

CAC ネットワーク トポロジ図を JPG または BMP 形式で保存および保存する: Skype for Business Server 2015 管理者は、下に示すように 、[ネットワーク構成の保存] 図を画像として保存オプションを使用して、CAC ネットワーク トポロジ構成をグラフィカル形式 (JPG および BMP ファイル形式) で保存できます。

![ネットワーク構成を画像として保存する。](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <strong>CAC ネットワーク トポロジ構成データを表示します。</strong>Skype for Business Server 2015 管理者は、以下に示すように [ネットワーク構成データの表示] オプションを使用して、ネットワーク地域、ネットワーク サイト、帯域幅プロファイル、サイト サブネット IP アドレスなどの関連するネットワーク構成データをテキスト形式で表示できます。

![ネットワーク構成データの表示。](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 **CAC ネットワーク トポロジをツリー ビュー スタイルで表示します。** Skype for Business Server 2015 管理者は、以下に示すように、ツール ウィンドウの左側にあるコントロール パネルを使用して、関連するネットワーク構成データをグラフィカル ツリー ビュー スタイルで表示できます。

![ツリー ビューでのネットワーク構成データの表示。](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 CAC ネットワーク トポロジ リンク (サイト間、地域間、サイト間リンクなど) のカスタム コネクタ **を定義します。** Skype for Business Server 2015 管理者は、以下に示すように[設定] オプションを使用して、CAC ネットワーク構成 WAN リンクのカスタム グラフィカル コネクタを定義できます。 これにより、ネットワーク構成でプロビジョニングされたさまざまな種類のネットワーク リンクを区別できます。

![ツール](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 **CAC ネットワーク トポロジ サイト情報、地域情報、プロビジョニングされた帯域幅ポリシーを表示します。** Skype for Business Server 2015 管理者は、以下に示すオプションを使用して、関連する CAC ネットワーク地域情報、サイト情報、CAC 帯域幅プロビジョニング情報を表示できます。 (たとえば、ネットワーク地域 **またはネットワーク** サイト オブジェクトの [情報] をクリックします)。

![ネットワークのカスタム コネクタの定義。](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a>概要

このツールは、展開用の CAC ネットワーク トポロジをグラフィカル形式で表示する Skype for Business Server 2015 管理者にとって有益なリソースです。

## <a name="response-group-agent-live"></a>Response Group Agent Live
<a name="RGAL"> </a>

応答グループ アプリケーションを使用すると、エージェントは組み込みの Web サービスを使用して有用なリアルタイム情報にアクセスできます。 残念ながら、このデータのグラフィカルビューはアプリケーションの外部では使用できません。 Response Group Agent Live Resource Kit ツールは、他のエージェントの存在など、リアルタイムの Skype for Business 通信ソフトウェア情報によって強化された、この情報にアクセスするためのシンプルでグラフィカルな方法を提供することで、この問題を解決します。

### <a name="description"></a>説明

応答グループ エージェント Live は、サインインおよびサインアウト機能と、応答グループ エージェントにリアルタイム情報 (グループ メンバーシップや現在の通話数など) を提供する Windows アプリケーションです。 これは、(Skype for Business からアクセス可能な) [エージェント グループ] ページの拡張バージョンを意図しています。

### <a name="purpose"></a>用途

応答グループ アプリケーションは着信呼び出しをキューに入れ、エージェント グループにルーティングします。 サービスへの呼び出しに関する情報に基づいた決定を行う場合、エージェントは、エージェント グループに関するリアルタイムの情報 (使用可能な他のエージェントや各キューで待機している通話の数など) にアクセスできます。 この情報は、最初は応答グループ サービスを通じてのみアクセス可能で、Response Group Agent Live によって直感的な方法で利用できます。

#### <a name="features"></a>機能

応答グループ エージェント Live ツールは、応答グループ サービスと Skype for Business Server 2015 SDK 上に構築されています。 応答グループ エージェントは、応答グループ サービスから利用できる情報と機能 (グループ メンバーシップ、他のエージェントの存在、待機中の通話数など) を提供します。

次の図は、Response Group Agent Live のメイン インターフェイスを示しています。

![応答グループ エージェント Live ツール。](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

Response Group Agent Live のエージェントには、次の 3 つの主な機能があります。

- **サインイン/サインアウト:** [エージェント グループ] ページ (Skype for Business Server 2015 からアクセス可能) とは異なって、Response Group Agent Live では、エージェントだけが一度にすべてのエージェント グループにサインインまたはサインアウトできます。 このアプリケーションは、エージェントがサインインまたはサインアウトするための 3 つの簡単な方法を提供します。

  - アプリケーション内の [サインイン/サインアウト] (緑と赤) ボタンをクリックします。

  - システム トレイ アイコンを右クリックし、サインインまたはサインアウトを選択します。

  - 構成可能なキーボード ショートカットの使用。

- **グループ メンバーシップ:** エージェント グループが選択されている場合、Response Group Agent Live は、このグループ内のエージェントの一覧を右側のウィンドウに表示します。 このアプリケーションと同じコンピューター上で Skype for Business Server 2015 を実行している場合、プレゼンス情報と連絡先カードが Response Group Agent Live に表示されます。 エージェントは、IM を送信したり、そこから直接他のエージェントを呼び出したりできます。

- **リアルタイム統計情報:** Response Group Agent Live は、すべてのエージェント グループのリアルタイム統計情報を提供します。 更新頻度は 1 分です。 応答グループが通話に応答すると、現在キューに入っている通話数のグループ名の横に視覚的なインジケーターが追加されます。 ポインターをグループの上に一時停止すると、最長の待機時間も表示されます。

### <a name="requirements"></a>要件

Response Group Agent Live には .NET Framework 4.0 が必要です。 さらに、プレゼンスと連絡先カードの機能を利用するには、Skype for Business をローカルにインストール (および実行中) する必要があります。

#### <a name="configuration"></a>構成

Response Group Agent Live は、アプリケーションの [オプション] ダイアログ ボックスを使用して、個々のユーザー設定に合わせてカスタマイズできます。 さらに、管理者は、既定のホスト アドレスを直接編集して、既定のホスト アドレスを定義RGAgentLive.exe.configできます。

次の図は、エージェントがホスト アドレスとショートカット キーの構成に使用できる [オプション] ダイアログ ボックスを示しています。 このダイアログにアクセスするには、メイン インターフェイスの上部にある [オプション] ボタンをクリックします。

![[応答グループ エージェントのライブ オプション] ダイアログ ボックス。](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

応答グループ エージェント Live 構成では、次の 3 つの異なる設定をカスタマイズできます。

- ホスト アドレス: これは通常、エージェントのホーム プールに属する Web プールの FQDN です。 正確な応答グループ サービス アドレスは、この情報からバックグラウンドで自動的に派生します (ホストの後に正しいパスを追加します)。

- ショートカット: サインイン/サインアウトの正確なショートカットをカスタマイズできます。 唯一の制限は、両方のショートカットに (少なくとも別のキーに加えて) "Windows ロゴ" キーを含む必要があるという制限です。

- Windows から開始: Windows で自動的に起動するようにアプリケーションを構成できます。

### <a name="examples"></a>例

次の図は、右側のウィンドウで連絡先を右クリックして、IM を呼び出す方法または別のエージェントに送信する方法を示しています。

![電話を発信する、または IM を送信する。](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

次の図は、Response Group Agent Live がキュー内の現在の通話数と、これらすべての着信呼び出しの中で最も長い待ち時間を表示する方法を示しています。

![キュー情報の表示。](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a>概要

迅速なサインインとサインアウト、グループ メンバーシップ、基本的なリアルタイム統計情報は、応答グループ サービスからアプリケーションの外部でのみ使用できる、興味深い応答グループ エージェント機能です。 応答グループ エージェント Live リソース キット ツールを使用すると、Skype for Business Server 2015 管理者は、迅速かつグラフィカルな方法でタスクを実行できる Windows アプリケーションをエージェントに提供できます。

## <a name="sefautil"></a>SEFAUtil
<a name="SEFAUtil"> </a>

SEFAUtil (セカンダリ内線機能のアクティブ化) は、Skype for Business Server 2015 通信ソフトウェア管理者およびヘルプデスク エージェントが、Skype for Business Server 2015 ユーザーの代わりに委任呼び出し、呼び出し転送、同時呼び出し、チーム呼び出し設定、およびグループ通話ピックアップを構成できるコマンドライン ツールです。 また、管理者は、このツールを使用して、特定のユーザーに対して公開されている通話ルーティング設定を照会することもできます。SEFAUtil ツールを使用すると、管理者は、ユーザーに代わって、呼び出しの転送または同時呼び出しを有効/無効/変更できます。 管理者は、(SIP URI の形式で) ターゲットを指定するか、ユーザーによって既に公開されているターゲットを使用できます。 管理者は、このツールを使用して、ユーザーに代わって代理人またはチーム呼び出しグループ のメンバーを追加または削除することもできます。このツールは Microsoft Unified Communications Managed API (UCMA) 3.0 を基に構築され、管理者は SEFAUtil の中央管理ストアに信頼されたアプリケーションを作成する必要があります。

SEFAUtil (セカンダリ内線機能のアクティブ化) を使用すると、Skype for Business Server 2015 管理者とヘルプデスク エージェントは、Skype for Business Server 2015 ユーザーの代わりに、代理呼び出し、呼び出し転送、同時呼び出し、チーム呼び出しの設定、およびグループ通話ピックアップを構成できます。 また、管理者は、このツールを使用して、特定のユーザーに対して公開されている通話ルーティング設定を照会することもできます。

### <a name="description"></a>説明

現在のバージョンの SEFAUtil は、コマンド ライン ツールのみです。サポートされているグラフィカル ユーザー インターフェイスはありません。 このツールは、Microsoft Unified Communications Managed API (UCMA) 3.0 に基づいて作成されています。 このツールの機能を使用すると、管理者とヘルプデスク エージェントは次の操作を実行できます。

- ユーザーのすべての通話ルーティング設定を表示する (呼び出し転送、委任、同時呼び出し、チーム通話、グループ通話ピックアップを含む)

- 転送設定の有効化/無効化/変更 (宛先と応答なしタイマーを含む)

- 呼び出し転送の即時構成を有効/無効/変更する

- 委任設定を有効/無効/変更する

- チーム呼び出しグループの設定を有効/無効/変更する

    > [!NOTE]
    > Skype for Business Server 2015 SEFAUtil ツールの新機能

- 同時呼び出し設定の有効化/無効化/変更 (宛先を含む)

    > [!NOTE]
    > Skype for Business Server 2015 SEFAUtil ツールの新機能

- グループ通話ピックアップ設定の有効化/無効化/変更

    > [!CAUTION]
    > Skype for Business Server 2015 SEFAUtil ツールの新機能

このツールには、次の制限があります。

- Skype for Business Server プールにホームしているユーザーにのみサポートされます

- 複数のユーザーの通話ルーティング設定の一括編集はサポートされていません

### <a name="output"></a>出力

このツールの現在のバージョンは、コマンド プロンプト ウィンドウでのみ出力を提供します。 詳細については、このドキュメントの後半の「例」セクションを参照してください。

### <a name="purpose"></a>用途

このツールを使用する主なシナリオの一部を次に示します。

- Bob は経営幹部であり、Skype for Business Server テレフォニーに移動されました。 彼は既存の PBX システムに委任を持っています。 Skype for Business Server 2015 への移行の一環として、管理者は既存の委任構成を反映するように Bob のルーティングを構成できます。

- アリスは旅行中で、あるお客様からの重要な電話を期待しているという実感を持っています。 しかし、彼女はホテルにいて、コンピューターにアクセスできません。 彼女はヘルプデスクに電話をかけ、仕事番号に対して行われたすべての通話を携帯電話番号に転送する要求を行います。 ヘルプデスク担当者は、彼女の代わりに構成を行うことができます。

- Joe の仕事番号への電話は、仕事中は常にモバイル ボイスメールに移動します。ただし、他のほとんどの場所では正しく動作するように見える。 ヘルプデスク技術者は Joe のルーティング構成を表示し、Joe が携帯電話に同時呼び出しを構成しているのを検出できます。 技術者は Joe にオフィスでのモバイル対応について尋ね、同時呼び出しルールが原因で、ネットワークのカバレッジが低いときに Joe のモバイル ボイスメールに通話が行き届くと判断できます。

- Mike は Contoso の新入社員で、Skype for Business Server 2015 が有効になっているときに、すべてのメンバーがチーム呼び出し用に構成されている新しいチームに参加しています。管理者は、チーム呼び出しグループ設定を設定して、新しいチーム メンバー全員を含め、さらに、チーム内の各メンバーのチーム呼び出しグループ メンバーとして Mike を追加できます。

- Contoso 社の人事部のカスタマー サービス プラクティスは、最初の呼び出し以降のすべての発信者に対して個人サービスを提供する方法です。 部門のすべてのメンバーが互いに非常に近い場所に座っている場合、チーム呼び出しですべての電話が同時に呼び出されるのは、チームに非常に混乱を与える可能性があります。 チーム メンバーを混乱させずに最適なサービスを提供するために、Skype for Business Server 2015 管理者はグループ通話ピックアップ機能を利用します。 管理者は、すべての部門メンバーをピックアップ グループに追加し、その部門にピックアップ グループ番号と通信します。 Samantha が自分のデスクを不在にした場合、Joe は自分の電話が鳴っているのを見て、自分のデスクから電話に応答します。

### <a name="requirements"></a>要件

SEFAUtil ツールは、信頼されたアプリケーション プールの一部であるコンピューターでのみ実行できます。 UCMA 3.0 をそのコンピューターにインストールする必要があります。 このツールを実行するには、SEFAUtil アプリケーション ID を持つ新しい信頼済みアプリケーションをそのプールに作成する必要があります。

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a>SEFAUtil ツール用の新しい信頼済みアプリケーションの作成

1. SEFAUTil ツールは、信頼されたアプリケーション プールの一部であるコンピューターでのみ実行できます。 必要に応じて、新しい信頼されたアプリケーション プールとしてプールを追加するには、次のコマンドレットを使用して Skype for Business Server 管理シェルを使用します。

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > UCMA 3.0 は、SEFAUtil ツールの実行に使用するコンピューターにインストールする必要があります。

2. 信頼されたアプリケーションは、SEFAUtil ツールのトポロジで定義する必要があります。 SEFAUtil を新しい信頼されたアプリケーションとして定義するには、Skype for Business Server 管理シェルを使用して次のコマンドレットを実行します。

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > 必要に応じて、別のポートを使用できます。
    
    > [!NOTE]
    > プールの FQDN: SEFAUtil アプリケーションをホストするサーバーまたはプールの FQDN (通常、Skype for Business フロントエンド サーバーまたはプール>します)。
    > プール レジストラー FQDN: このアプリケーション プールに関連付けられている Skype for Business フロントエンド サーバーまたはプールの FQDN。
    > プール サイト: このプールがホームであるサイトのサイト ID。

3. トポロジの変更を有効にする必要があります。 トポロジの変更を有効にする場合は、次のコマンドレットを実行して Skype for Business Server 管理シェルを使用できます。

   ```powershell
   Enable-CsToplogy
   ```

4. 必要に応じて、SEFAUtil ツールの実行に使用するサーバーに Skype for Business Server 2015 リソース キット ツールをインストールします (サーバーは信頼されたアプリケーション プールの一部である必要があります)。

5. SEFAUtil が正しく実行されていることを確認します。 これを行うには、管理者特権で Windows コマンド プロンプトからツールを実行し、展開内のユーザーの呼び出し転送設定を表示します。 既定では、ツールは "...\Program Files\Skype for Business Server 2015\Reskit" にあります。 ユーザーの転送設定を表示するには、次のコマンドを使用します。

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    ユーザーの呼び出し転送設定が表示されます。

#### <a name="group-call-pickup"></a>グループ通話ピックアップ

グループ通話ピックアップでは、機能を完全に有効にするためには、Skype for Business Server 2015 で追加の構成が必要です。 ピックアップ グループをユーザーに割り当てる前に、この機能の計画と展開の手順について、グループ通話ピックアップ製品のドキュメントを参照してください。

### <a name="examples"></a>例

#### <a name="display-current-call-handling-settings"></a>現在の通話処理の設定を表示する

次のコマンドは、ユーザーの呼び出し処理を表示します。  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> この例では **、/server スイッチを使用** して、接続する Skype for Business Server を指定します。

 **出力**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a>通話転送/応答なし宛先を設定する

この例では、通話転送/応答なし宛先と呼び出しの遅延を設定します。 ここでは、/server スイッチは提供されません。SEFAUtil は、Skype for Business Server 2015 の自動検出を試行します。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+14255550126@contoso.com;user=phone
```

 **出力**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a>通話転送を直ちに有効にする

この例では、別のユーザーへの転送を直ちに有効にします。

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 **出力**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a>直ちに呼び出し転送を無効にする

この例では、直ちに呼び出し転送を無効にします。

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com /disablefwdimmediate
```

 **出力**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>ユーザーを代理人として追加し、代理人の同時呼び出しを設定する

この例では、ユーザーを代理人として追加し、代理人の同時呼び出しを設定します。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 **出力**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a>代理人の同時呼び出しルールを変更する

この例では、前の例で設定した同時呼び出しルールを遅延呼び出しルールに変更します。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 **出力**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a>代理人を削除する

この例では、代理人を削除します。

> [!NOTE]
> 最後の代理人が削除されると、代理人呼び出しは自動的に無効になります。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 **出力**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>代理人を追加し、委任ルールにCall-Forwardを設定する

この例では、代理人を追加し、委任ルールへの転送を設定します。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 **出力**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>同時呼び出しを有効にして宛先番号を設定する

この例では、同時呼び出しを有効にし、同時呼び出し先番号を設定します。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> 既に同時呼び出しが有効になっているユーザーの同時呼び出し先番号を変更するには、コマンドに /enablesimulring スイッチを付け続ける必要があります。そうしないと、宛先番号は変更されません。

 **出力**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a>同時呼び出しを無効にする

この例では、同時呼び出しを無効にします。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 **出力**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>チーム メンバーを追加してTeam-Callメンバー グループに同時呼び出しTeam-Call設定する

この例では、ユーザーのチーム呼び出しグループにチーム メンバーを追加し、チーム呼び出しグループへの同時呼び出しを有効にしています。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> ユーザーのチーム呼び出しグループにメンバーを追加すると、ユーザーの同時呼び出し設定が自動的にチーム呼び出しグループを同じに切り替えます。

 **出力**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a>グループからメンバーをTeam-Callする

この例では、ユーザーのチーム呼び出しグループのチーム メンバーを削除します。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> 削除されるメンバーがチーム呼び出しグループの唯一のメンバーである場合、チーム呼び出しグループへの同時呼び出しは自動的に無効になります。

 **出力**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a>Delayed Ring をグループにTeam-Callする

この例では、遅延リングをチーム呼び出しグループの時間設定に変更します。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 **出力**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a>有効Team-Call

この例では、特定のユーザーのチーム呼び出しを有効にしています。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> ユーザーのチーム呼び出しグループにメンバーがない場合、チーム呼び出しは有効になりません。

 **出力**

#### <a name="disable-team-call"></a>無効Team-Call

この例では、特定のユーザーのチーム呼び出しを無効にします。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 **出力**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>グループ通話ピックアップを有効にし、ピックアップ グループをユーザーに割り当てる

この例では、ユーザーにピックアップ グループを割り当て、グループ通話ピックアップを有効にしています。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 **出力**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a>グループ通話ピックアップを無効にする

この例では、特定のユーザーのグループ通話ピックアップを無効にします。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> ユーザーのグループ通話ピックアップを無効にした場合、ユーザーに割り当てられたグループ番号は保持されません。 その後、そのユーザーのグループ通話ピックアップを再度有効にする場合は、/enablegrouppickup スイッチを使用してグループ番号を再び割り当てる必要があります。

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a>SYSPrep.ps1
<a name="SYSPrep"> </a>

### <a name="description"></a>説明

SYSPrep.ps1は、Windows Server 2008 Windows PowerShellコンピューターに次の Skype for Business Server 2015 の前提条件をインストールするスクリプトです。

- Microsoft .Net Framework 4.5

- Microsoft SQL Server Express

- Windows Powershell バージョン 3.0

- Visual C++ 2010 再頒布可能パッケージ

- インターネット インフォメーション サーバーの更新プログラム

- Windows Identity Foundation

- Skype for Business Server 2015 Core ファイル

  スクリプト名は Microsoft Windows オペレーティング システムのシステム準備ツールに似ていますが、異なります。 このスクリプトは、Skype for Business Server 2015 に必要な前提条件のみをインストールします。 これらの前提条件をインストールすると、Windows SYSPrep ツールを使用してサーバーのイメージを作成できます。

### <a name="requirements"></a>要件

SYSPrep.ps1 スクリプトを実行する前に、必要なファイルを Windows Server 2008 オペレーティング システム コンピューターのローカル フォルダー **(D:\Setup など)** にコピーする必要があります。 このフォルダーには、Skype for Business Server 2015 ファイルのコピーも含める必要があります。具体的には、次の **Setup.exe。** 必須コンポーネント ファイルは、次の場所からダウンロードできます。


| **前提条件**                                | **Location**                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| Microsoft .Net Framework 4.5  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| Microsoft SQL Server Express 2008 R2  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| Windows Powershell バージョン 3.0  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| Visual C++ 2010 再頒布可能パッケージ  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| インターネット インフォメーション サーバーの更新プログラム  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| Windows Identity Foundation  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| Skype for Business Server 2015 Setup.exe  <br/> | Skype for Business Server 2015 メディアからのコピー  <br/>                   |

### <a name="parameter"></a>パラメーター

**-SetupFolder パラメーターは**、必須コンポーネント ファイルのディレクトリの場所を引数として受け取ります。

### <a name="examples"></a>例

このスクリプトSYSPrep.ps1実行し、Skype for Business Server 2015 の前提条件をインストールするには、管理者特権のコマンド プロンプトから次のコマンドを実行します。

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a>割り当てられていない番号アナウンスの移行
<a name="UNAM"> </a>

割り当てられていない番号アナウンス移行ツールを使用すると、Skype for Business Server 2015 管理者は、アナウンス アプリケーションがサービスを提供する割り当てられていない番号の構成を、移行元の Skype for Business Server またはプールから移行先の Skype for Business Server またはプールに移動できます。

### <a name="description"></a>説明

割り当てられていない番号アナウンス移行ツールは、移行元サーバーまたはプールのアナウンス アプリケーションによってサービスされる割り当てられていない番号の構成を別のサーバーまたはプールに移動する Windows PowerShell スクリプトです。

Unassigned Number Announcements Migration スクリプトを実行すると、次の操作が実行されます。

1. 送信元サーバーまたはプールでホストされているアナウンス アプリケーションの割り当てられていない番号のアナウンスによって使用されるオーディオ ファイルを、移動先のサーバーまたはプールのファイル ストアに移動します。

    > [!NOTE]
    > オーディオ ファイルは、コピー先のプールにコピーされると、ソース プールから削除されます。

2. 送信元サーバーまたはプールでホストされているアナウンス アプリケーション用に構成された割り当てられていないすべてのアナウンスを、送信先サーバーまたはプールに移動します。

3. 送信元サーバーまたはプールでホストされているアナウンス アプリケーションによってサービスが提供される割り当てられていない番号範囲を、送信先サーバーまたはプールに再割り当てします。

スクリプトを正常に実行すると、移動元のサーバーまたはプールでホストされているアナウンス アプリケーションによってサービスが提供された割り当てられていない番号範囲はすべて、移動先のサーバーまたはプールによって同じ構成で処理されます。

### <a name="output"></a>出力

**Move-CsAnnouncementConfiguration** スクリプトは、Skype for Business Server 管理シェル ウィンドウで、移行操作の成功または失敗を実行した場所を示します。

エラーによって操作の実行が中断された場合、移行先に正常に移動された割り当てられていない番号の範囲は、移行先の運用フォームに残り、移行する残りの割り当てられていない番号の範囲も運用フォームのソースに残ります。 構成の残りの部分を完全に移行するには、エラーに対処した後、スクリプトを再実行します。

### <a name="purpose"></a>用途

Unassigned Number Announcements Migration スクリプトは、次の 3 つのシナリオで使用できます。

- **Skype for Business Server の新しいバージョンへの構成設定の移行:** Contoso 社は Skype for Business Server 2015 に移行中であり、移行プロセスの一環として、Skype for Business Server 管理者は、アナウンス アプリケーションがサービスを提供する割り当てられていない番号の構成を Lync Server 2013 展開から新しい Skype for Business Server 2015 展開に移行します。 構成設定を移動するために、Skype for Business Server 管理者は割り当てられていない番号アナウンス移行ツールを使用します。

- **Skype for Business Server 2015 から Lync Server 2013** への展開のロールバック:予期しない要因により、Contoso 社は移行を新しい Skype for Business Server 2015 展開にロールバックする必要があります。 サービスの中断を最小限に抑えるために、Skype for Business Server 管理者は、割り当てられていない番号アナウンス移行ツールを使用して、構成を Skype for Business Server 2015 展開から Lync Server 2013 展開にロールバックします。

- **展開間でのデータの移動:** Contoso 社は、1 つのプールのすべてのサーバーを新しいサーバーに置き換える処理を行っています。 その戦略は、新しい Skype for Business Server 2015 プールを展開し、すべてのデータを古いプールから新しいプールに移動し、古いプールを廃止することです。 新しいプールを展開すると、割り当てられていない番号アナウンス移行ツールを使用して、構成を古いプールから新しいプールに移動します。

#### <a name="requirements"></a>要件

ツールを正常に実行するために必要な主な要件を次に示します。

1. このスクリプトは、Skype for Business Server 管理シェルがインストールされているコンピューターから実行する必要があります。

2. アナウンス アプリケーションは、送信元と送信先の Skype for Business サーバーまたはプールに正常に展開されている必要があります。

#### <a name="move-csannouncementconfiguration-script"></a>Move-CsAnnouncementConfiguration スクリプト

次Move-CsAnnouncementConfigurationスクリプトには、次の表に示す 2 つのパラメーターが必要です。

![Move-CsAnnouncementConfigurationパラメーター。](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a>例

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a>Lync Server 2013 プールから Skype for Business Server 2015 プールへの割り当てられていない番号アナウンス構成の移動

この例では、割り当てられていない番号のアナウンスを送信元プール (Lync Server 2013) から送信先プール (Skype for Business Server 2015) に移動します。

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a>Skype for Business Server 2015 プールから Lync Server 2013 プールへの割り当てられていない番号アナウンス構成の移動

この例では、割り当てられていない番号のアナウンスを送信元プール (Skype for Business Server 2015) から送信先プール (Lync Server 2013) に移動します。

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a>Web Conf Data
<a name="WebConfData"> </a>

Web Conf Data Tool を使用すると、Skype for Business Server 2015 通信ソフトウェアの管理者は、開催者の Web 会議に関連付けられているデータを詳細に制御できます。 シナリオには、タイム スタンプ条件に基づいて特定のユーザーの会議データを削除する機能が含まれます。

### <a name="description"></a>説明

このツールを使用すると、管理者は次の操作を実行できます。

1. 1 人のユーザーに関連付けられているすべての Web 会議データを検索します。

2. 1 人のユーザーに関連付けられているすべての Web 会議データを削除します。

3. 特定の日付より古い 1 人のユーザーに関連付けられているすべての Web 会議データを削除します。

4. 1 人のユーザーがプールから別のプールに移動するときに、そのユーザーに関連付けられているすべての Web 会議データを移動します。

    > [!NOTE]
    > Lync Server 2010 のリソース キット ツールでは、そのユーザーがあるプールから別のプールに移動するときに、1 人のユーザーに関連付けられているすべての Web 会議データの移動がサポートされました。 この機能は **、MoveConferenceData** パラメーターを優先してこのツールから廃止されました。 このパラメーターの詳細については [、Move-CsUser コマンドレットを参照](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) してください。

ツールは、非アクティブな会議の会議データのみを削除します。 アクティブな会議 (またはセッション内の会議) は削除できません。

このツールは、ターゲット ユーザーと同じプール内にあるコンピューターから実行する必要があります。 このツールによって管理されている会議コンテンツ データを持つユーザーは、同じユーザー プールに参加している必要があります。

### <a name="output"></a>出力

このツールは、各操作の結果を出力します。

- クエリが実行された場合、ツールは、そのユーザーが開催者である非アクティブなすべての会議データ フォルダーの一覧を出力します。

- 削除を実行すると、データが削除される会議データ フォルダーの一覧が出力されます。

### <a name="requirements"></a>要件

このツールは、開催者が現在ホームに設定されているのと同じプールで実行する必要があります。

このツールは、コンテンツ ファイル ストアへのアクセス権を持つ管理者特権を使用して実行する必要があります。

### <a name="examples"></a>例

次の表に、パラメーターの一部を例で示します。

![Web Conf Data Tool のパラメーター。](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

上の例は、クエリ コマンドがどのように機能するのか示しています。 このようなコマンドの出力は、このツールの影響を受けるすべての会議コンテンツ フォルダーの一覧になります。

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

削除コマンドの例を次に示します。 削除コマンドを実行すると、このユーザーからすべての非アクティブな会議フォルダーが削除されます。

### <a name="summary"></a>概要

このツールは、会議の会議データを正確に制御する必要がある管理者にとって有益なリソースです。


