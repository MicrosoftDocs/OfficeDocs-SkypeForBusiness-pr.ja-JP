---
title: Skype for Business Server 2015 Resource Kit Tools のドキュメント
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: この記事では、Skype for Business Server 2015 Resource Kit のツールについて説明します。これには、各ツールの目的とその使用例が含まれます。 Skype for Business Server 2015 Resource Kit は、2015 Skype for Business Serverのデプロイと管理を行う IT 管理者にとって、日常的なタスクを容易にするのに役立ちます。 たとえば、Web Conf Data ツールを使用すると、オンライン会議中にユーザーがアップロードするデータを簡単に制御できます。 SEFAUtil ツールを使用して、ユーザーの代理通話の転送と応答を設定できます。 IT 管理者は、これらのツールを使用して、Skype for Business Server 2015 をより効果的に管理することをお勧めします。
ms.openlocfilehash: 83777dbe16e70030b13c07fced716ffbc4d51f35
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675499"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a>Skype for Business Server 2015 Resource Kit Tools のドキュメント

この記事では、Skype for Business Server 2015 Resource Kit のツールについて説明します。これには、各ツールの目的とその使用例が含まれます。 Skype for Business Server 2015 Resource Kit は、2015 Skype for Business Serverのデプロイと管理を行う IT 管理者にとって、日常的なタスクを容易にするのに役立ちます。 たとえば、 **Web Conf Data** ツールを使用すると、オンライン会議中にユーザーがアップロードするデータを簡単に制御できます。 **SEFAUtil** ツールを使用して、ユーザーの代理通話の転送と応答を設定できます。 IT 管理者は、これらのツールを使用して、Skype for Business Server 2015 をより効果的に管理することをお勧めします。

## <a name="installation-of-the-resource-kit-tools"></a>リソース キット ツールのインストール

Skype for Business Server 2015 リソース キットをインストールするには、ダウンロード センターから[OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631)をダウンロードします。

**OCSResKit.msi** を実行して、簡単なインストールを実行します。 .msiでは、**%Program Files%\Skype for Business Server 2015\ResKit** のすべてのツールがインストールされます。 自己完結型の実行可能ファイルであるツールは、このフォルダーにあります。 サポート ファイルも含まれるツールは、独自のサブフォルダーにあります。

## <a name="supported-environments"></a>サポートされている環境

Skype for Business Server 2015 Resource Kit は、Skype for Business Server 2015 に必要な仕様を満たすサーバーにインストールする必要があります。通常は 2015 Skype for Business Server実行に使用されます。

## <a name="resource-kit-tools-overview"></a>リソース キット ツールの概要

Skype for Business Server 2015 リソース キットで提供されるツールの一覧を次に示します。 要件と使用例を含む各ツールの説明については、次のセクションで説明します。

