---
title: Skype for Business Server 2015 リソースキットツールのドキュメント
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: このトピックでは、Skype for Business Server 2015 リソースキットのツールについて説明します。これらのツールは、各ツールの目的や使用例を含みます。 Skype for Business Server 2015 リソースキットは、Skype for business Server 2015 を展開して管理する IT 管理者にとって、日常的な作業を容易にするのに役に立ちます。 たとえば、Web Conf Data ツールを使用すると、オンライン会議中にユーザーによってアップロードされるデータを簡単に制御できます。 SEFAUtil ツールを使用して、代理人の着信の転送とユーザーへの応答を設定することができます。 IT 管理者は、これらのツールを使用して、Skype for Business Server 2015 をさらに効果的に管理することをお勧めします。
ms.openlocfilehash: ab43d8e951308fab5a4aefc25d9dad2804ea5d0e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005992"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a>Skype for Business Server 2015 リソースキットツールのドキュメント

このトピックでは、Skype for Business Server 2015 リソースキットのツールについて説明します。これらのツールは、各ツールの目的や使用例を含みます。 Skype for Business Server 2015 リソースキットは、Skype for business Server 2015 を展開して管理する IT 管理者にとって、日常的な作業を容易にするのに役に立ちます。 たとえば、 **Web Conf data**ツールを使用すると、オンライン会議中にユーザーによってアップロードされるデータを簡単に制御できます。 **SEFAUtil**ツールを使用して、代理人の着信の転送とユーザーへの応答を設定することができます。 IT 管理者は、これらのツールを使用して、Skype for Business Server 2015 をさらに効果的に管理することをお勧めします。

## <a name="installation-of-the-resource-kit-tools"></a>リソースキットツールのインストール