- [ABSConfig](resource-kit-tools.md#ABSConfig)

- [帯域幅ポリシー サービス モニター](resource-kit-tools.md#bpsm)

- [帯域幅使用率アナライザー](resource-kit-tools.md#bua)

- [Parkometer を呼び出す](resource-kit-tools.md#callpark)

- [DBAnalyze](resource-kit-tools.md#dba)

- [サービス データStorageインポートする](resource-kit-tools.md#Issd)

- [LCSSync](resource-kit-tools.md#LCSSync)

- [ルックアップ ユーザー コンソール](resource-kit-tools.md#LUC)

- [MsTurnPing](resource-kit-tools.md#MsTurnPing)

- [ネットワーク構成ビューアー](resource-kit-tools.md#NCV)

- [応答グループ エージェントライブ](resource-kit-tools.md#RGAL)

- [SEFAUtil](resource-kit-tools.md#SEFAUtil)

- [SYSPrep.ps1](resource-kit-tools.md#SYSPrep)

- [割り当てられていない番号のお知らせの移行](resource-kit-tools.md#UNAM)

- [Web Conf データ](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a>ABSConfig
<a name="ABSConfig"> </a>

アドレス帳サービス構成ツール (ABSConfig) は、管理者が Skype for Business Server 2015 でアドレス帳サービスの構成をカスタマイズするのに役立つ管理ツールです。 このツールでは、Skype for Business Server 2015 管理者が既定のアドレス帳サービス設定を復元することもできます。

### <a name="description"></a>説明

ABSConfig は、管理者がアドレス帳サービスに関連するActive Directory Domain Services属性を構成できるようにするグラフィカル ユーザー インターフェイス アプリケーションです。

ツールの主なシナリオは次のとおりです。

- 管理者が Active Directory Domain Services の属性を Skype for Business Server 2015 の属性にマップできるようにする。

- 管理者がアドレス帳サービス ファイルに含める、または除外するActive Directory Domain Services属性を指定できるようにする。

- 管理者が復元できるようにするには、既定のアドレス帳サービス設定を使用します。

ABSConfig ツールは、ABSConfig.exe ファイルを使用して開始できます。 ツールが [属性の **構成**] タブに開きます。このテーブルには、Active Directory Domain Services属性を Skype for Business Server 2015 の属性フィールドにマップし、特定の属性フィルターに基づいてアドレス帳サービス ファイルに含めるユーザーまたは除外するユーザーを指定するオプションがあります。 また、アドレス帳ファイルに含める電話番号の値をカスタマイズするオプションもあります。 **[既定値の復元]** オプションを使用すると、管理者はアドレス帳サービスの設定を既定値に復元できます。

> [!NOTE]
> AD 属性を異なる OC フィールド名に再マッピングすると、アドレス帳ファイルのダウンロードでのみ機能し、アドレス帳 Web クエリではサポートされません。

### <a name="output"></a>出力

ABSConfig は、データベースにアドレス帳サービスの構成を格納します。

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a>用途

ABSConfig を使用すると、2015 アドレス帳サービスSkype for Business Server簡単にカスタマイズできます。

### <a name="requirements"></a>要件

#### <a name="computer"></a>コンピューター

ABSConfig は、Skype for Business Server 2015 がインストールされているドメイン参加済みコンピューターからのみ実行できます。 Skype for Business Server 2015 Enterprise Editionの場合、セットアップ時にアドレス帳サービスが有効になっている任意のFront-End サーバーでこのツールを実行できます。

#### <a name="network"></a>ネットワーク

コンピューターは、Front-End プールとバックエンド データベースに接続できる必要があります。

#### <a name="software"></a>ソフトウェア

ABSConfig ツールを実行する前に、次のソフトウェア コンポーネントをインストールする必要があります。

- Skype for Business Server 2015

#### <a name="users"></a>ユーザー

Skype for Business Server 2015 の展開を更新するために必要なアクセス許可を持つ管理者。

### <a name="examples"></a>例

ABSConfig を開始するには、コマンド プロンプトで **ABSConfig.exe** を入力します。 ABSConfig ツールのユーザー インターフェイスを次に示します。

![ABSConfig.exe ツール。](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a>概要

ABSConfig ツールを使用すると、管理者は、2015 アドレス帳サービスSkype for Business Serverカスタマイズするための簡単で使いやすいツールを提供します。

## <a name="bandwidth-policy-service-monitor"></a>帯域幅ポリシー サービス モニター
<a name="bpsm"> </a>

帯域幅ポリシー サービス モニター ツールは、管理者が次の一覧を表示できるようにすることを目的としています。

1. トポロジで構成されたすべての Skype for Business Server 2015 帯域幅ポリシー サービス (認証とコア)

2. 各サービスが他の帯域幅ポリシー サービスとエッジ サーバーに対して行う接続

3. ネットワーク構成ドキュメントで構成されているすべてのリンクと、各帯域幅ポリシー サービスによって報告されるリアルタイムの帯域幅使用量

### <a name="description"></a>説明

帯域幅ポリシー サービス モニター ツールは、GUI ベースのアプリケーションとして実装されます。 管理者は、PDPMonUI.exeを実行してツールを起動します。

ツールを起動すると、トポロジ内の帯域幅ポリシー サービスの一覧を検出しようとします。 最初の更新が完了すると、ウィンドウの左側にあるウィンドウに、それらが属するクラスターによってグループ化されたサービスの一覧が表示されます。

管理者が特定の帯域幅ポリシー サービスを選択すると、右側のウィンドウにその特定のサービスに関する情報が表示されます。 そのウィンドウには、情報を表示する 2 つのメイン タブもあります。

#### <a name="machine-info-tab"></a>[コンピューター情報] タブ

[ **コンピューター情報** ] タブには、選択された帯域幅ポリシー サービスの詳細と、選択した帯域幅ポリシー サービスから他のサービスに対して行われるすべての接続の一覧と状態が表示されます。

#### <a name="topology-info-tab"></a>[トポロジ情報] タブ

[ **トポロジ情報** ] タブには、ネットワーク構成設定で構成されているすべてのリンクの一覧が表示されます。 リンクごとに、オーディオとビデオの帯域幅容量が表示されます。 さらに、現在使用されている帯域幅が Kbps と容量の割合の両方で表示されます。 このツールでは、カラー コーディングを使用して、容量に近い使用率を持つリンクを強調表示します。これにより、管理者はそのようなリンクをすばやく分離できます。

> [!NOTE]
>  帯域幅ポリシー サービス モニター ツールが構成済みの帯域幅ポリシー サービスのいずれかに接続するときにエラーが発生した場合、[ **コンピューター情報** ] タブと [ **トポロジ情報** ] タブの情報は設定されません。 ただし、ツールは最初に接続する可能性がありますが、その後、サービスへの接続が失われる可能性があります。 このような場合、管理者は古い情報を表示する可能性があります。 管理者は、特定の帯域幅ポリシー サービスに対してデータが最後に更新された日時を確認できる、各タブに **最終更新日** のタイムスタンプがあります。

### <a name="output"></a>出力

コマンド ライン出力はありません。プログラムの出力は、メインのグラフィカル ユーザー インターフェイス (GUI) 内に含まれています。

### <a name="purpose"></a>用途

帯域幅ポリシー サービス モニター ツールの目的は、トポロジで定義されている各帯域幅ポリシー サービスの状態を管理者が表示できるようにすることです。 さらに、管理者は、ネットワーク構成ドキュメントで定義されているすべてのリンクの帯域幅の使用状況をリアルタイムで確認できます。

### <a name="requirements"></a>要件

帯域幅ポリシー サービス モニター ツールは、Skype for Business Server トポロジの一部であるコンピューターで実行する必要があります。

### <a name="summary"></a>概要

帯域幅ポリシー サービス モニター ツールは、トポロジ内のすべての帯域幅ポリシー サービスの状態を調べるため、管理者にとって有益なリソースになる可能性があります。さらに重要なのは、ネットワーク構成設定で定義されているリンクのリアルタイム帯域幅使用率を取得できることです。

## <a name="bandwidth-utilization-analyzer"></a>帯域幅使用率アナライザー
<a name="bua"> </a>

Bandwidth Utilization Analyzer は、エンタープライズ ネットワーク内の WAN リンク間の UC エンドポイントによる帯域幅消費量のさまざまなビューに関するレポートを作成するツールです。 これらのレポートは、現在の帯域幅消費パターンを理解し、帯域幅容量計画を支援するために使用できます。

### <a name="description"></a>説明

Bandwidth Utilization Analyzer は、GUI ベースのアプリケーションとして実装されます。 このツールは、ネットワーク全体のオーディオ使用率に特化したレポートを生成し、容量計画に役立ちます。 また、さまざまなリンクに割り当てられている帯域幅容量についても反復処理します。

### <a name="output"></a>出力

Bandwidth Utilization Analyzer は、システムで構成されているすべての WAN リンクに対して、オーディオの帯域幅容量と使用率のグラフィカル プロットを提供します。

### <a name="purpose"></a>用途

音声とビデオの展開では、エンタープライズ ネットワーク全体のメディア トラフィックの帯域幅使用率の傾向を監視し、理解することが重要です。 帯域幅使用率アナライザー ツールを使用すると、管理者はそのことを実現できます。 このツールは次の処理を行います。

- ネットワーク全体のオーディオ使用率に関する特定のレポートを生成します

- さまざまなリンクに割り当てられている帯域幅容量のより効果的な容量計画とイテレーションに役立ちます

Bandwidth Utilization Analyzer は、帯域幅容量と使用率レポートのグラフィカル プロットを生成できます。次のようになります。

- エンタープライズ ネットワーク内のすべての WAN リンク

- 選択した WAN リンクによってフィルター処理されます。

- リンク容量を超えた WAN リンクによってフィルター処理される

- プロビジョニングされた帯域幅を十分に利用していない WAN リンクによってフィルター処理される

- 重要なレベルに達している WAN リンクでフィルター処理する (WAN リンクの帯域幅容量の 90% を超える帯域幅使用率)

- WAN リンクの種類 (ネットワーク サイト リンク、リージョン間リンク、サイト内のリンク) でフィルター処理される

- ネットワーク リージョンでフィルター処理される

#### <a name="applications"></a>アプリケーション

Bandwidth Utilization Analyzer には、次の 2 つのアプリケーション (ツール) があります。

- **WanLinkLogCollector.exe** このツールを使用すると、ユーザーは必要な情報を入力できます。

- **BandwidthUtilizationAnalyzer.xlsm** Microsoft Excelスプレッドシート ソフトウェア レポートは、WanLinkLogCollector.exeによって自動的に起動されます。 このアプリケーションを使用すると、この記事の後半で説明するように、ユーザーはレポートにフィルターを適用できます。

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a>帯域幅使用率アナライザーを使用するフェーズ

Bandwidth Utilization Analyzer を使用する場合、次の 2 つのフェーズがあります。

- WanLinkLogCollector.exeを使用して実行されるログを収集する

- BandwidthUtilizationAnalyzer.xlsm を使用して実行されるレポートをカスタマイズする

  > [!IMPORTANT]
  > BandwidthUtilizationAnalyzer.xlsm をエンド ユーザーが手動で起動しないことを強くお勧めします。

#### <a name="starting-bandwidth-utilization-analyzer"></a>帯域幅使用率アナライザーの開始

コマンド プロンプトまたはWindows エクスプローラーを使用してWanLinkLogCollector.exeを開始します。

 **WanLinkLogCollector.exeの使用**

WanLinkLogCollector.exeを使用するには、次の 3 つの手順があります。

1. **タイムラインを記録する** レポートを生成する必要があるタイムラインを指定します。

2. **ファイル ディレクトリを指定する** ファイルの場所情報を指定する

3. **ログを収集し、レポート ビューアーを起動する** コマンドを実行してレポートを生成する

#### <a name="step-1---log-the-timeline"></a>手順 1 - タイムラインを記録する

タイムラインをログに記録すると、ツール ユーザーは次の図に示すように次を指定できます。

1. **開始日** これは、レポートが生成されるタイムラインの開始日です。たとえば、2010 年 8 月 1 日です。

2. **終了日** これは、レポートの生成対象となるタイムラインの終了日です。たとえば、2010 年 9 月 30 日です。

     ![帯域幅使用率 A の開始日と終了日。](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a>手順 2 - ファイル ディレクトリを指定する

次のファイル ディレクトリは、次のようにユーザーが指定できます。

- **サーバー ログ ファイルの場所** 帯域幅ポリシー サーバー ログが格納されるフォルダーの場所。 これは通常 \<fileserver\>\\ 、FE\>\AppServerFiles\PDP の<選択にあります。

- **一時ファイルストレージの場所** レポートの生成中に中間ファイルが格納される一時ファイルの場所。

  ![帯域幅使用率の分析のファイル ディレクトリ。](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

  > [!NOTE]
  > サーバー ログと一時ファイル ストア フォルダーへの十分なファイル アクセスがツール ユーザーに提供されていることを確認します。

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>手順 3 - ログを収集し、レポート ビューアーを起動する

ログを収集してレポート ビューアーを起動するには、次に示すように [ **実行** ] をクリックします。 この手順では、必要なデータを収集します。

![帯域幅使用率の分析でデータを収集する。](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

入力の検証が成功すると、次のメッセージが表示されます。

![Bandwidth Utili で収集された通知をログに記録します。](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

[**OK**] をクリックします。 BandwidthUtilizationAnalyzer.xlsm が自動的に開始されます。 メッセージ ボックスの指示に従います。 詳細については、次のセクションの **「BandwidthUtilizationAnalyzer.xlsm の使用** 」を参照してください。


### <a name="using-bandwidthutilizationanalyzerxlsm"></a>BandwidthUtilizationAnalyzer.xlsm の使用

1. BandwidthUtilizationAnalyzer.xlsm が自動的に開始されたら、次に示すように **[更新** ] をクリックします。

     ![BandwidthUtilizationAnalyzer.xlsm。](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. ファイル フォルダーを開いたら、次に示すように、メッセージ ボックスで指定された場所からconsolidated.csvを選択します。 また、場所は **C:\Temp** と表示されます。

     ![BandwidthUtilizationAnalyzer でフォルダーを開きます。](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. [**インポート**] をクリックします。

4. グラフィカル プロットが自動的に生成されます。 これは、バックグラウンドで作業しているポインターが消えたときに使用できます。

     ![レポート ビューでフィルターを適用する。](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a>レポート ビューにフィルターを適用する

次に示すように、レポート ビューに適用できるフィルターを次に示します。

![レポート ビューでフィルターを適用する。](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. **名前** WAN リンクでフィルター処理します (フィルターはグラフの右側にあります)。 プレフィックスは、次のリンクの種類を表します。垂直 (青) ボックスを参照してください。

   - **S サイト** ネットワーク サイトからネットワーク リージョンへの WAN リンク

   - **IS サイト間** 2 つのネットワーク サイト間の WAN リンク

   - **R リージョン間** 2 つのネットワーク リージョン間の WAN リンク

2. **制限を超えました** 帯域幅使用率が帯域幅容量を超える WAN リンクでフィルター処理する

3. **重要なレベル** 帯域幅使用率が帯域幅容量の 90% 以上に達した WAN リンクでフィルター処理する

4. **使用率が低い** 帯域幅使用率が帯域幅容量の 25% 未満である WAN リンクでフィルター処理する

5. **リンクの種類** 次の WAN リンクの種類でフィルター処理します。

   - **ネットワーク サイトの** 種類

   - **サイト間の** 種類

   - **リージョン間リンクの** 種類

6. **地域** ネットワーク リージョンでフィルター処理する

次の図は、前述のフィルターを示しています。

名前でフィルター処理 **します**。 グラフに表示する必要があるリンクの一覧を選択します。

![BandwidthUtilizationAnalyzer の名前によるフィルター処理。](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

**超過制限** でフィルター処理します。 True **を** 選択してフィルターを適用します。

![超過制限によるフィルター処理。](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

**重要なレベル** でフィルター処理します。 True **を** 選択してフィルターを適用します。

![クリティカル レベルによるフィルター処理。](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

**[使用中]** でフィルター処理します。 True **を** 選択してフィルターを適用します。

![[使用中] でフィルター処理します。](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

**リンクの種類** でフィルター処理します。 表示する必要がある種類を選択します。

![リンクの種類によるフィルター処理。](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

**リージョン** でフィルター処理します。 リンクを表示する必要があるリージョンの一覧を選択します。

![リージョン別のフィルター処理。](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a>要件

- .NET Framework 3.5

- Microsoft Excel 2010またはExcel 2007

### <a name="summary"></a>概要

帯域幅使用率アナライザーは、ネットワーク全体の UC トラフィックのオーディオ帯域幅使用率をプロットするために使用されます。 このツールを使用して、ネットワーク上のビデオ帯域幅の使用率を報告することもできます。

## <a name="call-parkometer"></a>Parkometer を呼び出す
<a name="callpark"> </a>

Call Parkometer は、コール パークオービット データベースに簡単にアクセスできるコマンド ライン アプリケーションです。

### <a name="description"></a>説明

Call Parkometer は、現在パークされている通話を追跡するためのツールです。 また、オービットとコール パーク サーバー (CPS) の使用状況に関する統計情報も収集されます。 このコマンド ライン ツールは、ローカルコンピューターまたはリモート接続されたコンピューターから CPS 軌道SQL Serverデータベースへの読み取りと書き込みの両方のアクセスを提供します。

すべてのオプションは相互に排他的です。 コマンド ライン構文は次のとおりです。

- **-o** パラメーター - このプール用に構成されたすべてのオービット範囲を一覧表示します。

- **-n** パラメーター - このプールで現在使用されているすべてのオービットを一覧表示します。 表示される情報は次のとおりです。

  - PARKEE と parker の SIP Uniform Resource Identifier (URI)。

  - 呼び出しがパークされている CPS のホスト名。

  - 通話がパークされた時刻のタイムスタンプ。

- **-f** パラメーター - プール内の現在空いているオービットの数を一覧表示します。

- **-r \<n\>** パラメーター- 最後に \<n\> パークされた呼び出しを一覧表示します。 表示される情報は次のとおりです。

  - Parkee SIP URI。

  - Parker SIP URI。

  - 呼び出しがパークされた CPS のホスト名。

  - 呼び出しが取得または削除された時刻のタイムスタンプ。

- **-t\<n\>** パラメーター - データベース内の軌道を予約して、割り当てられた軌道番号のランダム性を示すテストを行います。

### <a name="output"></a>出力

コマンド プロンプトで指定された入力パラメーターに応じて、Call Parkometer には次の出力が表示されます。

- このプール用に構成されているすべてのオービット範囲

- 現在パークされている呼び出し

- 空の (使用可能な) 軌道の数

- 最近パークされた通話

- 一定の軌道値とランダムな軌道値をテストするために予約されたオービット

### <a name="purpose"></a>用途

CPS ツールの目的は、CPS データベースへのコマンド ライン アクセスを提供することです。 管理者は、CPS の使用状況を表示し、プールに割り当てられたオービットの数を決定できます。

### <a name="requirements"></a>要件

このツールが CPS を実行しているのと同じコンピューターで実行されている場合、要件はありません。 このツールをリモート コンピューターで実行する場合は、Skype for Business Server 2015 で使用されるSQL Server データベースをリモート アクセスを許可するように構成する必要があります。 プールのSQL Serverに接続するには、SQL Server データベース接続文字列を使用して Call Parkometer を構成する必要があります。 このSQL Serverデータベース接続文字列は、構成ファイル **で定義parkometer.exe.config**。parkometer.exeが配置されているのと同じディレクトリに配置する必要があります。 次の XML ファイルは、parkometer.exe.configの例です。構成する必要があるパラメーターは、ユーザー名 (mydomain\Administrator など)、パスワード (mypassword など)、ホスト名 (myserver など) です。

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

デプロイされたオービット範囲: -o パラメーターには、このプールに対して構成されているすべてのオービット範囲が示されています。

![Call Parkometer のオービット範囲。](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

現在パークされている呼び出し: -n パラメーターは、このプールで現在使用されているすべてのオービットを示すように一覧表示します。

![Call Parkometer で現在パークされている呼び出し。](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

自由軌道の数: -f パラメーターには、次に示すように、プール内の現在空いている軌道の数が一覧表示されます。

![Call Parkometer のフリー オービット。](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

最近パークされた呼び出し: -r \<n\> パラメーターには、次のように最後に \<n\> パークされた呼び出しが一覧表示されます。

![Call Parkometer で最近パークされた呼び出し。](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

テストオービット予約: -t パラメーターは、次に示すように、データベース内の軌道を予約するテストを行います \<n\> 。

![Call Parkometer で軌道予約をテストします。](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a>概要

Call Parkometer は、コール パーク サーバーに関する詳細情報を提供するコマンド ライン ツールです。

## <a name="dbanalyze"></a>DBAnalyze
<a name="dba"> </a>

### <a name="description"></a>説明

DBAnalyze は、管理者が Skype for Business Server 2015 データベースに関する分析レポートを収集するのに役立つコマンド ライン ツールです。 DBAnalyze には、診断、ユーザー データ、会議、MCU、ディスクの断片化というモードがあります。

- **診断モード** テーブル (レコードの数、断片化、データ サイズ、インデックス サイズ)、データ ファイルとログ ファイル サイズ、最後のバックアップ時間、コミュニケーション サーバーを Microsoft Office実行しているサーバー間の連絡先の分散、アクセス許可の平均数、連絡先、コンテナー、サブスクリプション、パブリケーション、ユーザーごとのエンドポイント、不適切にホームされたユーザー、ルーティングできないユーザー、ユーザーに関する情報を含むレポートを作成します。 ユーザーごとに開催される会議の平均数、スケジュールされた会議、アクティブな会議、データベースのバージョン。

    > [!NOTE]
    > 診断モードを実行すると、サーバーのパフォーマンスに影響を与える可能性があります。

- **ユーザー データ モード** 指定したユーザーの連絡先、コンテナー、サブスクリプション、パブリケーション、アクセス許可、連絡先グループのデータ、または連絡先とアクセス許可リストにそのユーザーを持つユーザーを報告します。 このモードでは、ユーザーが整理または招待された会議の概要データも報告されます。

- **会議モード** 会議のすべてのスケジュール時間の詳細、招待者リスト、会議で許可されているメディアの種類の一覧、アクティブな MCU (マルチポイント コントロール ユニット)、アクティブな参加者リスト、各参加者のシグナリング状態など、特定の会議の詳細なデータを報告します。

- **会議 ID をデコードする****/pstnid** スイッチで指定されているが、詳細についてはバックエンドに接続しない公衆交換電話網 (PSTN) 会議 ID をデコードします。

- **会議を解決する****/pstnid** スイッチで指定された PSTN 会議 ID をデコードし、ID で示された会議に関する情報を表示します。

- **MCU モード** プール内の各 MCU の ID、メディアの種類、URL、ハートビートの状態、会議の負荷、および参加者の負荷を報告します。

- **ディスク断片化モード** すべてのディスクの断片化状態を表示します。

このツールは、さまざまな問題を診断したり、管理者が容量計画を支援したりするために使用できます。 たとえば、サーバー A に所属するほとんどのユーザーが、サーバー B に所属するユーザーを連絡先として選択した場合、管理者はサーバー A 上のユーザーをサーバー B に移動して、サーバー間トラフィックを減らすことができます。

### <a name="output"></a>出力

このツールは、Skype for Business Server 2015 データベースに関する定義済みのレポートを出力します。 **パス**: %ProgramFiles%\Skype for Business Server 2015\Reskit

### <a name="purpose"></a>用途

Dbanalyze.exeをインストールするには、ローカル フォルダーにコピーし、ツールを実行します。 ツールを使用するには、コマンド ラインから次のコマンドを実行します。 `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` コマンド ライン オプションの説明を次に示します。

![Dbanalyze.exeのコマンド ライン オプション。](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a>要件

 **コンピューター** DBAnalyze は、Skype for Business Server 2015 がインストールされているドメイン参加済みコンピューターからのみ実行できます。

 **ネットワーク** コンピューターはバックエンド データベースに接続できる必要があります。

 DBAnalyze を実行する前に、**ソフトウェア** Skype for Business Server 2015 ソフトウェア コンポーネントをインストールする必要があります。

 **ユーザー** 次の表は、Skype for Business Server 2015 データベースにアクセスするために必要なアクセス許可を持つ管理者を示しています。

![Dbanalyze.exeのアクセス許可テーブル。](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> **/report:disk** モードでは、ローカル管理者アカウントが必要です。

### <a name="examples"></a>例

有効なDbanalyze.exe コマンドの例を次に示します。

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a>概要

DBAnalyzer を使用すると、管理者は 2015 Skype for Business Serverデータベースをすばやく簡単に分析できます。

## <a name="import-storage-service-data"></a>サービス データStorageインポートする
<a name="Issd"> </a>

ImportStorageServiceData リソース キット ツールを使用すると、Storage サービス (LYSS) からフラッシュされたキューとエンドポイントのデータをStorage サービスに再インポートできます。

### <a name="description"></a>説明

Storage サービスからフラッシュされたデータは、キュー 項目の状態またはデータベース サイズに基づいて自動 (定期的) に送信される可能性があります。 これは、プール フェールオーバー コマンドレットの手動呼び出し、または StorageServiceFullFlush コマンドレット (プール フェールオーバー コマンドレットが呼び出す) が原因で発生した可能性があります。 フロントエンドの Storage Service (LYSS) データベース サイズのいずれかが通常のレベルを超えている場合は、データを再インポートしないことをお勧めします。これは、多くのデータがエクスポートバックされる可能性があるためです。さらに、Storage サービス キューの拡張の原因となった可能性のある問題は、最初に解決する必要があります (エンドポイント エラー、ネットワークの問題、その他の問題Exchangeなど)。

 **シナリオ 1:** プールのフェールオーバー中に、各フロントエンドのストレージ サービスからファイルがフラッシュされる可能性があります。 フェールオーバーが完了したら、ツールを実行してデータを再インポートする必要があります。

 **シナリオ 2:** データは毎日、または特定のサイズのしきい値を超える Storage Service データベースに応答して自動的にフラッシュされます (たとえば、60%、80%、90% がいっぱい)。 この自動的にフラッシュされたデータは、管理者によって定期的に再インポートする必要があります。 上記の状況では、監視 SCOM パックがデプロイされていない場合、Storage サービスからフラッシュされるデータに関連するSkype for Business Server Storage サービスのイベントがあります。 32075 のイベント ID (完全フラッシュ操作が開始されました)、32076 (完全フラッシュが完了しました)、32082 (メンテナンス レベルのフラッシュが開始されました)、32083 (メンテナンス レベルのフラッシュ完了)、32089 (データベースの満杯のためフラッシュが発生しました)。 これらのイベント ID は RTM リリースに対応しています。 管理者がこれらのイベントを表示すると、フラッシュされたファイルがあることを意味します。このデータは、週に 1 回など、このツールを使用して定期的にインポートする必要があります。

Online Service リリースでは、Skype for Business Serverの正常性監視 SCOM パックが展開された場合、新しいアラートが発生する可能性があります。これにより、フラッシュされたデータをStorage サービスに再インポートするよう管理者に求めるメッセージが表示されます。 アラートをトリガーしたFront-End サーバーのイベント ログに対応するイベントがあります。 このイベントでは、フラッシュされたデータ ファイルが配置される親パスと、アラート条件を満たすファイルの数について説明します。 アラートの条件は、特定の親パスの下に少なくとも Y 日間の X ファイルが存在することです (X と Y は StorageService 内で事前設定されていますが、APPCONFIG ファイルを変更することでオーバーライドできます)。正常性アラートをトリガーできる 2 つのイベントの例を次に示します。違いは親パスです。 1 つの可能性は Web サービス ファイル共有の下にあり、もう 1 つは各フロントエンドのローカル アプリケーション データ ディレクトリです。 (例: c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService)。 管理者は、この再キット ツールを実行します。

このツールは、ツールが実行されているフロントエンドによってデータが所有されていない場合に、実行中のフロントエンドとその他のフロントエンドの CPU と IO の負荷を増加させます。 フロントエンドが CPU と IO の負荷が高くない場合 (ピーク時以外など) にこのツールを実行することをお勧めします。 次に、このツールは 1 つのデータ ファイルをインポートするのに 2 ~ 3 分かかります。 ツールの実行時間を見積もる場合は、この点に注意してください。 ツールによって生成された詳細ログ ファイルは、既定でファイル Microsoft Storeに表示されます。 ログ ファイルは数十 MB 以上である可能性があるため、エラーが報告されていない場合は削除します。

![サーバー イベント ログ イベントStorageサンプル。](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a>要件

Skype for Business Server 2015 Resource Kit ツールをインストールします。 このツールは、Skype for Business ServerとSkype for Business Server Management Shell がインストールされているドメイン参加済みコンピューターで実行されます。 このツールでは、管理シェルのコマンドレットを使用して、プール内のすべてのFront-End サーバーを識別します。 次に、 **RtcLocal** データベースがインストールされているプール内のマシンからツールを実行する必要があります。 このデータベースは、プールの WEBSERVICE ファイル共有の場所を取得するためにツールによって使用されます。 さらに、ツールを使用する前に、各Front-End サーバーは、まず、各Front-End サーバーとツールの実行元コンピューターで **Enable-PSRemoting** を使用してWindows PowerShellリモート処理を有効にする必要があります。 それ以外の場合、このツールからのリモート Windows PowerShell コマンドは失敗します。 Windows PowerShellリモート処理は、プール内のすべてのFront-End サーバーの完了後に無効にすることができます。 最後に、ツールを呼び出すアカウントまたは資格情報には、このツールを実行しているプールの Web サービス ファイル共有に対する読み取り/書き込みアクセス許可が必要です。 それ以外の場合、ツールは IO アクセス許可エラーで失敗します。

> [!NOTE]
> Windows Server 2012では、Windows PowerShellリモート処理は既定で有効になっていますが、Windows Server 2008 オペレーティング システムでは有効になっていません。

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

LCSSync ツールは、Skype for Business Server 2015 通信ソフトウェアをマルチフォレスト環境にデプロイするのに役立ちます。 このツールは、Active Directory Domain Services連絡先オブジェクトとして異なるユーザー フォレストのユーザーとグループを、Skype for Business Server 2015 がインストールされている中央フォレストに同期するために使用されます。

### <a name="description"></a>説明

 LCSSync では、中央フォレスト内の同期されたActive Directory Domain Services連絡先オブジェクトを使用して、ユーザーがSkype for Business Serverできるようにします。 シングル サインインを提供するには、プライマリ ユーザー アカウントを 2015 Skype for Business Serverの中央フォレスト内のActive Directory Domain Services連絡先オブジェクトにマップする必要があります。 このツールは、そのマッピングを実行するのに役立ちます。 このツールは、Microsoft Identity Integration Server で管理エージェントを作成するためのテンプレートを提供します。

### <a name="summary"></a>概要

LCSSync ツールは、Skype for Business Server 2015 をマルチフォレスト環境にデプロイするのに役立ちます。

## <a name="lookup-user-console"></a>ルックアップ ユーザー コンソール
<a name="LUC"> </a>

LookupUserConsole ツールには、特定のユーザーに関する内部Skype for Business Serverルーティング情報が表示されます。 この情報は、Microsoft が展開とルーティングの問題を診断する際に個人をサポートするのに役立つ場合があります。

### <a name="description"></a>説明

 LookupUserConsole.exeを実行すると、SIP アドレスを受け入れ、それらに関連する内部Skype for Business Serverルーティング情報を表示しようとするコマンド プロンプトが開きます。 **終了** と入力して LookupUserConsole ツールを終了します。

### <a name="requirements"></a>要件

Skype for Business Server 2015 リソース キットをインストールします。 このツールは、Skype for Business Serverがインストールされているドメイン参加済みコンピューターで実行されます。

### <a name="examples"></a>例

C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe

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

MSTurnPing ツールを使用すると、Skype for Business Server 2015 通信ソフトウェアの管理者は、Audio/Video Edge、オーディオ/ビデオ認証サービス、およびトポロジで帯域幅ポリシー サービスを実行しているサーバーを実行しているサーバーの状態を確認できます。

### <a name="description"></a>説明

MSTurnPing ツールを使用すると、Skype for Business Server 2015 通信ソフトウェアの管理者は、Audio/Video Edge、オーディオ/ビデオ認証サービス、およびトポロジで帯域幅ポリシー サービスを実行しているサーバーを実行しているサーバーの状態を確認できます。

このツールを使用すると、管理者は次のテストを実行できます。

1. A/V Edge Server テスト: このツールは、次の手順を実行して、トポロジ内のすべての A/V エッジ サーバーに対してテストを実行します。

   - Skype for Business Serverオーディオ/ビデオ認証サービスが開始され、適切な資格情報を発行できることを確認します。

   - Skype for Business Server Audio/Video Edge サービスが開始され、外部エッジでリソースを正常に割り当てることができることを確認します。

2. 帯域幅ポリシー サービス テスト: このツールは、次の手順を実行して、トポロジ内の帯域幅ポリシー サービスを実行しているすべてのサーバーに対してテストを実行します。

   - Skype for Business Server帯域幅ポリシー サービス (認証) が開始され、適切な資格情報を発行できることを確認します。

   - Skype for Business Server Bandwidth Policy Service (Core) が開始され、帯域幅チェックを正常に実行できることを確認します。

このツールは、トポロジの一部であり、ローカル ストアがインストールされているコンピューターから実行する必要があります。

### <a name="output"></a>出力

このツールは、各操作の結果を出力します。

- **AudioVideoEdgeServer** テストが実行された場合、ツールの出力は次のとおりです。

  - トポロジで Skype for Business Server 2015 オーディオ/ビデオ認証サービスを提供するコンピューターのテスト結果

  - トポロジで Skype for Business Server 2015 Audio/Video Edge サービスを提供するコンピューターのテスト結果

- **BandwidthPolicyServer** テストが実行された場合、ツールの出力は次のとおりです。

  - トポロジで Skype for Business Server 2015 帯域幅ポリシー サービス (認証) を提供するコンピューターのテスト結果

  - トポロジで Skype for Business Server 2015 Bandwidth Policy Service (Core) を提供するコンピューターのテスト結果

### <a name="requirements"></a>要件

- このツールは、トポロジ内にあり、ローカル ストアを持つコンピューターから実行する必要があります。

- このツールは、ローカル ストアにアクセスできる管理者として実行する必要があります。

### <a name="examples"></a>例

ツール入力の例を次に示します。

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a>概要

このツールは、オーディオ/ビデオおよび帯域幅ポリシー サービスを実行しているサーバーの状態を確認するSkype for Business Server 2015 管理者にとって有益なリソースです。

## <a name="network-configuration-viewer"></a>ネットワーク構成ビューアー
<a name="NCV"> </a>

ネットワーク構成ビューアーは、Skype for Business Server 2015 通信ソフトウェア管理者が使用して、指定された帯域幅容量に基づいて音声通話やビデオ通話などのリアルタイム通信セッションを許可するようにプロビジョニングされた企業の通話受付管理 (CAC) ネットワーク トポロジを表示できます。 Skype for Business Server 2015 管理者は、SKYPE FOR BUSINESS SERVER 2015 と共にインストールされる帯域幅ポリシー サービスによって適用される CAC ポリシーを定義します。

### <a name="description"></a>説明

ネットワーク構成ビューアー (NetworkConfigurationViewer.exe) を使用すると、管理者は次のタスクを実行できます。

- Skype for Business Server 2015 のデプロイから CAC ネットワーク トポロジを読み込んで、グラフィカル形式で表示します。

- 帯域幅ポリシー サーバーのログ ファイルから CAC ネットワーク トポロジを読み込んで表示する (グラフィカル形式)。

- ディスク上の XML 形式で CAC ネットワーク トポロジを保存して保存します。

- CAC ネットワーク トポロジ図を JPG または BMP 形式で保存して保存します。

- CAC ネットワーク トポロジ構成データを表示します。

- ツリー ビュー スタイルで CAC ネットワーク トポロジを表示します。

- CAC ネットワーク トポロジ リンクのカスタム コネクタ (サイト間、リージョン間、サイト間リンクなど) を定義します。

- CAC ネットワーク トポロジ サイト情報、リージョン情報、プロビジョニングされた帯域幅ポリシーとネットワーク リンクを表示します。

### <a name="purpose"></a>用途

グラフィカル インターフェイスでエンタープライズ CAC ネットワーク トポロジのリンクを表示します。

### <a name="examples"></a>例

 **Skype for Business Server 2015 の展開から CAC ネットワーク トポロジをグラフィカル形式で読み込んで表示** します。Skype for Business Server 2015 管理者は、2015 Skype for Business Serverコンピューター **で CAC ネットワーク トポロジの構成を読み込んで表示できます。** 次の図に示すように、ネットワーク構成オプションをダウンロードします。 このツールは、Skype for Business Server 2015 構成ストアに接続されていないコンピューターに展開すると、このような構成のダウンロードまたは表示に失敗します。

![ネットワーク構成のダウンロード。](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 **帯域幅ポリシー サーバー ログ ファイルから CAC ネットワーク トポロジを読み込んで表示するグラフィカル形式:** Skype for Business Server 2015 帯域幅ポリシー サーバーは、2015 年のファイル共有の場所Skype for Business Serverログ メカニズムの一部として CAC ネットワーク トポロジを保存します。 Skype for Business Server 2015 管理者は、次に示すように [**ネットワーク構成を開く]** オプションを使用して、このようなファイルをグラフィカル形式で表示できます。

![帯域幅ポリシー サーバーのログ ファイルを開きます。](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

ディスクに XML 形式で CAC ネットワーク トポロジを保存して保存します。Skype for Business Server 2015 管理者は、次に示すように [ネットワーク **構成のコピーを保存する]** オプションを使用して、CAC ネットワーク トポロジ構成ファイルを XML 形式で保存できます。 保存された構成ファイルは、グラフィカル表示のためにオフラインで使用できます。

![ネットワーク構成を XML ファイルとして保存します。](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

CAC ネットワーク トポロジ図を JPG または BMP 形式で保存およびMicrosoft Storeする: Skype for Business Server 2015 管理者は、次に示すように、[**ネットワーク構成図を図として保存**] オプションを使用して、CAC ネットワーク トポロジ構成をグラフィカル形式 (JPG および BMP ファイル形式) で保存できます。

![ネットワーク構成を図として保存します。](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <strong>CAC ネットワーク トポロジ構成データを表示する:</strong>Skype for Business Server 2015 管理者は、ネットワーク構成データの表示オプションを使用して、ネットワークリージョン、ネットワーク サイト、帯域幅プロファイル、サイト サブネット IP アドレスなどの関連するネットワーク構成データをテキスト形式で表示できます。次に示すようにします。

![ネットワーク構成データの表示。](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 **ツリー ビュー スタイルで CAC ネットワーク トポロジを表示する:** Skype for Business Server 2015 管理者は、次に示すように、ツール ウィンドウの左側にあるコントロール パネルを使用して、関連するネットワーク構成データをグラフィカル ツリー ビュー スタイルで表示できます。

![ツリー ビューでネットワーク構成データを表示する。](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 **CAC ネットワーク トポロジ リンクのカスタム コネクタ (サイト間、リージョン間、サイト間リンクなど) を定義** します。Skype for Business Server 2015 管理者は、次に示す設定 オプションを使用して、CAC ネットワーク構成 WAN リンクのカスタム グラフィカル コネクタを定義できます。 これは、ネットワーク構成でプロビジョニングされるさまざまな種類のネットワーク リンクを区別するのに役立ちます。

![ツール。](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 **CAC ネットワーク トポロジ サイト情報、リージョン情報、プロビジョニングされた帯域幅ポリシーを表示します。** Skype for Business Server 2015 管理者は、次に示すオプションを使用して、関連する CAC ネットワーク 領域情報、サイト情報、および CAC 帯域幅プロビジョニング情報を表示できます。 (たとえば、ネットワーク リージョンまたはネットワーク サイト オブジェクトの **[情報** ] をクリックします)。

![ネットワークのカスタム コネクタを定義する。](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a>概要

このツールは、2015 年の管理者Skype for Business Server、展開の CAC ネットワーク トポロジをグラフィカル形式で表示する場合に役立つリソースです。

## <a name="response-group-agent-live"></a>応答グループ エージェントライブ
<a name="RGAL"> </a>

応答グループ アプリケーションでは、組み込みの Web サービスを使用して、エージェントが有用なリアルタイム情報にアクセスできるようになります。 残念ながら、このデータのグラフィカル ビューはアプリケーションの外部では使用できません。 応答グループ エージェント Live Resource Kit ツールは、この情報にアクセスするためのシンプルでグラフィカルな方法を提供することで、この問題を解決します。他のエージェントの存在など、リアルタイムのSkype for Business通信ソフトウェア情報で強化されます。

### <a name="description"></a>説明

応答グループ エージェント Live は、サインインとサインアウトの機能と、応答グループ エージェントに対していくつかのリアルタイム情報 (グループ メンバーシップや現在の呼び出し数など) を提供するWindows アプリケーションです。 これは、拡張バージョンの [エージェント グループ] ページ (Skype for Businessからアクセス可能) であることを目的とします。

### <a name="purpose"></a>用途

応答グループ アプリケーションは、着信呼び出しをキューに入れ、エージェント グループにルーティングします。 サービスへの呼び出しに関する情報に基づいた決定を行うために、エージェントはエージェント グループに関するリアルタイムの情報にアクセスできます。たとえば、他のエージェントが使用可能であるか、各キューで待機している呼び出しの数などです。 この情報は、最初は応答グループ サービスを介してのみアクセスでき、応答グループ エージェント Live によって直感的な方法で利用できるようになります。

#### <a name="features"></a>機能

応答グループ エージェントライブ ツールは、応答グループ サービスと Skype for Business Server 2015 SDK 上に構築されます。 応答グループ エージェントには、応答グループ サービスから利用できる情報と機能 (グループ メンバーシップ、他のエージェントの存在、待機中の呼び出しの数など) が提供されます。

次の図は、応答グループ エージェント Live のメイン インターフェイスを示しています。

![応答グループ エージェントライブ ツール。](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

応答グループ エージェント Live のエージェントでは、次の 3 つの主な機能を使用できます。

- **サインイン/サインアウト:**[エージェント グループ] ページ (2015 Skype for Business Serverからアクセス可能) とは異なり、応答グループ エージェント Live では、エージェントのみがすべてのエージェント グループに一度にサインインまたはサインアウトできます。 このアプリケーションでは、エージェントがサインインまたはサインアウトするための 3 つの簡単な方法を提供します。

  - アプリケーション内のサインイン/アウト (緑と赤) ボタンをクリックします。

  - システム トレイ アイコンを右クリックし、サインインまたはサインアウトを選択します。

  - 構成可能なキーボード ショートカットを使用する。

- **グループ メンバーシップ:** エージェント グループが選択されると、応答グループ エージェント Live によって、このグループ内のエージェントの一覧が右側のウィンドウに表示されます。 Skype for Business Server 2015 がこのアプリケーションと同じコンピューターで実行されている場合は、プレゼンス情報と連絡先カードが応答グループ エージェント Live に表示されます。 エージェントは IM を送信するか、そこから直接他のエージェントを呼び出すことができます。

- **リアルタイム統計:** 応答グループ エージェント ライブでは、すべてのエージェント グループのリアルタイムの統計情報が提供されます。 更新頻度は 1 分です。 応答グループによって呼び出しに応答すると、キューに登録されている呼び出しの現在の数を持つグループ名の横に視覚的なインジケーターが追加されます。 グループの上にポインターを一時停止すると、最も長い待機時間も表示されます。

### <a name="requirements"></a>要件

応答グループ エージェント Live には、.NET Framework 4.0 が必要です。 また、プレゼンス カードと連絡先カード機能を利用するには、Skype for Businessをローカルにインストール (および実行) する必要があります。

#### <a name="configuration"></a>構成

応答グループ エージェント Live は、アプリケーションの [オプション] ダイアログ ボックスを使用して、個々の設定に合わせてカスタマイズできます。 さらに、管理者は、RGAgentLive.exe.config ファイルの defaultHostAddress プロパティを直接編集することで、既定のホスト アドレスを定義できます。

次の図は、エージェントがホスト アドレスとショートカット キーを構成するために使用できる [オプション] ダイアログ ボックスを示しています。 このダイアログには、メイン インターフェイスの右上にある [オプション] ボタンをクリックしてアクセスします。

![[応答グループ エージェントのライブ オプション] ダイアログ ボックス。](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

応答グループ エージェントのライブ構成では、次の 3 つの異なる設定をカスタマイズできます。

- ホスト アドレス: これは通常、エージェントのホーム プールに属する Web プール FQDN です。 正確な応答グループ サービス アドレスは、この情報からバックグラウンドで自動的に派生します (ホストの後に適切なパスを追加します)。

- ショートカット: サインイン/サインアウトの正確なショートカットをカスタマイズできます。 唯一の制限は、両方のショートカットに "Windows ロゴ" キー (少なくとも別のキーに加えて) を含める必要がある点です。

- Windowsから開始: アプリケーションは、Windowsで自動的に開始するように構成できます。

### <a name="examples"></a>例

次の図は、右側のウィンドウで連絡先を右クリックして IM を呼び出すか、別のエージェントに送信する方法を示しています。

![電話をかけるか、IM を送信します。](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

次の図は、応答グループ エージェント Live がキュー内の現在の呼び出し数と、これらのすべての着信呼び出しの中で最も長い待機時間を表示する方法を示しています。

![キュー情報の表示。](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a>概要

高速サインインとサインアウト、グループ メンバーシップ、および基本的なリアルタイム統計は、応答グループ サービスからアプリケーションの外部でのみ使用できる興味深い応答グループ エージェント機能です。 応答グループ エージェント Live Resource Kit ツールを使用すると、Skype for Business Server 2015 管理者はエージェントにWindows アプリケーションを提供し、タスクを迅速かつグラフィカルに実行できます。

## <a name="sefautil"></a>SEFAUtil
<a name="SEFAUtil"> </a>

SEFAUtil (セカンダリ拡張機能のアクティブ化) は、Skype for Business Server 2015 コミュニケーション ソフトウェア管理者とヘルプデスク エージェントが、Skype for Business Server 2015 ユーザーに代わって代理呼び出し、通話転送、同時呼び出し、チーム通話設定、グループ通話ピックアップを構成できるようにするコマンド ライン ツールです。 また、このツールを使用すると、管理者は、特定のユーザーに対して発行される通話ルーティング設定に対してクエリを実行できます。 SEFAUtil ツールを使用すると、管理者は、通話転送を有効/無効/変更したり、ユーザーに代わって同時に呼び出し音を鳴したりできます。 管理者は、ターゲットを (SIP URI の形式で) 指定することも、ユーザーによって既に公開されているターゲットを使用することもできます。 また、このツールを使用すると、管理者は、ユーザーに代わって代理人またはチームコール グループ メンバーを追加または削除できます。 このツールは、Microsoft Unified Communications Managed API (UCMA) 3.0 を基に構築されており、管理者は SEFAUtil の Central Management ストアに信頼できるアプリケーションを作成する必要があります。

SEFAUtil (セカンダリ拡張機能のアクティブ化) により、Skype for Business Server 2015 の管理者とヘルプデスク エージェントは、2015 Skype for Business Server ユーザーに代わって代理呼び出し、通話転送、同時呼び出し、チーム通話設定、グループ通話ピックアップを構成できます。 また、このツールを使用すると、管理者は特定のユーザーに対して発行される通話ルーティング設定に対してクエリを実行できます。

### <a name="description"></a>説明

SEFAUtil の現在のバージョンは、コマンド ライン ツールにすぎません。サポートされているグラフィカル ユーザー インターフェイスはありません。 このツールは、Microsoft Unified Communications Managed API (UCMA) 3.0 に基づいています。 このツールの機能を使用すると、管理者とヘルプデスク エージェントは次の操作を行うことができます。

- ユーザーのすべての通話ルーティング設定を表示する (通話転送、委任、同時呼び出し、チーム通話、グループ通話ピックアップを含む)

- 通話転送設定を有効/無効/変更する (宛先タイマーと応答なしタイマーを含む)

- 通話転送の即時構成を有効/無効/変更する

- 委任設定を有効/無効/変更する

- チーム呼び出しグループの設定を有効/無効/変更する

    > [!NOTE]
    > Skype for Business Server 2015 SEFAUtil ツールの新機能

- 同時呼び出し設定を有効/無効/変更する (宛先を含む)

    > [!NOTE]
    > Skype for Business Server 2015 SEFAUtil ツールの新機能

- グループ通話ピックアップの設定を有効/無効/変更する

    > [!CAUTION]
    > Skype for Business Server 2015 SEFAUtil ツールの新機能

このツールには、次の制限事項があります。

- Skype for Business Server プールに所属しているユーザーに対してのみサポートされます

- 複数のユーザーの通話ルーティング設定の一括編集はサポートされていません

### <a name="output"></a>出力

このツールの現在のバージョンでは、コマンド プロンプト ウィンドウでのみ出力が提供されます。 詳細については、このドキュメントの後半の「例」セクションを参照してください。

### <a name="purpose"></a>用途

このツールを使用できる主なシナリオの一部を次に示します。

- Bob はエグゼクティブであり、Skype for Business Serverテレフォニーに移行されました。 既存の PBX システムに委任を持っています。 Skype for Business Server 2015 への移行の一環として、管理者は、既存の委任構成を反映するように Bob のルーティングを構成できます。

- Alice は旅行中で、顧客の 1 人からの重要な呼び出しを期待していることに気付きます。 しかし、彼女はホテルにいて、コンピューターにアクセスできない。 彼女はヘルプデスクに電話し、勤務先番号に対して行われたすべての通話を携帯電話番号に転送するよう要求します。 ヘルプデスクの担当者は、彼女に代わって構成を行うことができます。

- Joe の勤務先番号への呼び出しは、仕事中はいつでもモバイル ボイスメールに移動します。ただし、他のほとんどの場所では正常に動作しているように見えます。 ヘルプデスクの技術者は、Joe のルーティング構成を表示し、Joe が自分の携帯電話に対して同時に呼び出し音を構成していることを検出します。 技術者は、自分のオフィスでのモバイル カバレッジについて Joe に問い合わせ、同時呼び出しルールが、ネットワーク カバレッジが低いときに、通話が Joe のモバイル ボイスメールに移動する原因であることを判断できます。

- マイクは Contoso の新入社員であり、2015 年 Skype for Business Serverにチームコールを有効にすると、すべてのメンバーがチーム呼び出し用に構成されている新しいチームに参加します。管理者は、チームコール グループの設定を設定して、すべての新しいチーム メンバーを含め、さらに、管理者は自分のチームの各メンバーのチームコール グループ メンバーとしてマイクを追加します。

- Contoso の人事部門のカスタマー サービスプラクティスは、最初の呼び出し以降のすべての呼び出し元に個人用サービスを提供することです。 部門のすべてのメンバーが互いに非常に近くに座っていることを考えると、チーム呼び出しですべての電話が同時に鳴り響くのは、チームにとって破壊的です。 チーム メンバーを中断することなく最高のサービスを提供するために、Skype for Business Server 2015 管理者はグループ通話ピックアップ機能を利用します。 管理者は、すべての部門メンバーをピックアップ グループに追加し、ピックアップ グループ番号を部署に伝えます。 Samantha がデスクから不在になると、Joe は電話が鳴っているのに気づき、自分の机から電話に応答します。

### <a name="requirements"></a>要件

SEFAUtil ツールは、信頼されたアプリケーション プールの一部であるコンピューターでのみ実行できます。 UCMA 3.0 は、そのコンピューターにインストールする必要があります。 このツールを実行するには、SEFAUtil アプリケーション ID を持つ新しい信頼済みアプリケーションをそのプールに作成する必要があります。

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a>SEFAUtil ツール用の新しい信頼済みアプリケーションの作成

1. SEFAUTil ツールは、信頼されたアプリケーション プールの一部であるコンピューターでのみ実行できます。 必要に応じて、次のコマンドレットを使用して、Skype for Business Server Management Shell を使用して、新しい信頼されたアプリケーション プールとしてプールを追加できます。

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > UCMA 3.0 は、SEFAUtil ツールの実行に使用されるすべてのコンピューターにインストールする必要があります。

2. SEFAUtil ツールのトポロジで信頼されたアプリケーションを定義する必要があります。 SEFAUtil を新しい信頼されたアプリケーションとして定義するには、Skype for Business Server Management Shell を使用して、次のコマンドレットを実行します。

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > 必要に応じて、別のポートを使用できます。
    
    > [!NOTE]
    > プール FQDN: SEFAUtil アプリケーションをホストするサーバーまたはプールの FQDN (通常はSkype for Business フロント エンド サーバー>またはプール)。
    > プール レジストラー FQDN: このアプリケーション プールに関連付けられているSkype for Business フロント エンド サーバーまたはプールの FQDN。
    > プール サイト: このプールがホームになっているサイトのサイト ID。

3. トポロジの変更を有効にする必要があります。 トポロジの変更を有効にするには、次のコマンドレットを実行して、Skype for Business Server Management Shell を使用します。

   ```powershell
   Enable-CsToplogy
   ```

4. 必要に応じて、SEFAUtil ツールの実行に使用される Skype for Business Server 2015 Resource Kit Tools をサーバーにインストールします (サーバーは信頼されたアプリケーション プールの一部である必要があります)。

5. SEFAUtil が正しく実行されていることを確認します。 これを行うには、管理者特権を持つ Windows コマンド プロンプトからツールを実行して、展開内のユーザーの通話転送設定を表示します。 既定では、ツールは "...\Program Files\Skype for Business Server 2015\Reskit" にあります。 ユーザーの通話転送設定を表示するには、次のコマンドを使用します。

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    ユーザーの通話転送設定が表示されます。

#### <a name="group-call-pickup"></a>グループ通話ピックアップ

グループ通話ピックアップでは、機能を完全に有効にするには、Skype for Business Server 2015 で追加の構成が必要です。 ピックアップ グループをユーザーに割り当てる前に、この機能の計画と展開の手順については、グループ通話ピックアップ製品のドキュメントを参照してください。

### <a name="examples"></a>例

#### <a name="display-current-call-handling-settings"></a>現在の呼び出し処理設定を表示する

次のコマンドは、ユーザーの呼び出し処理を表示します。  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> この例では、**/server** スイッチを使用して、接続するSkype for Business Serverを指定します。

 **出力**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a>転送呼び出し先/応答なし宛先を設定する

次の使用例は、着信転送/応答なしの宛先とリング遅延を設定します。 ここでは、/server スイッチは提供されません。SEFAUtil は、Skype for Business Server 2015 を自動検出しようとします。

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

#### <a name="enable-call-forwarding-immediately"></a>通話転送をすぐに有効にする

この例では、別のユーザーへの通話転送をすぐに有効にします。

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

#### <a name="disable-call-forwarding-immediately"></a>通話転送をすぐに無効にする

この例では、通話転送をすぐに無効にします。

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

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>代理人としてユーザーを追加し、デリゲートの同時呼び出しを設定する

この例では、ユーザーをデリゲートとして追加し、デリゲートの同時呼び出しを設定します。

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

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a>デリゲートの同時呼び出しルールを変更する

この例では、前の例で設定した同時呼び出し規則を遅延呼び出し規則に変更します。

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

#### <a name="remove-the-delegate"></a>デリゲートを削除する

次の使用例は、デリゲートを削除します。

> [!NOTE]
> 最後のデリゲートが削除されると、デリゲートの呼び出しは自動的に無効になります。

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

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>デリゲートを追加し、Call-Forwardをデリゲート ルールに設定する

次の使用例は、デリゲートを追加し、デリゲートルールへの呼び出しを設定します。

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

この例では、同時呼び出しを有効にし、同時呼び出し先の番号を設定します。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> 同時呼び出しが既に有効になっているユーザーの同時呼び出し先番号を変更するには、/enableimulring スイッチを使用してコマンドを保持します。それ以外の場合、宛先番号は変更されません。

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

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>Team-Callのチーム メンバーを追加し、Team-Call メンバー グループに同時呼び出しを設定する

この例では、チーム メンバーをユーザーのチーム呼び出しグループに追加し、チーム通話グループへの同時呼び出しを有効にします。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> ユーザーのチーム呼び出しグループにメンバーを追加すると、ユーザーの同時呼び出し設定がチーム呼び出しグループの同時呼び出しに自動的に切り替わります。

 **出力**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a>Team-Call グループからメンバーを削除する

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

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a>遅延リングをTeam-Call グループに設定する

次の使用例は、遅延リングをチーム呼び出しグループ時刻の設定に変更します。

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

#### <a name="enable-team-call"></a>Team-Callを有効にする

この例では、特定のユーザーのチーム呼び出しを有効にします。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> ユーザーのチーム通話グループにメンバーがない場合、チーム通話は有効になりません。

 **出力**

#### <a name="disable-team-call"></a>Team-Callを無効にする

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

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>グループ通話ピックアップを有効にして、ユーザーにピックアップ グループを割り当てる

この例では、ユーザーにピックアップ グループを割り当て、グループ通話ピックアップを有効にします。

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
> ユーザーのグループ通話ピックアップを無効にすると、ユーザーに割り当てられたグループ番号は保持されません。 その後、そのユーザーのグループ通話ピックアップを再度有効にする場合は、/enablegrouppickup スイッチを使用してグループ番号をもう一度割り当てる必要があります。

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a>SYSPrep.ps1
<a name="SYSPrep"> </a>

### <a name="description"></a>説明

SYSPrep.ps1は、Windows Server 2008 オペレーティング システム コンピューターに次のSkype for Business Server 2015 前提条件をインストールするWindows PowerShell スクリプトです。

- Microsoft .NET Framework 4.5

- Microsoft SQL Server Express

- Windows PowerShell バージョン 3.0

- Visual C++ 2010 再頒布可能

- インターネット インフォメーション サーバーの更新プログラム

- Windows Identity Foundation

- Skype for Business Server 2015 Core ファイル

  スクリプト名は Microsoft Windows オペレーティング システムのシステム準備ツールに似ていますが、これらは異なります。 このスクリプトでは、Skype for Business Server 2015 に必要な前提条件のみがインストールされます。 これらの前提条件がインストールされたら、Windows SYSPrep ツールを使用してサーバーのイメージを作成できます。

### <a name="requirements"></a>要件

SYSPrep.ps1 スクリプトを実行する前に、前提条件ファイルを Windows Server 2008 オペレーティング システム コンピューター (**D:\Setup など)** のローカル フォルダーにコピーする必要があります。 このフォルダーには、Skype for Business Server 2015 ファイルのコピー (特に **Setup.exe)** も含める必要があります。 前提条件ファイルは、次の場所からダウンロードできます。


| **前提条件**                                | **Location**                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| Microsoft .NET Framework 4.5  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| Microsoft SQL Server Express 2008 R2  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| Windows PowerShell バージョン 3.0  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| Visual C++ 2010 再頒布可能  <br/>          | <https://support.microsoft.com/en-us/topic/the-latest-supported-visual-c-downloads-2647da03-1eea-4433-9aff-95f26a218cc0>  <br/>  |
| インターネット インフォメーション サーバーの更新プログラム  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| Windows Identity Foundation  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| Skype for Business Server 2015 Setup.exe  <br/> | Skype for Business Server 2015 メディアからコピーする  <br/>                   |

### <a name="parameter"></a>パラメーター

**SetupFolder** パラメーターは、必須ファイルのディレクトリの場所を引数として受け取ります

### <a name="examples"></a>例

SYSPrep.ps1 スクリプトを実行し、Skype for Business Server 2015 の前提条件をインストールするには、管理者特権のコマンド プロンプトから次のコマンドを実行します。

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a>割り当てられていない番号のお知らせの移行
<a name="UNAM"> </a>

割り当てられていない番号のお知らせ移行ツールを使用すると、Skype for Business Server 2015 管理者は、アナウンス アプリケーションによって処理される未割り当ての番号構成を移行元のSkype for Business Serverまたはプールから宛先に移動できます。Skype for Business Serverまたはプール。

### <a name="description"></a>説明

割り当てられていない番号のお知らせ移行ツールは、ソース サーバーまたはプールのアナウンス アプリケーションによって提供される未割り当て番号構成を別のサーバーまたはプールに移動するWindows PowerShell スクリプトです。

実行すると、割り当てられていない番号のお知らせ移行スクリプトは、次の操作を実行します。

1. ソース サーバーまたはプールでホストされているアナウンス アプリケーションの未割り当て番号のお知らせで使用されているすべてのオーディオ ファイルを、移行先サーバーまたはプールのファイル ストアに移動します。

    > [!NOTE]
    > オーディオ ファイルは、コピー先プールにコピーされると、ソース プールから削除されます。

2. 移行元サーバーまたはプールでホストされているアナウンス アプリケーション用に構成されているすべての未割り当て番号のお知らせを移行先サーバーまたはプールに移動します。

3. 移行元サーバーまたはプールでホストされているアナウンス アプリケーションによって処理されるすべての未割り当て番号範囲を宛先サーバーまたはプールに再割り当てします。

スクリプトが正常に実行されると、ソース サーバーまたはプールでホストされているアナウンス アプリケーションによって処理されたすべての未割り当て番号範囲が、移行先サーバーまたはプールによって同じ構成で処理されるようになりました。

### <a name="output"></a>出力

**Move-CsAnnouncementConfiguration** スクリプトは、移行操作の成功または失敗を実行したSkype for Business Server管理シェル ウィンドウで示します。

操作の実行がエラーによって中断された場合、移行先に正常に移動された未割り当て番号範囲は操作形式で宛先に残り、移行する未割り当て番号範囲の残りの部分は運用形式でもソースに残ります。 残りの構成を完全に移行するには、エラーに対処した後でスクリプトを再実行します。

### <a name="purpose"></a>用途

割り当てられていない番号のお知らせ移行スクリプトは、次の 3 つのシナリオで使用できます。

- **構成設定を新しいバージョンのSkype for Business Serverに移行する:** Contoso は 2015 Skype for Business Serverに移行中であり、移行プロセスの一環としてSkype for Business Server 管理者は、アナウンス アプリケーションが提供する未割り当ての番号構成を Lync Server 2013 展開から新しい Skype for Business Server 2015 展開に移動したいと考えます。 構成設定を移動するには、Skype for Business Server管理者が割り当てられていない番号のお知らせ移行ツールを使用します。

- **2015 Skype for Business Serverから Lync Server 2013 への展開のロールバック:** 予期しない要因により、Contoso は新しい Skype for Business Server 2015 展開に移行をロールバックする必要があります。 サービスの中断を最小限に抑えるために、Skype for Business Server管理者は、割り当てられていない番号のお知らせ移行ツールを使用して、Skype for Business Server 2015 展開から Lync Server 2013 展開に構成をロールバックします。

- **デプロイ間でのデータの移動:** Contoso は、1 つのプールのすべてのサーバーを新しいサーバーに置き換えています。 戦略は、新しい 2015 プールSkype for Business Serverデプロイし、すべてのデータを古いプールから新しいプールに移動してから、古いプールを非推奨にすることです。 新しいプールがデプロイされると、未割り当て番号のお知らせ移行ツールを使用して、構成を古いプールから新しいプールに移動します。

#### <a name="requirements"></a>要件

ツールを正常に実行するために必要な主な要件は次のとおりです。

1. このスクリプトは、Skype for Business Server Management Shell がインストールされているコンピューターから実行する必要があります。

2. アナウンス アプリケーションは、サーバーまたはプールのソースと宛先Skype for Business正常にデプロイする必要があります。

#### <a name="move-csannouncementconfiguration-script"></a>Move-CsAnnouncementConfiguration スクリプト

Move-CsAnnouncementConfiguration スクリプトには、次の表に示す 2 つのパラメーターが必要です。

![パラメーターをMove-CsAnnouncementConfigurationします。](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a>例

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a>Lync Server 2013 プールから Skype for Business Server 2015 プールへの割り当てられていない番号のお知らせ構成の移動

この例では、未割り当ての番号のお知らせをソース プール (Lync Server 2013) から移行先プール (Skype for Business Server 2015) に移動します。

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a>Skype for Business Server 2015 プールから Lync Server 2013 プールへの割り当てられていない番号のお知らせ構成の移動

次の使用例は、ソース プール (Skype for Business Server 2015) から宛先プール (Lync Server 2013) に割り当てられていない番号のお知らせを移動します。

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a>Web Conf データ
<a name="WebConfData"> </a>

Web Conf Data Tool を使用すると、Skype for Business Server 2015 通信ソフトウェアの管理者は、開催者の Web 会議に関連付けられているデータをより詳細に制御できます。 シナリオには、タイム スタンプの条件に基づいて特定のユーザーの会議データを削除する機能が含まれます。

### <a name="description"></a>説明

このツールを使用すると、管理者は次の操作を実行できます。

1. 1 人のユーザーに関連付けられているすべての Web 会議データを検索します。

2. 1 人のユーザーに関連付けられているすべての Web 会議データを削除します。

3. 特定の日付より古い 1 人のユーザーに関連付けられているすべての Web 会議データを削除します。

4. そのユーザーが 1 つのプールから別のプールに移動されたときに、1 人のユーザーに関連付けられているすべての Web 会議データを移動します。

  > [!NOTE]
  > Lync Server 2010 用リソース キット ツールでは、そのユーザーが 1 つのプールから別のユーザーに移動されたときに、1 人のユーザーに関連付けられているすべての Web 会議データの移動がサポートされました。 この機能は、 **MoveConferenceData** パラメーターを優先して、このツールから非推奨になりました。 このパラメーターの詳細については、 [Move-CsUser コマンドレットを](/powershell/module/skype/move-csuser?) 参照してください。

このツールは、非アクティブな会議の会議データのみを削除します。 アクティブな会議 (またはセッション内の会議) は削除できません。

このツールは、ターゲット ユーザーと同じプール内にあるコンピューターから実行する必要があります。 このツールによって会議コンテンツ データが管理されているユーザーは、同じユーザー プールに所属している必要があります。

### <a name="output"></a>出力

このツールは、各操作の結果を出力します。

- クエリが実行された場合、ツールは、そのユーザーを開催者として含むすべての非アクティブな会議データ フォルダーの一覧を出力します。

- 削除が実行されると、データが削除されるすべての会議データ フォルダーの一覧がツールによって出力されます。

### <a name="requirements"></a>要件

ツールは、開催者が現在ホームになっているのと同じプールで実行する必要があります。

このツールは、コンテンツ ファイル Microsoft Storeへのアクセス権を持つ管理者特権を使用して実行する必要があります。

### <a name="examples"></a>例

次の表では、パラメーターについて説明します。その一部は例で使用されています。

![Web Conf Data Tool パラメーター。](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

上記の例は、クエリ コマンドの動作を示しています。 このようなコマンドの出力は、このツールの影響を受けるすべての会議コンテンツ フォルダーの一覧になります。

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

前の例は、delete コマンドの例です。 delete コマンドは、このユーザーからすべての非アクティブな会議フォルダーを削除します。

### <a name="summary"></a>概要

このツールは、会議のデータをより正確に制御する必要がある管理者にとって貴重なリソースになる可能性があります。