Skype for Business Server 2015 リソースキットをインストールするには、ダウンロードセンターから[ocsreskit.msi](https://www.microsoft.com/download/details.aspx?id=52631)をダウンロードします。

**Ocsreskit.msi**を実行して、単純なインストールを実行します。 .Msi は、次のパスにあるすべてのツールをインストールします。 **% Program Files%\Skype For Business Server 2015 \ うえ**。 このフォルダーには、自己完結型の実行可能ファイルであるツールがあります。 また、サポートファイルを含むツールは、独自のサブフォルダーに格納されます。

## <a name="supported-environments"></a>サポートされる環境

Skype for Business server 2015 リソースキットは、skype for business server 2015 の実行に使用されているように、通常、skype for business server 2015 に必要な仕様を満たしているサーバーにインストールする必要があります。

## <a name="resource-kit-tools-overview"></a>リソースキットツールの概要

以下に、Skype for Business Server 2015 リソースキットで提供されるツールの一覧を示します。 各ツールの説明 (要件および使用例を含む) については、以下のセクションで説明します。

- [ABSConfig](resource-kit-tools.md#ABSConfig)

- [帯域幅ポリシーサービスモニター](resource-kit-tools.md#bpsm)

- [帯域幅使用率アナライザー](resource-kit-tools.md#bua)

- [コール Par・メータ計](resource-kit-tools.md#callpark)

- [DBAnalyze](resource-kit-tools.md#dba)

- [ストレージサービスデータのインポート](resource-kit-tools.md#Issd)

- [LCSSync](resource-kit-tools.md#LCSSync)

- [参照ユーザーコンソール](resource-kit-tools.md#LUC)

- [MsTurnPing](resource-kit-tools.md#MsTurnPing)

- [ネットワーク構成ビューアー](resource-kit-tools.md#NCV)

- [応答グループエージェント Live](resource-kit-tools.md#RGAL)

- [SEFAUtil](resource-kit-tools.md#SEFAUtil)

- [Sysprep.inf](resource-kit-tools.md#SYSPrep)

- [割り当てられていない番号のアナウンスの移行](resource-kit-tools.md#UNAM)

- [Web Conf データ](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a>ABSConfig
<a name="ABSConfig"> </a>

アドレス帳サービス構成ツール (ABSConfig) は、管理者が Skype for Business Server 2015 でアドレス帳サービスの構成をカスタマイズするのに役立つ管理ツールです。 このツールを使用すると、Skype for Business Server 2015 管理者は、既定のアドレス帳サービス設定を復元することもできます。

### <a name="description"></a>説明

ABSConfig は、管理者がアドレス帳サービスに関連する Active Directory ドメインサービスの属性を構成できるグラフィカルユーザーインターフェイスアプリケーションです。

このツールの主なシナリオは次のとおりです。

- 管理者が Active Directory ドメインサービスの属性を Skype for Business Server 2015 の属性にマップできるようにします。

- 管理者が Active Directory ドメインサービスの属性を指定して、アドレス帳サービスファイルに含めたり除外したりできるようにします。

- 管理者が既定のアドレス帳サービス設定を復元できるようにする。

ABSConfig ツールは、ABSConfig ファイルを使用して開始できます。 ツールが [ **Configure Attributes** ] タブに表示されます。この表には、Active Directory ドメインサービスの属性を Skype for Business Server 2015 の属性フィールドにマップし、特定の属性フィルターに基づいてアドレス帳サービスファイルに含めるまたは除外するユーザーを指定するオプションがあります。 また、アドレス帳ファイルに含める電話番号の値をカスタマイズするためのオプションもあります。 [**既定**の設定に戻す] オプションを使用すると、管理者はアドレス帳サービスの設定を既定値に戻すことができます。

> [!NOTE]
> AD 属性を異なる OC フィールド名に再マッピングすることは、アドレス帳のファイルダウンロードに対してのみ機能し、アドレス帳 Web クエリではサポートされていません。

### <a name="output"></a>出力

ABSConfig は、アドレス帳サービスの構成をデータベースに格納します。

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a>用途

ABSConfig では、Skype for Business Server 2015 アドレス帳サービスをすばやく簡単にカスタマイズすることができます。

### <a name="requirements"></a>Requirements

#### <a name="computer"></a>コンピューター

ABSConfig は、Skype for Business Server 2015 がインストールされているドメインに参加しているコンピューターからのみ実行できます。 Skype for Business Server 2015 Enterprise Edition の場合、このツールは、アドレス帳サービスがセットアップ中に有効になっているすべてのフロントエンドサーバー上で実行できます。

#### <a name="network"></a>ネットワーク

コンピューターは、フロントエンドプールとバックエンドデータベースに接続できる必要があります。

#### <a name="software"></a>ソフトウェア

ABSConfig ツールを実行する前に、次のソフトウェアコンポーネントをインストールする必要があります。

- Skype for Business Server 2015

#### <a name="users"></a>ユーザー

Skype for Business Server 2015 の展開を更新するのに必要なアクセス許可を持つ管理者。

### <a name="examples"></a>例

ABSConfig を開始するには、コマンドプロンプトで**ABSConfig**を入力します。 次に示すのは、ABSConfig tool のユーザーインターフェイスです。

![ABSConfig ツール。](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a>概要

ABSConfig ツールを使用すると、管理者は、Skype for Business Server 2015 アドレス帳サービスをカスタマイズするための簡単なツールを使用することができます。

## <a name="bandwidth-policy-service-monitor"></a>帯域幅ポリシーサービスモニター
<a name="bpsm"> </a>

帯域幅ポリシーサービスモニターツールを使用すると、管理者は以下の一覧を表示できます。

1. トポロジで構成されているすべての Skype for Business Server 2015 帯域幅ポリシーサービス (認証とコア)

2. 各サービスが他の帯域幅ポリシーサービスとエッジサーバーに対して行う接続

3. ネットワーク構成ドキュメントに構成されているすべてのリンク、および各帯域幅ポリシーサービスによって報告されるリアルタイムの帯域幅の使用状況

### <a name="description"></a>説明

帯域幅ポリシーサービスモニターツールは、GUI ベースのアプリケーションとして実装されています。 管理者は、PDPMonUI を実行してツールを開始します。

ツールが開始すると、トポロジ内の帯域幅ポリシーサービスの一覧の検出が試みられます。 最初の更新が完了すると、ウィンドウの左側にあるウィンドウに、所属するクラスターによってグループ化されたサービスの一覧が表示されます。

管理者が特定の帯域幅ポリシーサービスを選択すると、右側のウィンドウにその特定のサービスに関する情報が表示されます。 このウィンドウには、情報を表示するための2つの主要なタブもあります。

#### <a name="machine-info-tab"></a>[コンピューター情報] タブ

[**コンピューター情報**] タブには、選択されている帯域幅ポリシーサービスの詳細と、選択した帯域幅ポリシーサービスによって他のサービスに対して行われたすべての接続のリストと状態が表示されます。

#### <a name="topology-info-tab"></a>[トポロジ情報] タブ

[**トポロジ情報**] タブには、ネットワーク構成設定で構成されているすべてのリンクの一覧が表示されます。 各リンクについて、音声およびビデオの帯域幅の容量が表示されます。 さらに、現在使用されている帯域幅が、Kbps で、容量の割合として表示されます。 このツールは、色分けを使用して、使用率が近づいているリンクを強調表示します。これにより、管理者はそのようなリンクをすばやく分離することができます。

> [!NOTE]
>  構成された帯域幅ポリシーサービスに接続するときに、帯域幅ポリシーサービスモニターツールでエラーが発生した場合、[**コンピューター情報**] タブと [**トポロジ情報**] タブに情報は表示されません。 ただし、最初に接続した後、サービスへの接続が失われる可能性があります。 このような場合、管理者が古い情報を表示することがあります。 各タブに**最後に更新**されたタイムスタンプがあり、管理者は特定の帯域幅ポリシーサービスのデータが最後に更新された日時を確認できます。

### <a name="output"></a>出力

コマンドライン出力はありません。プログラムの出力は、メインのグラフィカルユーザーインターフェイス (GUI) に含まれています。

### <a name="purpose"></a>用途

帯域幅ポリシーサービス監視ツールの目的は、管理者がトポロジで定義されている各帯域幅ポリシーサービスの状態を表示できるようにすることです。 さらに、管理者は、ネットワーク構成ドキュメントで定義されているすべてのリンクについて、リアルタイムの帯域幅使用量を確認できます。

### <a name="requirements"></a>Requirements

帯域幅ポリシーサービスモニターツールは、Skype for Business Server のトポロジの一部であるコンピューター上で実行する必要があります。

### <a name="summary"></a>概要

帯域幅ポリシーサービスモニターツールは、管理者にとって価値のあるリソースとなり、トポロジ内のすべての帯域幅ポリシーサービスの状態を調査できること、さらに重要な点として、ネットワーク構成設定で定義されます。

## <a name="bandwidth-utilization-analyzer"></a>帯域幅使用率アナライザー
<a name="bua"> </a>

帯域幅使用率アナライザーは、エンタープライズネットワーク内の WAN リンク全体にわたる UC エンドポイントによる帯域幅消費量のさまざまな表示に関するレポートを作成するツールです。 これらのレポートを使用して、現在の帯域幅の使用パターンを理解し、帯域幅の容量計画に役立てることができます。

### <a name="description"></a>説明

帯域幅使用率アナライザーは、GUI ベースのアプリケーションとして実装されています。 このツールは、ネットワーク全体の音声使用に特化したレポートを生成し、容量計画に役立てることができます。 また、さまざまなリンクに割り当てられている帯域幅容量を反復処理します。

### <a name="output"></a>出力

帯域幅使用率アナライザーは、システム内で構成されているすべての WAN リンクについて、帯域幅容量とオーディオの使用率を図で示しています。

### <a name="purpose"></a>用途

音声およびビデオの展開では、企業ネットワーク全体のメディアトラフィックの帯域幅使用率の傾向を監視し、理解しておくことが重要です。 帯域幅使用率アナライザーツールを使用すると、管理者はこれを実現することができます。 このツールは、次の処理を行います。

- ネットワーク全体の音声使用状況に関する特定のレポートを生成します。

- さまざまなリンクに割り当てられている帯域幅容量に対して、さらに効果的な容量計画と反復処理を行うことができます。

帯域幅使用率アナライザーは、帯域幅容量と使用率レポートをグラフィカルにプロットすることができます。次のようになります。

- エンタープライズネットワーク内のすべての WAN リンク

- 選択された WAN リンクでフィルター処理

- リンク容量を超過した WAN リンクでフィルター処理

- プロビジョニングされた帯域幅を利用している WAN リンクでフィルター処理

- 重大レベルに達している WAN リンクでフィルター処理する (WAN リンクの帯域幅の容量の90% を超える帯域幅の使用率)

- WAN リンクの種類によるフィルター処理—ネットワークサイトリンク、地域間リンク、サイト内のリンク

- ネットワーク地域でフィルター処理

#### <a name="applications"></a>アプリケーション

帯域幅使用率アナライザーには、次の2つのアプリケーション (ツール) があります。

- **Wanlinklogcollector.exe**このツールを使用すると、ユーザーは必要な情報を入力できます。

- **Bandwidthutilizationanalyzer.xlsm** Wanlinklogcollector.exe は、Microsoft Excel スプレッドシートソフトウェアレポートを自動的に起動します。 このアプリケーションでは、この記事で後述するように、ユーザーがレポートにフィルターを適用することができます。

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a>帯域幅使用率アナライザーを使用するフェーズ

帯域幅使用アナライザーを使用する場合は、次の2つのフェーズがあります。

- ログを収集する (Wanlinklogcollector.exe を使用して実行される)

- Bandwidthutilizationanalyzer.xlsm を使用して実行されるレポートをカスタマイズする

    > [!IMPORTANT]
    > Bandwidthutilizationanalyzer.xlsm をエンドユーザーが手動で起動しないようにすることを強くお勧めします。

#### <a name="starting-bandwidth-utilization-analyzer"></a>帯域幅使用率分析の開始

コマンドプロンプトまたはエクスプローラーを使用して、Wanlinklogcollector.exe を起動します。

 **Wanlinklogcollector.exe を使用する**

Wanlinklogcollector.exe を使用するには、次の3つの手順を実行します。

1. **タイムラインのログを記録する**レポートを生成するために必要なタイムラインを指定する

2. **ファイルディレクトリを指定する**ファイルの場所情報を指定する

3. **ログを収集してレポートビューアーを起動する**コマンドを実行してレポートを生成します。

#### <a name="step-1---log-the-timeline"></a>手順 1-タイムラインのログを記録する

タイムラインのログを記録すると、次の図に示すように、ツールユーザーは次のものを指定できます。

1. **開始日**これは、レポートが生成されるタイムラインの開始日です。たとえば、2010年8月1日。

2. **終了日**これは、レポートが生成されるタイムラインの終了日です。たとえば、2010年9月30日。

     ![帯域幅使用率の開始日と終了日](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a>手順 2-ファイルディレクトリを指定する

表示されているように、次のファイルディレクトリをユーザーが指定できます。

- **サーバーログファイルの場所**帯域幅ポリシーサーバーのログが格納されるフォルダーの場所。 通常、これは\<、\> \\ \AppServerFiles\PDP. で選択さ\>れている [日本語の項目です<

- **一時ファイルの保存場所**レポートの生成中に中間ファイルが保存される一時ファイルの場所。

    ![帯域幅使用率 Anal のファイルディレクトリ](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > サーバーログと一時ファイルストアフォルダーへの十分なファイルアクセスがツールユーザーに提供されていることを確認します。

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>手順 3-ログを収集してレポートビューアーを起動する

ログを収集してレポートビューアーを起動するには、下の図のように [**実行**] をクリックします。 この手順では、必要なデータを収集します。

![帯域幅使用率の収集におけるデータの収集の概要 y](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

入力の検証に成功すると、次に示すメッセージが表示されます。

![帯域幅 Bandwidthutilizationanalyzer で収集された通知を記録します。](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

**[OK]** をクリックします。 Bandwidthutilizationanalyzer.xlsm が自動的に開始されます。 メッセージボックスの指示に従います。 詳細については、次のセクションの「 **Using bandwidthutilizationanalyzer.xlsm** 」を参照してください。


### <a name="using-bandwidthutilizationanalyzerxlsm"></a>Bandwidthutilizationanalyzer.xlsm の使用

1. Bandwidthutilizationanalyzer.xlsm が自動的に開始されたら、下の図のように [**更新**] をクリックします。

     ![Bandwidthutilizationanalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. ファイルフォルダーが開いたら、次に示すように、メッセージボックスに指定されている場所から [統合] を選択します。 また、場所が**C:\Temp**であることも示しています。

     ![Bandwidthutilizationanalyzer.xlsm でフォルダーを開きます。](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. [**インポート**] をクリックします。

4. グラフィカルプロットが自動的に生成されます。 このツールは、バックグラウンドで動作しているポインターが表示されなくなったときに使用できます。

     ![レポートビューでフィルターを適用します。](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a>レポートビューにフィルターを適用する

以下に示すように、レポートビューに適用できるフィルターについては、次のように説明します。

![レポートビューでフィルターを適用します。](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. **名前**WAN リンクでフィルター処理します (グラフの右側にフィルターがあります)。プレフィックスは次のリンクの種類を示します。垂直 (青) のボックスを表示します。

   - **S サイト**ネットワークサイトからネットワーク地域への WAN リンク

   - **サイト間**2つのネットワークサイト間の WAN リンク

   - **R 地域間**2つのネットワーク地域間の WAN リンク

2. **制限を超え**た帯域幅の使用率が帯域幅の容量を超えている WAN リンクでフィルター処理する

3. **重要なレベル**帯域幅の使用率が90% 以上に達したか、帯域幅の容量を超えている WAN リンクでフィルター処理する

4. **低使用時**帯域幅の使用率が帯域幅の容量の25% 未満である WAN リンクでフィルター処理する

5. **リンクの種類**次の WAN リンクの種類でフィルター処理します。

   - **ネットワークサイト**の種類

   - **サイト間の**種類

   - **地域間リンクの**種類

6. **Region**ネットワーク地域によるフィルター

次の図は、以前に説明したフィルターを示しています。

**名前**でフィルター処理します。 グラフに表示する必要があるリンクの一覧を選択します。

![Bandwidthutilizationanalyzer.xlsm での名前によるフィルター処理。](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

制限を**超え**てフィルターを適用します。 フィルターを適用するには、[ **True** ] を選択します。

![制限を超過したフィルター処理。](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

**重要レベル**でフィルター処理します。 フィルターを適用するには、[ **True** ] を選択します。

![重要レベルでのフィルター処理。](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

**使用率**の低いフィルターを適用します。 フィルターを適用するには、[ **True** ] を選択します。

![フィルター処理に使用されます。](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

リンクの**種類**でフィルター処理します。 表示する必要のある種類を選択します。

![リンクの種類によるフィルター処理。](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

**地域**でフィルター処理します。 リンクを表示する必要がある地域の一覧を選択します。

![地域別のフィルター処理。](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a>Requirements

- .NET Framework 3.5

- Microsoft Excel 2010 または Excel 2007

### <a name="summary"></a>概要

帯域幅使用率アナライザーは、ネットワーク経由で UC トラフィックのオーディオ帯域幅の使用率をプロットするために使用されます。 このツールを使用して、ネットワーク上のビデオ帯域幅の使用状況を報告することもできます。

## <a name="call-parkometer"></a>コール Par・メータ計
<a name="callpark"> </a>

Call Par・ m は、コールパークオービットデータベースへの簡単なアクセスを提供するコマンドラインアプリケーションです。

### <a name="description"></a>説明

Call Par・メータは、現在パークされている通話を追跡するためのツールです。 また、オービットおよびコールパークサーバー (CPS) の使用状況に関する統計を収集します。 このコマンドラインツールを使用すると、ローカルまたはリモートで接続されているコンピューターから、CPS による SQL Server データベースの読み取りおよび書き込みアクセスの両方を行うことができます。

すべてのオプションは相互に排他的です。 コマンドラインの構文は次のとおりです。

- **-o**パラメーター-このプールに構成されているすべてのオービット範囲を一覧表示します。

- **-n**パラメーター-このプールで現在使用されているすべてのオービットを一覧表示します。 表示される情報は次のとおりです。

  - Parkee および parker の SIP Uniform Resource Identifier (URI)。

  - 通話が保留されている CPS のホスト名。

  - 通話が保留された時点のタイムスタンプ。

- **-f**パラメーター-プール内の現在の空きオービットの数を一覧表示します。

- **-r \<n\> **パラメーター— n 個\<\>の最後に保留された通話を一覧表示します。 表示される情報は次のとおりです。

  - Parkee SIP URI。

  - Parker SIP URI。

  - 呼び出しがパークされた CPS のホスト名。

  - 呼び出しが取得または削除された時点のタイムスタンプ。

- **-t\<n\> **パラメーター-データベース内でオービットを予約して、割り当てられているオービット数のランダム性を示すテストを行います。

### <a name="output"></a>出力

コマンドプロンプトで指定された入力パラメーターに応じて、Call Par・メータは次の出力を表示します。

- このプールに対して構成されているすべてのオービット範囲

- 現在パークされている通話

- 空き (利用可能な) オービットの数

- 最近パークされた通話

- オービットは、一様でランダムなオービットの値をテストするために予約されています

### <a name="purpose"></a>用途

CPS ツールの目的は、CPS データベースへのコマンドラインアクセスを提供することです。 管理者は、CPS の使用状況を表示して、プールに割り当てられているオービットの数を確認できます。

### <a name="requirements"></a>Requirements

このツールを CPS を実行しているのと同じコンピューターで実行する場合、要件はありません。 このツールをリモートコンピューターで実行する場合、Skype for Business Server 2015 で使用される SQL Server データベースを、リモートアクセスを許可するように構成する必要があります。 プールの SQL Server に接続するには、SQL Server データベース接続文字列を使用して、呼び出し Par・メータを構成する必要があります。 この SQL Server データベースの接続文字列は、構成ファイルで定義されています。 **.config**を指定します。このディレクトリは、parている parm が配置されているのと同じディレクトリに配置する必要があります。 次の XML ファイルは、paragent.config の例です。構成する必要があるパラメーターは、ユーザー名 (例: myドメイン管理者)、パスワード (mypassword など)、ホスト名 (たとえば、myserver) です。

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

展開されるオービット範囲:-o パラメーターは、次のように、このプールに構成されているすべてのオービット範囲を一覧表示します。

![呼び出し Par・メータメーターのオービット範囲。](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

現在パークされている通話: n パラメーターは、このプールで現在使用されているすべてのオービットを示しています。

![Call Parm の現在パークされている通話。](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

空きオービットの数:-f パラメーターには、プール内の現在の空きオービットの数が表示されます。

![Free オービット in Call Parm。](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

最近パークされた通話: \<次\>に示すよう\<に\> 、最後に保留された通話を-r n パラメーターで一覧表示します。

![Call Parm の最近パークされた通話。](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

テストオービット予約:-t \<n\>パラメーターは、次のように、データベースでオービットを予約します。

![Call Parm でオービット予約をテストします。](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a>概要

Call Par・ m は、コールパークサーバーに関する詳細情報を提供するコマンドラインツールです。

## <a name="dbanalyze"></a>DBAnalyze
<a name="dba"> </a>

### <a name="description"></a>説明

DBAnalyze は、管理者が Skype for Business Server 2015 データベースに関する分析レポートを収集するのに役立つコマンドラインツールです。 DBAnalyze には、診断、ユーザーデータ、会議、Mcu、ディスクの断片化という次のモードがあります。

- **診断モード**テーブルに関する情報を含むレポートを作成します (レコード数、断片化、データサイズ、およびインデックスサイズ)、データファイルとログファイルのサイズ、最新のバックアップ時間、Microsoft Office Communications Server を実行しているサーバー間の連絡先の配分、ユーザーごとのアクセス許可の平均数、連絡先、コンテナー、サブスクリプション、公開、およびルーティングできないユーザー、ユーザーごとに開催された会議の平均数、会議の予定、アクティブな会議、データベースバージョンを示します。

    > [!NOTE]
    > 診断モードを実行すると、サーバーのパフォーマンスに影響する可能性があります。

- **ユーザーデータモード**指定されたユーザーまたはそのユーザーの連絡先およびアクセス許可の一覧に、連絡先、コンテナー、サブスクリプション、パブリケーション、アクセス許可、および連絡先グループのデータを報告します。 このモードでは、ユーザーが開催または招待されている会議の概要データも報告します。

- **電話会議モード**会議のすべてのスケジュール時の詳細、招待者リスト、会議に使用できるメディアの種類の一覧、アクティブな Mcu (multipoint control unit)、アクティブな参加者の一覧、各参加者の信号状態など、特定の会議の詳細データを報告します。

- **会議 ID のデコード****/Pstnid**スイッチで指定された公衆交換電話網 (PSTN) の会議 ID をデコードしますが、バックエンドには接続せずに詳細情報を返します。

- **電話会議を解決**する **/Pstnid**スイッチで指定されている PSTN 会議 ID をデコードし、id で示される電話会議に関する情報を表示します。

- **Mcu モード**プール内の各 MCU の ID、メディアの種類、URL、ハートビートの状態、会議の負荷、参加者の負荷などのレポートを作成します。

- **ディスク断片化モード**すべてのディスクの断片化状態を表示します。

このツールを使用すると、さまざまな問題を診断したり、管理者が容量計画を支援したりすることができます。 たとえば、サーバー A に所属するほとんどのユーザーが、連絡先として server B に所属するユーザーを選択すると、管理者はサーバー A のユーザーをサーバー B に移動して、サーバー間のトラフィックを減らすことができます。

### <a name="output"></a>出力

このツールは、Skype for Business Server 2015 データベースに関する定義済みのレポートを出力します。 **パス**:%ProgramFiles%\Skype For Business Server 2015 \ うえ

### <a name="purpose"></a>用途

Dbanalyze .exe をインストールするには、それをローカルフォルダーにコピーしてからツールを実行します。 このツールを使用するには、コマンドラインから次のコマンドを実行します。 `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`コマンドラインオプションの説明を以下に示します。

![Dbanalyze .exe のコマンドラインオプション。](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a>Requirements

 **コンピューター**DBAnalyze は、Skype for Business Server 2015 がインストールされているドメインに参加しているコンピューターからのみ実行できます。

 **ネットワーク**コンピューターは、バックエンドデータベースに接続できる必要があります。

 **ソフトウェア**DBAnalyze を実行する前に、Skype for Business Server 2015 ソフトウェアコンポーネントをインストールする必要があります。

 **ユーザー**次の表に、Skype for Business Server 2015 データベースへのアクセスに必要なアクセス許可を持つ管理者を示します。

![Dbanalyze .exe のアクセス許可の表。](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> **/Report: disk** mode では、ローカル管理者アカウントが必要です。

### <a name="examples"></a>例

次に、有効な Dbanalyze .exe コマンドの例を示します。

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a>概要

DBAnalyzer を使用すると、管理者は Skype for Business Server 2015 データベースの分析をすばやく簡単に行うことができます。

## <a name="import-storage-service-data"></a>ストレージサービスデータのインポート
<a name="Issd"> </a>

ImportStorageServiceData リソースキットツールを使用すると、ストレージサービス (一から) にフラッシュされたキューおよびエンドポイントデータをストレージサービスに再インポートできます。

### <a name="description"></a>説明

ストレージサービスからフラッシュされたデータは、キューアイテムの状態またはデータベースサイズに基づいて、定期的に自動 (定期的) になっている場合があります。 プールフェールオーバーコマンドレットを手動で起動したか、または StorageServiceFullFlush コマンドレット (プールフェールオーバーコマンドレットによって起動される) が発生したことが原因である可能性があります。 フロントエンドのデータベースサイズが通常のレベルより上にある場合は、データのエクスポートが多くなる可能性があるため、データを再インポートするのが理想的ではないことに注意してください。さらに、ストレージサービスキューを拡張する原因となったエラーに寄与する可能性がある問題は、最初に解決する必要があります (たとえば、Exchange エンドポイントのエラー、ネットワークの問題、またはその他の問題)。

 **シナリオ 1:** プールのフェールオーバー中は、フロントエンドごとに記憶域サービスからファイルがフラッシュされることがあります。 フェールオーバーが完了したら、データを再インポートするためにツールを実行する必要があります。

 **シナリオ 2:** データが毎日自動的にフラッシュされるか、特定のサイズのしきい値を超える記憶域サービスデータベースに対する応答として (たとえば、60%、80%、90% がいっぱい)。 この自動フラッシュされたデータは、管理者が定期的に再インポートする必要があります。 上記の状況では、monitoring SCOM パックが展開されていない場合、ストレージサービスからフラッシュされるデータに関連する Skype for Business Server ストレージサービスのイベントがあります。 32075のイベント Id (完全なフラッシュ操作が開始)、32076 (完全フラッシュの完了)、32082 (メンテナンスレベルのフラッシュが開始されました)、32083 (メンテナンスレベルのフラッシュが完了)、32089 (データベースの容量がいっぱいになったため、フラッシュが発生しました)。 メモこれらのイベント Id は RTM リリースに対応しています。 管理者にこれらのイベントが表示される場合は、フラッシュアウトされたファイルがあることを意味します。このデータは、たとえば1週間に1回、このツールを使用して定期的にインポートして戻します。

オンラインサービスリリースの場合、Skype for business Server 用の health monitoring SCOM pack が展開されていると、新しい通知が発生する可能性があります。これにより、フラッシュされたデータをストレージサービスに再インポートするように管理者に要求することができます。 アラートをトリガーしたフロントエンドサーバーのイベントログに、対応するイベントが表示されます。 このイベントは、フラッシュされたデータファイルが配置されている親のパスの説明と、通知の条件に一致するファイルの数を指定します。 通知の条件は、特定の親パスの下に X 個以上のファイルが存在することを示しています (X と Y は、StorageService 内で事前設定されていますが、APPCONFIG ファイルを変更することで上書きできます)。状態アラートをトリガーできるイベントの2つの例を次に示します。その違いは親パスです。 Web サービスのファイル共有の下にある可能性がありますが、もう1つの可能性は各フロントエンドのローカルアプリケーションデータディレクトリです。 (たとえば、c:\ProgramData\Microsoft\Skype for Business Server 2015/StorageService)。 その後、管理者はこのうえツールを実行します。

このツールを実行すると、ツールが実行されたフロントエンドがデータを所有していない場合でも、このツールを実行しているフロントエンドの CPU および IO 負荷が増加します。 このツールは、フロントエンドの CPU および IO 負荷が高い場合 (ピーク時間外など) に、このツールを使用することをお勧めします。 2番目に、このツールは、1つのデータファイルをインポートするのに 2 ~ 3 分間かかります。 ツールの実行時間を見積もる場合は、この点に留意してください。 ツールによって生成される詳細ログファイルは、既定でファイルストアに表示されます。 エラーが報告されなかった場合は、ログファイルの数が数 MB 以上になる可能性があるので、削除します。

![ストレージサーバーイベントログイベントのサンプル](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a>Requirements

Skype for Business Server 2015 リソースキットツールをインストールします。 このツールは、Skype for Business Server および Skype for business Server 管理シェルがインストールされているドメインに参加しているコンピューター上で実行されます。 このツールは、管理シェルのコマンドレットを使用して、プール内のすべてのフロントエンドサーバーを識別します。 2番目に、このツールは、 **Rtclocal**データベースがインストールされているプール内のコンピューターから実行する必要があります。 このデータベースは、ツールによって、プールの WEBSERVICE ファイル共有の場所を取得するために使用されます。 さらに、ツールを使用する前に、各フロントエンドサーバーで、 **enable-psremoting**を使用して Windows PowerShell リモート処理を有効にする必要があります。また、各フロントエンドサーバーでは、そのツールが実行されているコンピューターを使用します。 それ以外の場合、このツールのリモート Windows PowerShell コマンドは失敗します。 Windows PowerShell リモート処理は、プール内のすべてのフロントエンドサーバーで、完了後にオフにすることができます。 最後に、ツールを呼び出すアカウントまたは資格情報が、このツールを実行するプールの webservice ファイル共有に対する読み取り/書き込みアクセス許可を持っている必要があります。 それ以外の場合、I/O アクセス許可エラーが発生してもツールは失敗します。

> [!NOTE]
> Windows Server 2012 では、windows PowerShell リモート処理は既定で有効になっていますが、Windows Server 2008 オペレーティングシステムでは有効になっていません。

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

LCSSync ツールは、マルチフォレスト環境で Skype for Business Server 2015 communications software を展開するのに役に立ちます。 このツールは、異なるユーザーフォレストのユーザーおよびグループを、Active Directory ドメインサービスの連絡先オブジェクトとして、Skype for Business Server 2015 がインストールされている中央フォレストに同期するために使用されます。

### <a name="description"></a>説明

 LCSSync は、中央フォレストにある同期された Active Directory ドメインサービスの連絡先オブジェクトを使用して、Skype for Business Server のユーザーを有効にします。 シングルサインオンを提供するには、プライマリユーザーアカウントを、Skype for Business Server 2015 の中央フォレストにある Active Directory ドメインサービスの連絡先オブジェクトにマップする必要があります。 このツールは、そのマッピングを実行するのに役に立ちます。 このツールには、Microsoft Identity Integration Server で管理エージェントを作成するためのテンプレートが用意されています。

### <a name="summary"></a>概要

LCSSync ツールは、マルチフォレスト環境に Skype for Business Server 2015 を展開するのに役に立ちます。

## <a name="lookup-user-console"></a>参照ユーザーコンソール
<a name="LUC"> </a>

LookupUserConsole ツールは、特定のユーザーに関する Skype for Business Server の内部ルーティング情報を表示します。 この情報は、Microsoft サポートの個人が展開とルーティングの問題を診断するのに役立つ場合があります。

### <a name="description"></a>説明

 LookupUserConsole を実行すると、SIP アドレスを受け付け、それに関連する内部 Skype for Business Server のルーティング情報を表示しようとするコマンドプロンプトが開きます。 「 **Exit** 」と入力して、LookupUserConsole ツールを終了します。

### <a name="requirements"></a>Requirements

Skype for Business Server 2015 リソースキットをインストールします。 このツールは、Skype for Business Server がインストールされているドメインに参加しているコンピューター上で実行されます。

### <a name="examples"></a>例

C:\Program Files\Skype for Business Server 2015 \ うえ\>lookupuserconsole. .exe

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

MSTurnPing ツールを使用すると、Skype for Business Server 2015 communications software の管理者は、音声ビデオエッジと音声ビデオ認証サービスを実行しているサーバーと、トポロジ内で帯域幅ポリシーサービスを実行しているサーバーの状態を確認できます。

### <a name="description"></a>説明

MSTurnPing ツールを使用すると、Skype for Business Server 2015 communications software の管理者は、音声ビデオエッジと音声ビデオ認証サービスを実行しているサーバーと、トポロジ内で帯域幅ポリシーサービスを実行しているサーバーの状態を確認できます。

このツールを使用すると、管理者は次のテストを実行できます。

1. 音声ビデオエッジサーバーテスト: このツールは、次の手順を実行して、トポロジ内のすべての音声ビデオエッジサーバーに対してテストを実行します。

   - Skype for Business Server の音声/ビデオ認証サービスが開始されており、適切な資格情報を発行できることを確認します。

   - Skype for Business Server Audio/Video エッジサービスが開始されていることを確認し、外部エッジにリソースを正常に割り当てることができます。

2. 帯域幅ポリシーサービステスト: このツールは、次の手順を実行して、トポロジ内の帯域幅ポリシーサービスを実行しているすべてのサーバーに対してテストを実行します。

   - Skype for Business Server 帯域幅ポリシーサービス (認証) が開始されており、適切な資格情報を発行できることを確認します。

   - Skype for Business Server 帯域幅ポリシーサービス (コア) が開始されており、帯域幅の確認を正常に実行できることを確認します。

このツールは、トポロジの一部であり、ローカルストアがインストールされているコンピューターから実行する必要があります。

### <a name="output"></a>出力

ツールによって各操作の結果が出力されます。

- **AudioVideoEdgeServer**テストが実行された場合、ツールの出力は次のようになります。

  - トポロジで Skype for Business Server 2015 音声ビデオ認証サービスを提供するコンピューターのテスト結果

  - トポロジで Skype for Business Server 2015 音声ビデオエッジサービスを提供するコンピューターのテスト結果

- **BandwidthPolicyServer**テストが実行された場合、ツールの出力は次のようになります。

  - トポロジで Skype for Business Server 2015 帯域幅ポリシーサービス (認証) を提供するコンピューターのテスト結果

  - トポロジで Skype for Business Server 2015 帯域幅ポリシーサービス (コア) を提供するコンピューターのテスト結果

### <a name="requirements"></a>Requirements

- このツールは、トポロジ内にあり、ローカルストアを持つコンピューターから実行する必要があります。

- このツールは、ローカルストアへのアクセス権を持つ管理者として実行する必要があります。

### <a name="examples"></a>例

ツール入力の例を次に示します。

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a>概要

このツールは、Skype for Business Server 2015 管理者が、音声ビデオおよび帯域幅ポリシーサービスを実行しているサーバーの状態を確認するための貴重なリソースになることがあります。

## <a name="network-configuration-viewer"></a>ネットワーク構成ビューアー
<a name="NCV"> </a>

ネットワーク構成ビューアーは、Skype for Business Server 2015 communications software 管理者が使用して、リアルタイム通信セッションを許可するようにプロビジョニングされた企業の通話受付管理 (CAC) ネットワークトポロジを表示することができます。指定した帯域幅容量に基づく音声またはビデオ通話。 Skype for Business Server 2015 管理者は、Skype for business Server 2015 と共にインストールされる帯域幅ポリシーサービスによって適用される CAC ポリシーを定義します。

### <a name="description"></a>説明

ネットワーク構成ビューアー (NetworkConfigurationViewer) を使用すると、管理者は次のタスクを実行できます。

- Skype for Business Server 2015 展開からの CAC ネットワークトポロジを、グラフィカルな形式で読み込んで表示します。

- 帯域幅ポリシーサーバーのログファイルから、画像形式で CAC ネットワークトポロジを読み込んで表示します。

- CAC ネットワークトポロジをディスク上の XML 形式で保存して保存します。

- CAC ネットワークトポロジダイアグラムを JPG または BMP 形式で保存して保存します。

- CAC ネットワークトポロジ構成データを表示します。

- ツリービュースタイルで CAC ネットワークトポロジを表示します。

- CAC ネットワークトポロジリンク (たとえば、サイト間、地域間、サイト間リンクなど) 用のカスタムコネクタを定義してください。

- CAC ネットワークトポロジサイト情報、地域情報、およびプロビジョニングされた帯域幅ポリシーとネットワークリンクを表示します。

### <a name="purpose"></a>用途

グラフィカルインターフェイスでエンタープライズ CAC ネットワークトポロジリンクを表示します。

### <a name="examples"></a>例

 次の図に示すように、skype for business **server 2015 展開からの cac ネットワークトポロジを読み込み、表示**します。 Skype for business server 2015 管理者は、次の図に示すように、[**ネットワーク構成のダウンロード**] オプションを使用して、すべての skype for business SERVER 2015 コンピューターで cac ネットワークトポロジ構成を読み込んで表示できます。 このツールは、Skype for Business Server 2015 構成ストアに接続されていないコンピューターに展開された場合に、このような構成のダウンロードや表示に失敗します。

![ネットワーク構成のダウンロード。](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 **帯域幅ポリシーサーバーのログファイルから、画像形式で CAC ネットワークトポロジを読み込み、表示します。** Skype for Business Server 2015 帯域幅ポリシーサーバー Skype for Business Server 2015 ファイル共有の場所のログ機構の一部として CAC ネットワークトポロジを保存します。 Skype for Business Server 2015 管理者は、次に示すように、 **[Open Network Configuration** ] オプションを使用して、このようなファイルをグラフィカルな形式で表示できます。

![帯域幅ポリシーサーバーのログファイルを開きます。](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

CAC ネットワークトポロジをディスク上の XML 形式で保存および格納する: Skype for Business Server 2015 管理者は、以下に示すように、[**ネットワーク構成のコピーを保存**する] オプションを使用して cac ネットワークトポロジ構成ファイルを xml 形式で保存できます。 保存した構成ファイルは、グラフィック表示のためにオフラインで使用できます。

![ネットワーク構成を XML ファイルとして保存します。](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

CAC ネットワークトポロジダイアグラムを JPG または BMP 形式で保存して保存します。 Skype for Business Server 2015 管理者は、以下に示すように、[**ネットワーク構成ダイアグラムを画像として保存**] オプションを使用して、cac ネットワークトポロジ構成をグラフィカルな形式 (JPG および BMP ファイル形式) で保存できます。

![ネットワーク構成を画像として保存します。](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <strong>CAC ネットワークトポロジ構成データを表示します。</strong>Skype for Business Server 2015 管理者は、次のように [ネットワーク構成データの表示] オプションを使用して、ネットワーク地域、ネットワークサイト、帯域幅プロファイル、およびサイトサブネットの IP アドレスなど、関連するネットワーク構成データをテキスト形式で表示できます。

![ネットワーク構成データを表示する。](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 **ツリービュー形式の CAC ネットワークトポロジを表示します。** Skype for Business Server 2015 管理者は、次に示すように、ツールウィンドウの左側にあるコントロールパネルを使用して、関連するネットワーク構成データをグラフィカルなツリービュースタイルで表示できます。

![ツリービューでのネットワーク構成データの表示。](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 **CAC ネットワークトポロジリンクのカスタムコネクタ (サイト間、地域間、サイト間のリンクなど) を定義します。-:** Skype for Business Server 2015 管理者は、次に示すように設定オプションを使用して、CAC ネットワーク構成の WAN リンク用のカスタムグラフィカルコネクタを定義できます。 これにより、ネットワーク構成でプロビジョニングされたさまざまな種類のネットワークリンクを区別することができます。

![ツール](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 **CAC ネットワークトポロジのサイト情報、地域情報、およびプロビジョニングされた帯域幅ポリシーを表示します。** Skype for Business Server 2015 管理者は、以下に示すオプションを使用して、関連する CAC ネットワーク地域情報、サイト情報、および CAC 帯域幅プロビジョニング情報を表示できます。 (たとえば、[ネットワーク地域またはネットワークサイトオブジェクトの**情報**] をクリックします)。

![ネットワークのカスタムコネクタを定義します。](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a>概要

このツールは、画像形式で展開するために CAC ネットワークトポロジを表示する、Skype for business Server 2015 管理者にとって有益なリソースになる可能性があります。

## <a name="response-group-agent-live"></a>応答グループエージェント Live
<a name="RGAL"> </a>

応答グループアプリケーションによって、エージェントは組み込みの Web サービスを使用して、便利なリアルタイム情報にアクセスできます。 残念ながら、このデータのグラフィック表示はアプリケーションの外部では使用できません。 Response Group Agent Live Resource Kit tool では、このような情報にアクセスするためのシンプルでグラフィカルな方法を提供することにより、この問題を解決します。これは、他のエージェントの存在などのリアルタイムの Skype for Business 通信ソフトウェア情報を使用して拡張されています。

### <a name="description"></a>説明

応答グループエージェント Live は、サインインとサインアウトの機能、およびいくつかのリアルタイム情報 (グループメンバーシップ、現在の通話数など) を応答グループエージェントに提供する Windows アプリケーションです。 エージェントグループページの拡張バージョンとして使用される (Skype for Business からアクセス可能) ことを目的としています。

### <a name="purpose"></a>用途

応答グループアプリケーションは、着信呼び出しをキューに入れ、それらをエージェントグループにルーティングします。 サービスに対する呼び出しを決定するために、エージェントはエージェントグループに関するリアルタイムの情報にアクセスできます。これには、他にどのエージェントを使用できるかや、各キューで待機している呼び出しの数などがあります。 この情報は、最初は応答グループサービスを介してのみアクセス可能です。これは、応答グループエージェント Live により直観的な方法で利用可能になります。

#### <a name="features"></a>機能

応答グループエージェント Live ツールは、応答グループサービスと Skype for Business Server 2015 SDK 上に構築されています。 応答グループのエージェントは、応答グループサービス (グループメンバーシップ、他のエージェントのプレゼンス、待機中の通話数など) から利用できる情報と機能を提供します。

下の図は、応答グループエージェント Live の主要なインターフェイスを示しています。

![応答グループエージェント Live ツール。](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

応答グループエージェント Live のエージェントでは、次の3つの主要な機能を使用できます。

- **サインイン/サインアウト:**[エージェントグループ] ページ (Skype for Business Server 2015 からアクセス可能) に反して、Response Group Agent Live では、エージェントのみが一度にサインインすることも、すべてのエージェントグループから除外することもできます。 このアプリケーションでは、エージェントがサインインまたはサインアウトするための3つの簡単な方法が提供されます。

  - アプリケーション内の [サインイン/出力 (緑と赤)] ボタンをクリックします。

  - システムトレイアイコンを右クリックし、[サインイン] または [サインアウト] を選択します。

  - 構成可能なキーボードショートカットを使用する。

- **グループメンバーシップ:** エージェントグループが選択されている場合、応答グループエージェントのライブには、このグループのエージェントの一覧が右側のウィンドウに表示されます。 Skype for Business Server 2015 がこのアプリケーションと同じコンピューター上で実行されている場合、プレゼンス情報と連絡先カードが応答グループエージェント Live に表示されます。 エージェントは、そこから直接 IM を送信したり、他のエージェントを呼び出したりすることができます。

- **リアルタイムの統計情報:** 応答グループエージェント Live は、すべてのエージェントグループのリアルタイム統計情報を提供します。 更新間隔は1分です。 呼び出しが応答グループによって応答されると、そのグループ名の横に、キューに入れられている現在の呼び出しの数で視覚的なインジケーターが追加されます。 また、グループの上にポインターを置くと、待機時間が長くなります。

### <a name="requirements"></a>Requirements

応答グループエージェント Live には、.NET Framework 4.0 が必要です。 また、プレゼンスと連絡先カードの機能を利用するには、Skype for Business がローカルにインストールされていて、実行中である必要があります。

#### <a name="configuration"></a>構成

応答グループエージェント Live は、アプリケーションの [オプション] ダイアログボックスを使用して、個々の設定に合わせてカスタマイズできます。 さらに、管理者は、RGAgentLive ファイルの defaultHostAddress プロパティを直接編集することによって、既定のホストアドレスを定義できます。

次の図は、エージェントがホストアドレスとショートカットキーを構成する際に使用できる [オプション] ダイアログボックスを示しています。 このダイアログには、メインインターフェイスの右上にある [オプション] ボタンをクリックするとアクセスできます。

![応答グループエージェントの [Live オプション] ダイアログボックス](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

Response Group Agent Live 構成では、次の3種類の設定をカスタマイズできます。

- [ホストアドレス: これは通常、エージェントのホームプールに属する web プールの FQDN です。 正確な応答グループサービスのアドレスは、この情報から (ホストの後に適切なパスを追加することによって) バックグラウンドで自動的に生成されます。

- ショートカット: サインイン/アウトの正確なショートカットをカスタマイズできます。 唯一の制限は、両方のショートカットに "Windows ロゴ" キーが含まれている必要があることです (少なくとも他のキーに加えて)。

- Windows で起動する: アプリケーションは、Windows で自動的に起動するように構成できます。

### <a name="examples"></a>例

次の図は、右側のウィンドウで連絡先を右クリックして、他のエージェントに電話をかけたり、IM を送信したりする方法を示しています。

![電話をかけたり、IM を送信したりする。](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

次の図は、応答グループエージェント Live が、キュー内の現在の呼び出し数と、これらのすべての着信呼び出しのうちで最長の待機時間を表示する方法を示しています。

![キュー情報の表示。](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a>概要

Fast サインインとサインアウト、グループメンバーシップ、および基本的なリアルタイム統計情報は、応答グループサービスからアプリケーションの外部でのみ使用可能な、興味深い応答グループエージェントの機能です。 Response Group Agent Live Resource Kit tool を使用すると、Skype for Business Server 2015 の管理者は、迅速かつグラフィカルな方法でタスクを実行できるようにするための Windows アプリケーションでエージェントを提供できます。

## <a name="sefautil"></a>SEFAUtil
<a name="SEFAUtil"> </a>

SEFAUtil (第2拡張機能のアクティブ化) は、Skype for Business Server 2015 communications software 管理者およびヘルプデスク担当者が、代理人の呼び出し、着信の転送、同時呼び出しを構成できるようにするコマンドラインツールです。Skype for Business Server 2015 ユーザーの代理としてのチーム呼び出しの設定とグループ通話のピックアップ。 また、このツールを使用すると、管理者は特定のユーザーに対して公開されている呼び出しルーティング設定を照会することができます。SEFAUtil ツールを使用すると、管理者は着信の転送を有効/無効にしたり、ユーザーの代わりに同時に呼び出したりすることができます。 管理者は、ターゲット (SIP URI の形式) を指定するか、ユーザーによって既に公開されているターゲットを使用できます。 このツールを使用すると、管理者は、ユーザーの代わりに代理人またはチーム呼び出しグループのメンバーを追加または削除することもできます。このツールは、Microsoft 統合コミュニケーション Managed API (UCMA) 3.0 上に構築されており、管理者は SEFAUtil の中央管理ストアで信頼済みアプリケーションを作成する必要があります。

SEFAUtil (セカンダリ拡張機能のアクティブ化) skype for Business Server 2015 管理者およびヘルプデスク担当者が、Skype の代わりに委任、着信の転送、同時呼び出し、チーム呼び出しの設定、グループ通話ピックアップを構成できるようにします。Business Server 2015 ユーザーの場合。 また、このツールを使用すると、管理者は特定のユーザーに対して公開されている呼び出しルーティング設定を照会することができます。

### <a name="description"></a>説明

SEFAUtil の現在のバージョンはコマンドラインツールにすぎません。グラフィカルユーザーインターフェイスはサポートされていません。 このツールは、Microsoft 統合コミュニケーション Managed API (UCMA) 3.0 に基づいています。 このツールの機能により、管理者とヘルプデスク担当者は次のことを行うことができます。

- ユーザーのすべての通話ルーティング設定を表示する (着信転送、委任、同時呼び出し、チーム呼び出し、グループ通話ピックアップを含む)

- 通話転送設定の有効化/無効化/変更 (送信先と応答なしのタイマーを含む)

- 着信転送の即時構成の有効化/無効化/変更

- 委任設定の有効化/無効化/変更

- チーム呼び出しグループの設定の有効化/無効化/変更

    > [!NOTE]
    > Skype for Business Server 2015 SEFAUtil ツールの新サービス

- 同時呼び出しの設定の有効化/無効化/変更 (destination を含む)

    > [!NOTE]
    > Skype for Business Server 2015 SEFAUtil ツールの新サービス

- グループ通話ピックアップ設定の有効化/無効化/変更

    > [!CAUTION]
    > Skype for Business Server 2015 SEFAUtil ツールの新サービス

このツールには次の制限があります。

- Skype for Business Server プールに所属するユーザーのみがサポートされています。

- 複数のユーザーの通話ルーティング設定の一括編集はサポートされていません

### <a name="output"></a>出力

このツールの現在のバージョンでは、コマンドプロンプトウィンドウにのみ出力が提供されます。 詳細については、このドキュメントで後述する「例」セクションを参照してください。

### <a name="purpose"></a>用途

このツールが使用される主なシナリオのいくつかを次に示します。

- Bob はエグゼクティブで、Skype for Business Server テレフォニーに移行されました。 既存の PBX システム上で委任を行います。 Skype for Business Server 2015 への移行の一環として、管理者は、既存の委任構成を反映するように Bob のルーティングを構成できます。

- Alice は出張中で、お客様の1人からの重要な連絡を期待していることを認識しています。 しかし、彼女はホテルにいて、コンピューターにアクセスできません。 ヘルプデスクに電話をかけて、自分の勤務先番号へのすべての通話に対して、自分の携帯電話番号への転送を要求します。 ヘルプデスク担当者は、自分の代わりに構成を行うことができます。

- 仕事の電話番号に対する Joe の呼び出しは、自分が勤務しているときに、携帯電話のボイスメールに送られます。ただし、その他の多くの場所では正常に動作しているように見えます。 ヘルプデスク技術者は、Joe のルーティング構成を表示して、Joe が自分の携帯電話に対して同時呼び出しを構成していることを検出できます。 この技術者は、自分のオフィスのモバイルの範囲について Joe に質問をし、同時呼び出しが、ネットワークのカバレージが悪い場合に、その通話が Joe のモバイルボイスメールに送られる原因となっていることを確認することができます。

- Mike は Contoso 社の新入社員で、チーム呼び出し用にすべてのメンバーが構成されている新しいチームに参加しています。 Skype for Business Server 2015 を有効にしている場合、管理者はチーム呼び出しグループの設定を設定して、すべての新しいチームメンバーを含めることができます。また、管理者はチーム内の各メンバーのチーム呼び出しグループメンバーとして Mike を追加します。

- Contoso 社の人事部のカスタマーサービスプラクティスでは、最初の呼び出し以降のすべての発信者に対して個人サービスを提供します。 部署のすべてのメンバーが互いに近い場所に配置されているため、すべての電話がチーム呼び出しで同時に着信すると、チームの業務が非常に中断されます。 チームメンバーを中断せずに最高のサービスを提供するため、Skype for Business Server 2015 管理者はグループ通話ピックアップ機能を利用します。 管理者は、すべての部門メンバーをピックアップグループに追加し、その部署に pickup グループ番号を伝えます。 Samantha がデスクから不在になっている場合、Joe は自分の電話が鳴ったことを通知し、彼は自分の席から呼び出しに応答することになります。

### <a name="requirements"></a>Requirements

SEFAUtil ツールは、信頼されたアプリケーションプールの一部であるコンピューターでのみ実行できます。 UCMA 3.0 をそのコンピューターにインストールする必要があります。 ツールを実行するには、SEFAUtil アプリケーション ID を持つ新しい信頼されたアプリケーションをそのプールに作成する必要があります。

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a>SEFAUtil ツール用の新しい信頼されたアプリケーションを作成する

1. SEFAUTil ツールは、信頼されたアプリケーションプールの一部であるコンピューターでのみ実行できます。 必要に応じて、新しい信頼されたアプリケーションプールとしてプールを追加するには、次のコマンドレットを使用して、Skype for Business Server 管理シェルを使用します。

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > SEFAUtil ツールの実行に使用するすべてのコンピューターに UCMA 3.0 がインストールされている必要があります。

2. 信頼されたアプリケーションは、SEFAUtil ツールのトポロジで定義されている必要があります。 SEFAUtil を新しい信頼されたアプリケーションとして定義するには、Skype for Business Server 管理シェルを使用して、次のコマンドレットを実行します。

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > 必要に応じて、別のポートを使用できます。
    
    > [!NOTE]
    > [プールの FQDN]: SEFAUtil アプリケーションをホストするサーバーまたはプールの FQDN (通常は Skype for Business フロントエンドサーバーの > またはプール)。
    > プールレジストラー FQDN: このアプリケーションプールに関連付けられている Skype for Business フロントエンドサーバーまたはプールの FQDN。
    > プールサイト: このプールが所属しているサイトのサイト ID。

3. トポロジの変更を有効にする必要があります。 トポロジの変更を有効にするには、次のコマンドレットを実行して、Skype for Business Server 管理シェルを使用します。

   ```powershell
   Enable-CsToplogy
   ```

4. 必要に応じて、SEFAUtil ツールの実行に使用するサーバーに、Skype for Business Server 2015 のリソースキットツールをインストールします (サーバーは、信頼されたアプリケーションプールの一部である必要があります)。

5. SEFAUtil が正しく動作していることを確認します。 これを行うには、管理者特権を使用して windows コマンドプロンプトからツールを実行し、展開内のユーザーの着信転送設定を表示します。 既定では、このツールは「..\Program Files\Skype for Business Server 2015 \ うえ」にあります。 ユーザーの着信転送設定を表示するには、次のコマンドを使用します。

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    ユーザーの着信転送設定が表示されます。

#### <a name="group-call-pickup"></a>グループ通話ピックアップ

グループ通話ピックアップでは、機能を完全に有効にするために、Skype for Business Server 2015 で追加の構成が必要になります。 ピックアップグループをユーザーに割り当てる前に、この機能の計画と展開の手順については、「Group Call Pickup product documentation」を参照してください。

### <a name="examples"></a>例

#### <a name="display-current-call-handling-settings"></a>現在の通話処理の設定を表示する

次のコマンドを実行すると、ユーザーの通話処理が表示されます。  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> この例では、 **/server**スイッチを使用して、接続先の Skype For business サーバーを指定します。

 **出力**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a>着信転送/応答のない宛先を設定する

次の使用例は、着信転送/着信応答の宛先を指定せず、リングの遅延を設定します。 ここでは、/server スイッチは提供されていません。SEFAUtil は、Skype for Business Server 2015 の自動検出を試行します。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
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

#### <a name="enable-call-forwarding-immediately"></a>直ちに着信転送を有効にする

この例では、別のユーザーへの着信転送をすぐに有効にします。

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

#### <a name="disable-call-forwarding-immediately"></a>直ちに着信転送を無効にする

この例では、すぐに着信転送を無効にします。

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com  /disablefwdimmediate
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

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>代理人としてユーザーを追加し、代理人の同時呼び出しを設定する

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
> 最後の代理人が削除されると、代理人の着信は自動的に無効になります。

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

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>代理人を追加して、代理人に呼び出しを転送するルールを設定する

この例では、代理人を追加し、代理人に呼び出しを転送するルールを設定します。

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

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>同時呼び出しを有効にして、宛先番号を設定する

この例では、同時呼び出しを有効にして、同時呼び出し先番号を設定します。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> 既に同時呼び出しが有効になっているユーザーの同時呼び出し先番号を変更するには、コマンドを/enablesimulring スイッチにします。そうしないと、宛先番号は変更されません。

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

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>チーム呼び出しのチームメンバーを追加し、チーム呼び出しメンバーグループに同時呼び出しを設定する

この例では、ユーザーのチーム呼び出しグループにチームメンバーを追加し、チーム呼び出しグループへの同時呼び出しを有効にします。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> ユーザーのチーム呼び出しグループにメンバーを追加すると、そのユーザーの同時呼び出しの切り替わりがチーム呼び出しグループに自動的に切り替えられます。

 **出力**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a>チーム呼び出しグループからメンバーを削除する

この例では、ユーザーのチーム呼び出しグループのチームメンバーを削除します。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> 削除されるメンバーがチーム呼び出しグループの唯一のメンバーである場合は、同時にチーム呼び出しグループへの呼び出しが自動的に無効になります。

 **出力**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a>遅延呼び出しをチーム呼び出しグループに設定する

この例では、遅延呼び出しをチーム呼び出しグループ時間設定に変更します。

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

#### <a name="enable-team-call"></a>チーム呼び出しを有効にする

この例では、指定したユーザーのチーム呼び出しを有効にします。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> ユーザーのチーム呼び出しグループにメンバーがいない場合、チーム呼び出しは有効になりません。

 **出力**

#### <a name="disable-team-call"></a>チーム呼び出しを無効にする

この例では、指定したユーザーのチーム呼び出しを無効にします。

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

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>グループ通話ピックアップを有効にし、ユーザーにピックアップグループを割り当てる

この例では、ピックアップグループをユーザーに割り当て、グループ通話ピックアップを有効にします。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 **出力**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a>グループ通話ピックアップを無効にする

この例では、指定したユーザーのグループ通話ピックアップを無効にします。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> ユーザーのグループ通話ピックアップを無効にしても、ユーザーに割り当てられていたグループ番号は保持されません。 その後、そのユーザーのグループ通話ピックアップを再度有効にする場合は、グループ番号を/enablegrouppickup スイッチを使用して再度割り当てる必要があります。

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a>Sysprep.inf
<a name="SYSPrep"> </a>

### <a name="description"></a>説明

Sysprep.inf は、windows Server 2008 オペレーティングシステムコンピューターに次の Skype for Business Server 2015 の必須コンポーネントをインストールする Windows PowerShell スクリプトです。

- Microsoft .Net Framework 4.5

- Microsoft SQL Server Express

- Windows Powershell バージョン3.0

- Visual C++ 2010 再頒布可能パッケージ

- インターネットインフォメーションサービスの更新プログラム

- Windows Identity Foundation

- Skype for Business Server 2015 コアファイル

  このスクリプト名は、Microsoft Windows オペレーティングシステムのシステム準備ツールに似ていますが、これらは異なります。 このスクリプトでは、Skype for Business Server 2015 に必要な前提条件のみがインストールされます。 これらの前提条件がインストールされたら、Windows SYSPrep ツールを使用してサーバーのイメージを作成できます。

### <a name="requirements"></a>Requirements

Sysprep.inf スクリプトを実行する前に、前提条件となるファイルを Windows Server 2008 オペレーティングシステムコンピューター上のローカルフォルダーにコピーする必要があります ( **D:\Setup など)**。 このフォルダーには、Skype for Business Server 2015 ファイルのコピー (具体的には setup.exe) も含まれている必要があり**ます。** 前提条件となるファイルは、次の場所からダウンロードできます。


| **前提条件**                                | **場所**                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| Microsoft .Net Framework 4.5  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| Microsoft SQL Server Express 2008 R2  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| Windows Powershell バージョン3.0  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| Visual C++ 2010 再頒布可能パッケージ  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| インターネットインフォメーションサービスの更新プログラム  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| Windows Identity Foundation  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| Skype for Business Server 2015 Setup.exe  <br/> | Skype for Business Server 2015 メディアからのコピー  <br/>                   |

### <a name="parameter"></a>パラメーター

**-Setupfolder**パラメーターには、必須コンポーネントファイルのディレクトリの場所を引数として指定します。

### <a name="examples"></a>例

Sysprep.inf スクリプトを実行して、Skype for Business Server 2015 の前提条件をインストールするには、管理者特権でのコマンドプロンプトから次のコマンドを実行します。

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a>割り当てられていない番号のアナウンスの移行
<a name="UNAM"> </a>

割り当てられていない番号のアナウンス移行ツールを使用すると、Skype for Business Server 2015 管理者は、アナウンスアプリケーションによってサービスを受けている割り当てられていない番号の構成を、ソース Skype for Business Server またはプールからに移動することができます。接続先の Skype for Business Server またはプール。

### <a name="description"></a>説明

割り当てられていない番号のアナウンス移行ツールは、元のサーバーまたはプールのアナウンスアプリケーションによって処理された割り当てられていない番号の構成を別のサーバーまたはプールに移動する Windows PowerShell スクリプトです。

割り当てられていない番号のアナウンス移行スクリプトを実行すると、次の操作が実行されます。

1. 移動元のサーバーまたはプールでホストされているアナウンスアプリケーションの、割り当てられていない番号アナウンスによって使用されるすべてのオーディオファイルを、展開先のサーバーまたはプールのファイルストアに移動します。

    > [!NOTE]
    > オーディオファイルは、移動先のプールにコピーされると、ソースプールから削除されます。

2. 移行元のサーバーまたはプールでホストされているアナウンスアプリケーションに対して構成されている、割り当てられていない番号のアナウンスを、宛先のサーバーまたはプールに移動します

3. 移行元のサーバーまたはプールでホストされているアナウンスアプリケーションによってサービスを受けているすべての未使用の番号範囲を、宛先のサーバーまたはプールに再割り当てします。

スクリプトの実行に成功すると、移動元のサーバーまたはプールでホストされていたアナウンスアプリケーションによって処理された、割り当てられていないすべての番号の範囲が、移行先のサーバーまたはプールで同じ構成で処理されるようになります。

### <a name="output"></a>出力

" **Move-CsAnnouncementConfiguration**スクリプトは、Skype For Business Server 管理シェルウィンドウで、移行操作の実行が成功したか失敗したかを示します。

操作の実行がエラーによって中断された場合、宛先に正常に移動された割り当てられていない番号の範囲は、運用フォームの移動先に残り、割り当てられていない残りの番号範囲は移行されません。ソースと運用フォーム。 残りの構成を完全に移行するには、エラーに対処した後、スクリプトを再実行します。

### <a name="purpose"></a>用途

割り当てられていない番号のアナウンス移行スクリプトは、次の3つのシナリオで使用できます。

- **新しいバージョンの Skype For Business Server への構成設定の移行:** Contoso 社では、Skype for business Server 2015 への移行プロセスにおいて、移行プロセスの一環として、Skype for Business Server の管理者が、アナウンスアプリケーションによって処理された割り当てられていない番号の構成を Lync Server 2013 展開から新しい Skype for Business Server 2015 展開に移動することを希望しています。 Skype for Business Server 管理者は、構成設定を移動するために、割り当てられていない番号のアナウンス移行ツールを使用します。

- **Skype For Business server 2015 から Lync Server 2013 に展開をロールバックする:** 予期しない要因が発生したため、Contoso 社は、新しい Skype for Business Server 2015 展開に移行をロールバックする必要があります。 サービスへの中断を最小限に抑えるため、Skype for Business Server 管理者は、割り当てられていない番号のアナウンス移行ツールを使用して、Skype for Business Server 2015 の展開から Lync Server 2013 の展開への構成をロールバックします。

- **展開間でのデータの移動:** Contoso 社は、1つのプールのすべてのサーバーを新しいサーバーに置き換える処理を行っています。 その戦略は、新しい Skype for Business Server 2015 プールを展開し、古いプールから新しいプールにすべてのデータを移動して、古いプールを廃止することです。 新しいプールを展開した後、割り当てられていない番号のアナウンス移行ツールを使用して、古いプールから新しいプールに構成を移動します。

#### <a name="requirements"></a>Requirements

ツールを正常に実行するために必要な主な要件は次のとおりです。

1. このスクリプトは、Skype for Business Server 管理シェルがインストールされているコンピューターから実行する必要があります。

2. アナウンスアプリケーションは、移行元と移行先の Skype for Business サーバーまたはプールに正常に展開される必要があります。

#### <a name="move-csannouncementconfiguration-script"></a>「Move-Csアナウンス Ementconfiguration スクリプト」

このスクリプトでは、次の表に示す2つのパラメーターが必要です。

![CsAnnouncementConfiguration パラメーターを移動します。](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a>例

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a>割り当てられていない番号のアナウンス構成を Lync Server 2013 プールから Skype for Business Server 2015 プールに移動する

この例では、割り当てられていない番号のアナウンスをソースプール (Lync Server 2013) から移行先のプール (Skype for Business Server 2015) に移動します。

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a>Skype for Business Server 2015 プールから Lync Server 2013 プールに割り当てられていない番号のアナウンス構成を移動する

この例では、割り当てられていない番号のアナウンスをソースプール (Skype for Business Server 2015) から移行先のプール (Lync Server 2013) に移動します。

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a>Web Conf データ
<a name="WebConfData"> </a>

Web Conf Data ツールを使用すると、Skype for Business Server 2015 コミュニケーションソフトウェアの管理者が、開催者の Web 会議に関連付けられているデータをより詳細に制御することができます。 シナリオには、タイムスタンプの条件に基づいて特定のユーザーの会議データを削除する機能が含まれます。

### <a name="description"></a>説明

このツールを使用すると、管理者は次の操作を実行できます。

1. 単一のユーザーに関連付けられているすべての Web 会議データを検索します。

2. 1人のユーザーに関連付けられているすべての Web 会議データを削除します。

3. 特定の日付よりも前の1人のユーザーに関連付けられているすべての Web 会議データを削除します。

4. ユーザーがあるプールから別のプールに移動したときに、1人のユーザーに関連付けられているすべての Web 会議データを移動します。

    > [!NOTE]
    > Lync Server 2010 のリソースキットツールは、1人のユーザーに関連付けられているすべての Web 会議データを、あるプールから別のプールに移動した場合にサポートされていました。 このツールでは、 **Moveconferencedata**パラメーターを使用してこの機能が廃止されました。 このパラメーターの詳細については、「 [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps)コマンドレット」を参照してください。

このツールは、非アクティブな会議の会議データのみを削除します。 アクティブな会議 (またはセッション中の会議) を削除することはできません。

このツールは、ターゲットユーザーと同じプールにあるコンピューターから実行する必要があります。 このツールで管理されている会議コンテンツデータのユーザーは、同じユーザープールに所属している必要があります。

### <a name="output"></a>出力

このツールでは、各操作の結果が出力されます。

- クエリが実行されると、そのユーザーが開催者として設定されているすべての非アクティブな会議データフォルダーの一覧が出力されます。

- 削除が実行されると、そのデータが削除されるすべての会議データフォルダーの一覧が出力されます。

### <a name="requirements"></a>Requirements

このツールは、開催者が現在所属しているのと同じプールで実行する必要があります。

このツールは、コンテンツファイルストアにアクセスできる管理者権限を使用して実行する必要があります。

### <a name="examples"></a>例

次の表では、パラメーターについて説明します。これらのパラメーターについては、例で使用します。

![Web Conf データツールのパラメーター。](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

前の例では、クエリコマンドがどのように動作するかを示しています。 このようなコマンドの出力は、このツールによって影響を受けるすべての会議コンテンツフォルダーのリストになります。

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

上記は、delete コマンドの例です。 [削除] コマンドを実行すると、このユーザーからすべての非アクティブな会議フォルダーが削除されます。

### <a name="summary"></a>概要

このツールは、会議の会議データをより正確に制御する必要がある管理者にとって、貴重なリソースになる可能性があります。


