---
title: Lync Server 2013 リソースキットツールのドキュメント
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 511a4ee9920237e1671a44a2f7481b40fbeb8e1a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-resource-kit-tools-documentation"></a>Lync Server 2013 リソースキットツールのドキュメント

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-01-09_

このトピックでは、Lync Server 2013 リソースキットの一部であるツールとその用途の例について説明します。Lync Server 2013 のリソースキットツールは、Lync Server 2013 を展開して管理する IT 管理者が日常的なタスクを簡単に行うことができるようにするために役立ちます。 たとえば、**Web Conf Data** ツールを使用すると、オンライン会議中にユーザーによってアップロードされたデータを簡単に制御できます。 **SEFAUtil** ツールを使用すると、ユーザーの問い合わせに対して自動転送や自動応答を設定できます。 IT 管理者はこれらのツールを使用して、より効率的に Lync Server 2013 を管理することをお勧めします。

<div>

## <a name="installation-of-the-resource-kit-tools"></a>リソース キット ツールのインストール

Lync Server 2013 のリソースキットツールをインストールするには、 **OCSReskit**をダウンロードします。 リソースキットツールのインストーラーは、のダウンロードセンターからダウンロードでき[http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429)ます。

**OCSResKit.msi** を実行すると、簡易インストールが行われます。 .Msi は、次のパスにあるすべてのツールをインストールします。 **% Program Files\\%\\Microsoft Lync Server 2013 ResKit**。 このフォルダーには、自己完結型のツールの実行可能ファイルが格納されます。 ファイルが自分のサブフォルダーにもあるツール。

</div>

<div>

## <a name="supported-environments"></a>サポートされる環境

最適なパフォーマンスを実現するには、Lync Server 2013、リソースキットツールを同じ環境にインストールして、Lync Server 2013 で必要とされる仕様と同じようにする必要があります。

</div>

<div>

## <a name="resource-kit-tools-overview"></a>リソース キット ツールの概要

次の一覧では、Lync Server 2013 リソースキットで提供されるツールについて説明します。 各ツールの説明 (要件、使用例など) については、次のセクションで説明します。

  - ABSConfig

  - Bandwidth Policy Service Monitor

  - Bandwidth Utilization Analyzer

  - Call Parkometer

  - CleanupStorageServiceData

  - DBAnalyze

  - ImportStorageServiceData

  - LCSSync

  - LookupUserConsole

  - MsTurnPing

  - Network Configuration Viewer

  - Response Group Agent Live

  - SEFAUtil

  - SYSPrep.ps1

  - Unassigned Number Announcements Migration

  - Web Conf Data

</div>

<div>

## <a name="absconfig"></a>ABSConfig

アドレス帳サービス構成ツール (ABSConfig) は、管理者が Lync Server 2013 のアドレス帳サービスの構成をカスタマイズするのに役立ちます。 このツールを使用すると、Lync Server 2013 管理者が既定のアドレス帳サービス設定を復元することもできます。

<div>

## <a name="description"></a>説明

ABSConfig は、管理者がアドレス帳サービスに関連する Active Directory ドメインサービスの属性を構成できるようにするグラフィカルユーザーインターフェイスアプリケーションです。

このツールを使用する主なシナリオは、次のとおりです。

  - 管理者が Active Directory ドメインサービスの属性を Lync Server 2013 の属性にマッピングできるようにするには、

  - 管理者が Active Directory ドメイン サービスの属性をアドレス帳サービスのファイルに含めるか、ファイルから除外できるようにする。

  - 管理者がアドレス帳サービスの既定の設定を復元できるようにする。

ABSConfig ツールは、absConfig ファイルを使って開始できます。 ツールが [属性の**構成**] タブに表示されます。この表には、Active Directory ドメインサービスの属性を Lync Server 2013 の属性フィールドにマップし、特定の属性フィルターに基づいてアドレス帳サービスファイルに含めるか除外するかを指定するオプションがあります。 また、アドレス帳ファイルに含める電話番号の値をカスタマイズできます。 [**Restore Defaults**] オプションを使用すると、アドレス帳サービスの設定を既定の値に復元できます。

</div>

<div>

## <a name="changes-from-lync-server-2010"></a>Lync Server 2010 からの変更点

Lync Server 2013 ABS 構成ツールでは、属性の [有効] チェックボックスをオフにすることで、属性 (行) を削除できます。 これは、Lync Server 2010 での行の削除と同じ効果があります。

<div>


> [!NOTE]  
> [有効にする] チェックボックスは、右端の列にあります。列を表示するには、右にスクロールする必要がある場合があります。



</div>

</div>

<div>

## <a name="output"></a>出力

ABSConfig は、アドレス帳サービスの構成をデータベースに格納します。

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a>用途

ABSConfig を使用すると、Lync Server 2013 アドレス帳サービスをすばやく簡単にカスタマイズすることができます。

</div>

<div>

## <a name="requirements"></a>要件

<div>

## <a name="computer"></a>コンピューター

ABSConfig は、Lync Server 2013 がインストールされているドメインに参加しているコンピューターからのみ実行できます。 Lync Server 2013 Enterprise Edition の場合、このツールは、セットアップ時にアドレス帳サービスが有効になっているすべてのフロントエンドサーバーで実行できます。

</div>

<div>

## <a name="network"></a>ネットワーク

コンピューターは、フロントエンド プールとバックエンド データベースに接続できる必要があります。

</div>

<div>

## <a name="software"></a>ソフトウェア

ABSConfig ツールを実行する前に、次のソフトウェア コンポーネントをインストールしておく必要があります。

  - Microsoft Lync Server 2013

</div>

<div>

## <a name="users"></a>ユーザー

Lync Server 2013 の展開を更新するのに必要な権限を持っている管理者。

</div>

</div>

<div>

## <a name="examples"></a>例

ABSConfig は、コマンド プロンプトで **ABSConfig.exe** と入力して起動することができます。ABSConfig ツールのユーザー インターフェイスを以下に示します。

![ABSConfig.exe ツール](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "ABSConfig.exe ツール")

</div>

<div>

## <a name="summary"></a>概要

ABSConfig ツールを使用すると、管理者は、Lync Server 2013 アドレス帳サービスをカスタマイズするための簡単で使いやすいツールが提供されます。

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a>Bandwidth Policy Service Monitor

Bandwidth Policy Service Monitor ツールを使用すると、管理者は以下のリストを表示することができます。

1.  トポロジで構成されているすべての Lync Server 2013 帯域幅ポリシーサービス (認証とコア)

2.  各サービスの帯域幅ポリシー サービスとエッジ サーバーへの接続状況

3.  ネットワーク構成ドキュメントで構成されたすべてのリンクと、各帯域幅ポリシー サービスから報告されたリアルタイムの帯域幅の使用状況

<div>

## <a name="description"></a>説明

Bandwidth Policy Service Monitor ツールは、GUI ベースのアプリケーションとして実装されています。管理者は、PDPMonUI.exe を実行してツールを起動します。

ツールを起動すると、ツールはトポロジ内の帯域幅ポリシー サービスの一覧を検索します。初期アップデートが完了すると、ウィンドウの左ペインに、所属するクラスターによってグループ分けされたサービスの一覧が表示されます。

管理者が特定の帯域幅ポリシー サービスを選ぶと、右ペインにそのサービスの情報が表示されます。次の 2 つのメイン タブにそれぞれ情報が表示されます。

<div>

## <a name="machine-info-tab"></a>[Machine Info] タブ

[**Machine Info**] タブには、選択した帯域幅ポリシー サービスの詳細と、選択した帯域幅ポリシー サービスから別のサービスへの接続の一覧と状態が表示されます。

</div>

<div>

## <a name="topology-info-tab"></a>[Topology Info] タブ

[**Topology Info**] タブには、ネットワーク構成設定で構成されたすべてのリンクの一覧が表示されます。各リンクには、音声とビデオの帯域幅容量が表示されます。さらに、現在使用されている帯域幅が、Kbps と容量に対する割合で表示されます。ツールでは色分けが使用され、容量の上限に近づいているリンクが強調表示されます。これにより、管理者は対象のリンクをすばやく分離できます。

<div>


> [!NOTE]  
>  構成済みの任意の帯域幅ポリシー サービスに Bandwidth Policy Service Monitor ツールを接続するときに問題が発生すると、[<STRONG>Machine Info </STRONG>] タブと [<STRONG>Topology Info</STRONG>] タブに情報が表示されません。ただし、最初は接続されたにもかかわらず、後にサービスへの接続が途切れることもあります。このような場合、管理者に古い情報が表示されることがあります。各タブには [<STRONG>Last Updated</STRONG>] タイムスタンプが用意されているため、管理者は特定の帯域幅ポリシー サービスのデータが最後に更新された時間を確認できます。



</div>

</div>

</div>

<div>

## <a name="output"></a>出力

コマンドラインの出力はありません。プログラムの出力は、メインのグラフィカル ユーザー インターフェイス (GUI) に含まれています。

</div>

<div>

## <a name="purpose"></a>用途

Bandwidth Policy Service Monitor ツールを使用すると、管理者はトポロジに定義された各帯域幅ポリシー サービスの詳細を確認できます。さらに、管理者はネットワーク構成ドキュメントに定義されたすべてのリンクの帯域幅の使用状況を、リアルタイムで確認できます。

</div>

<div>

## <a name="requirements"></a>要件

帯域幅ポリシーのサービスモニターツールは、Lync Server トポロジの一部であるコンピューターで実行する必要があります。

</div>

<div>

## <a name="summary"></a>概要

Bandwidth Policy Service Monitor ツールを使用すると、トポロジ内の帯域幅ポリシー サービスの状態を確認できます。さらに、ネットワーク構成設定で定義されたリンクの帯域幅のリアルタイムの使用状況を把握できるため、管理者にとって非常に重要なリソースです。

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a>Bandwidth Utilization Analyzer

Bandwidth Utilization Analyzer は、エンタープライズ ネットワークの WAN リンク全体の UC エンドポイントで消費される帯域幅を、さまざまな観点から確認できるレポートを作成するツールです。これらのレポートを使用すると、現在の帯域幅の消費パターンを把握して、帯域幅の容量計画に活用できます。

<div>

## <a name="description"></a>説明

Bandwidth Utilization Analyzer は、GUI ベースのアプリケーションとして実装されます。このツールは、ネットワーク全体音声に限定した使用状況に関するレポートを作成し、容量の計画に活用できます。また、さまざまなリンクに割り当てられた帯域幅容量を反復処理します。

</div>

<div>

## <a name="output"></a>出力

Bandwidth Utilization Analyzer には、システムで構成されたすべての WAN リンクにおける、音声の帯域幅容量と使用状況に関するグラフィカル プロットが用意されています。

</div>

<div>

## <a name="purpose"></a>用途

音声やビデオを配信する際に、エンタープライズ ネットワーク全体のメディア トラフィックによる帯域幅の使用状況の傾向を把握することは重要です。Bandwidth Utilization Analyzer ツールを使用すると、管理者はそれを把握できます。このツールでは、次の操作を実行できます。

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

<div>

## <a name="applications"></a>アプリケーション

Bandwidth Utilization Analyzer には、次の 2 つのアプリケーション (ツール) が用意されています。

  - **WanLinkLogCollector**   このツールを使用すると、ユーザーは必要な情報を入力することができます。

  - **BandwidthUtilizationAnalyzer**  Microsoft Excel スプレッドシートソフトウェアレポートは、WanLinkLogCollector によって自動的に起動されます。 このアプリケーションでは、レポートにフィルターを適用できます (この記事の後半で説明します)。

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a>Bandwidth Utilization Analyzer の使用フェーズ

Bandwidth Utilization Analyzer の使用は、次の 2 つのフェーズに分けられます。

  - ログの収集 (WanLinkLogCollector.exe を使用)

  - レポートのカスタマイズ (BandwidthUtilizationAnalyzer.xlsm を使用)

<div>


> [!IMPORTANT]  
> BandwidthUtilizationAnalyzer.xlsm はエンド ユーザーが手動で起動できないようにすることを強くお勧めします。



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a>Bandwidth Utilization Analyzer の起動

コマンド プロンプトで WanLinkLogCollector.exe を実行するか、Windows エクスプローラーを使用して起動します。

**WanLinkLogCollector.exe の使用**

WanLinkLogCollector.exe を使用するには、次の 3 つの手順を実行します。

1.  **ログの記録**   レポートを生成する必要があるタイムラインを指定します。

2.  **ファイルの**   場所情報を提供するファイルディレクトリを指定する

3.  **ログを収集し、レポートビューアー**  を起動するコマンドを実行してレポートを生成する

<div>

## <a name="step-1---log-the-timeline"></a>手順 1 - ログのタイムラインを指定する

タイムラインのログを記録するには、以下の図に示すように、次の項目を指定します。

1.  **Start date** レポートを生成するタイムラインの開始日 (例: 2010 年 8 月 1 日)。

2.  **End date** レポートを生成するタイムラインの終了日 (例: 2010 年 9 月 30 日)。
    
    ![Bandwidth Utilization Analyzer の開始日/終了日](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Bandwidth Utilization Analyzer の開始日/終了日")  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a>手順 2 - ファイルのディレクトリを指定する

図に示すように、以下のファイル ディレクトリを指定することができます。

  - **サーバーのログファイルの場所**帯域幅ポリシーサーバーログが保存されているフォルダーの場所。 通常、これは\<、\>\\\<ファイルサーバーで\>\\FE appserverfiles\\PDP を選ぶことができます。

  - **一時ファイルの保存場所**レポートの生成中に中間ファイルが保存される一時ファイルの場所。

![Bandwidth Utilization Analyzer のファイル ディレクトリ](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "Bandwidth Utilization Analyzer のファイル ディレクトリ")

<div>


> [!NOTE]  
> サーバー ログや一時ファイルを格納するフォルダーにアクセスできる十分な権限をツールのユーザーに割り当てるようにしてください。



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>手順 3 - ログを収集してレポート ビューアーを起動する

ログを収集してレポート ビューアーを起動するには、以下の図に示す [**Execute**] をクリックします。この手順により、必要なデータが収集されます。

![Bandwidth Utilization Analyzer でのデータの収集](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Bandwidth Utilization Analyzer でのデータの収集")

入力の検証が正常に行われると、以下のメッセージが表示されます。

![BandwidthUtilizationAnalyzer でログに収集された通知](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "BandwidthUtilizationAnalyzer でログに収集された通知")

[**OK **] をクリックします。BandwidthUtilizationAnalyzer.xlsm は自動的に起動します。メッセージ ボックスの指示に従います。詳細については、次のセクション「**BandwidthUtilizationAnalyzer.xlsm の使用**」を参照してください。

</div>

<div>


**BandwidthUtilizationAnalyzer.xlsm の使用**

1.  BandwidthUtilizationAnalyzer.xlsm が自動的に起動したら、以下の図に示す [**Refresh**] をクリックします。
    
    ![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")

2.  ファイルのフォルダーが開いたら、メッセージ ボックスで指定した場所にある consolidated.csv を選びます。 また、場所が**C:\\Temp**として表示されます。
    
    ![BandwidthUtilizationAnalyzer でフォルダーを開く](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "BandwidthUtilizationAnalyzer でフォルダーを開く")

3.  [**Import**] をクリックします。

4.  グラフィカル プロットが自動的に生成されます。バックグラウンドで作業中のポインターが表示されなくなると、使用できます。
    
    ![レポート ビューでのフィルターの適用](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "レポート ビューでのフィルターの適用")

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a>レポート ビューにフィルターを適用する

レポート ビューに適用できるフィルター (以下の図を参照) は、次のとおりです。

![レポート ビューでのフィルターの適用](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "レポート ビューでのフィルターの適用")

1.  **Name** WAN リンクでフィルター処理 (グラフの右側のフィルター)。プレフィックス (縦長の青いボックスを参照) は、次のようなリンクの種類を示します。
    
      - **S: Site** ネットワーク サイトからネットワーク地域への WAN リンク
    
      - **IS Inter-Site** 2 つのネットワーク サイト間の WAN リンク
    
      - **R Inter-Region** 2 つのネットワーク地域間の WAN リンク

2.  **Exceeded limit** 帯域幅の使用率が帯域幅容量を超過している WAN リンクでフィルター処理

3.  **Critical levels** 帯域幅の使用率が帯域幅容量の 90% 以上に達した WAN リンクでフィルター処理

4.  **Under-utilized** 帯域幅の使用率が帯域幅容量の 25% に達していない WAN リンクでフィルター処理

5.  **Link type** 次に示す WAN リンクの種類でフィルター処理します。
    
      - **Network site** タイプ
    
      - **Inter-site** タイプ
    
      - **Inter-Region link** タイプ

6.  **Region** ネットワーク地域でフィルター処理

次の図は、これまでに紹介したフィルターを示します。

[**Name**] でフィルター処理します。グラフに表示するリンクのリストを選びます。

![BandwidthUtilizationAnalyzer での [Name] でのフィルター処理](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "BandwidthUtilizationAnalyzer での [Name] でのフィルター処理")

[**Exceeded limit**] でフィルター処理します。 フィルターを適用するには、[**True**] を選びます。

![[Exceeded Limit] でのフィルター処理](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "[Exceeded Limit] でのフィルター処理")

[**Critical levels **] でフィルター処理します。 フィルターを適用するには、[**TRUE **] を選びます。

![[Critical Levels] でのフィルター処理](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "[Critical Levels] でのフィルター処理")

[**Under-utilized **] でフィルター処理します。 フィルターを適用するには、[**TRUE **] を選びます。

![[Under Utilized] でのフィルター処理](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "[Under Utilized] でのフィルター処理")

[**Link Type**] でフィルター処理します。 表示する種類を 1 つ以上選びます。

![[Link Type] でのフィルター処理](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "[Link Type] でのフィルター処理")

[**Region**] でフィルター処理します。 リンクを表示する地域のリストを選びます。

![[Region] でのフィルター処理](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "[Region] でのフィルター処理")

</div>

</div>

</div>

<div>

## <a name="requirements"></a>要件

  - .NET Framework 3.5

  - Microsoft Excel 2010 または Excel 2007

</div>

<div>

## <a name="summary"></a>概要

Bandwidth Utilization Analyzer は、ネットワーク全体の UC トラフィックにおける音声の帯域幅の使用状況をプロットするために使用します。このツールは、ビデオの帯域幅の使用状況を報告する場合にも同様に使用できます。

</div>

</div>

<div>

## <a name="call-parkometer"></a>Call Parkometer

Call Parkometer は、コール パーク オービット デバイスに簡単にアクセスできるコマンドライン アプリケーションです。

<div>

## <a name="description"></a>説明

Call Parkometer は、現在パークされている通話を追跡するツールです。 オービットやコール パーク サーバー (CPS) の使用状況に関する統計情報も収集します。 このコマンドラインツールは、CPS への読み取りアクセスと書き込みアクセスの両方を提供します。これには、ローカルまたはリモート接続コンピューターからの SQL Server データベースが使用されます。

すべてのオプションは同時に使用できません。コマンドライン構文は次のとおりです。

  - **–o** パラメーター - このプールで構成されたすべてのオービット範囲を一覧表示します。

  - **–n** パラメーター - このプールで現在使用されているすべてのオービットを一覧表示します。情報は次のように表示されます。
    
      - パーク元とパーク先の SIP Uniform Resource Identifier (URI)。
    
      - 通話のパーク先の CPS のホスト名。
    
      - 通話がパークされた時点のタイムスタンプ。

  - **–f** パラメーター - プールで現在使用されていないオービットの数を一覧表示します。

  - **– r \<n\> **パラメーター—\>最後に\<保留した通話の一覧を表示します。 情報は次のように表示されます。
    
      - パーク先の SIP URI。
    
      - パーク元の SIP URI。
    
      - 通話のパーク先の CPS のホスト名。
    
      - 通話が保留解除または切断された時点のタイムスタンプ。

  - **-t\<n\> **パラメーター-データベース内のオービットを予約して、割り当てられた値の乱数をランダムに表示します。

</div>

<div>

## <a name="output"></a>出力

コマンド プロンプトで指定された入力パラメーターによっては、Call Parkometer に次の出力が表示されます。

  - このプールで構成されたすべてのオービット範囲

  - 現在パークされている通話

  - 有効な (使用可能な) オービットの数

  - 最近パークされた通話

  - 一定およびランダムなオービットの値をテストするために予約されたオービット

</div>

<div>

## <a name="purpose"></a>用途

CPS ツールを使用すると、CPS データベースへのコマンドライン アクセスを確立できます。管理者は、CPS の使用状況を確認して、プールに割り当てられているオービットの数を把握できます。

</div>

<div>

## <a name="requirements"></a>要件

CPS が実行されている同じコンピューターで実行する場合、このツールの使用に必要な条件はありません。 このツールがリモートコンピューターで実行される場合は、Lync Server 2013 で使用される SQL Server データベースがリモートアクセスを許可するように構成されている必要があります。 呼び出しの場合は、プールの SQL Server に接続するために SQL Server データベース接続文字列を使用して構成されている必要があります。 この SQL Server データベース接続文字列は構成ファイルで定義されて**います。** このファイルは、par・・・・・・・・ m の場所にあるのと同じディレクトリに配置する必要があります。 次の XML ファイルは、par・メータの例です。構成する必要があるパラメーターは、ユーザー名 (たとえば、mydomain\\Administrator)、パスワード (mypassword など)、ホスト名 (たとえば、myserver) です。

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

</div>

<div>

## <a name="examples"></a>例

展開されたオービット範囲: –o パラメーターによって、このプールで構成されたすべてのオービット範囲が次のように一覧表示されます。

![Call Parkometer のオービット範囲](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Call Parkometer のオービット範囲")

現在パークされている通話: –n パラメーターによって、このプールで現在使用されているすべてのオービットが次のように一覧表示されます。

![Call Parkometer で現在保留されている通話](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Call Parkometer で現在保留されている通話")

使用されていないオービットの数: –f パラメーターによって、プールで現在使用されていないオービットの数が次のように一覧表示されます。

![Call Parkometer の使用されていないオービット](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Call Parkometer の使用されていないオービット")

最近の保留中の通話: \<–\> r n パラメーター \<は\> 、次に示すように、最後の保留中の通話を一覧表示します。

![Call Parkometer で最近保留された通話](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Call Parkometer で最近保留された通話")

次に示すように、軌道\<予約\>をテストします。-t n パラメーターテストでは、データベース内でオービットを予約しています。

![Call Parkometer のオービット予約のテスト](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Call Parkometer のオービット予約のテスト")

</div>

<div>

## <a name="summary"></a>概要

Call Parkometer は、コール パーク サーバーに関する詳しい情報を提供するコマンドライン ツールです。

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a>CleanupStorageServiceData

CleanupStorageServiceData リソースキットツールを使用すると、Lync Server Storage Service によって使用されているデータベースから、孤立したデータを削除することができます。 ストレージサービスの1つの機能は、Lync Server と、SQL Server や Exchange などのさまざまなバックエンドデータストレージエンドポイント間の通信をバッファリングすることです。

<div>

## <a name="description"></a>説明

高可用性をサポートするために、SS は、プール内の複数のフロントエンドサーバーにあるデータのコピーを受け取り、一時的に保存し、そのデータを最終的な長期保存場所に配信した後、そのデータを削除します。 通常の操作中に、サーバーがクラッシュしたり、処理の問題が発生したりして、一部のデータが正しくクリーンアップされないことがあります。 このデータは無害ですが、制限された処理リソースを消費します。 通常必要となるデータメンテナンスの多くは自動化されていますが、このツールを使用すると、自動削除ができない場合に、孤立したデータの安全な識別と削除を行うことができます。 このツールは、health monitoring System Center Operations Manager (SCOM) アラートが発生したときに表示されます。これにより、管理者は、プール内のローカルの SS データベースから不要なデータを削除するように求められます。 フロントエンドのイベントログに、アラートをトリガーするイベントが表示されます。 イベントの詳細には、フロントエンドに含まれる孤立したデータの量に関する情報が含まれ、そのデータが特定の事前決定しきい値を超えたときに発生します。

</div>

<div>

## <a name="requirements"></a>要件

Lync Server 2013 のリソースキットツールをインストールします。 このツールは、Lync Server および Lync Server 2013 管理シェルがインストールされているドメインに参加しているコンピューターで実行されます。 このツールは、管理シェルのコマンドレットを使用して、プール内のすべてのフロントエンドサーバーを特定します。 第二に、このツールは、 **Rtclocal**データベースがインストールされているプール内のコンピューターから実行する必要があります。 このデータベースは、Lync Server ルーティングサービスとの通信に必要な接続の詳細情報を取得するために CleanupStorageServiceData ツールによって使用されます。最後に、ツールを呼び出すアカウントまたは資格情報に、出力ログの書き込み先のファイル共有への読み取り/書き込みアクセス許可が必要です。また、このツールは、プールが安定した状態にあることに依存します。 つまり、すべてのフロントエンドサーバーが起動して実行されていることが前提となっています。各ルーティンググループは、1つのプライマリフロントエンドサーバーと2つのセカンダリフロントエンドサーバーの完全なセットを持っている必要があります。ervers

</div>

<div>

## <a name="examples"></a>例

C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\\storageservice\> ImportStorageServiceData

    Description:
    This tool will remove orphaned data from the Storage Service database
    for a pool. You are required to run this tool on a machine inside the
    pool which has the Lync Server Management Shell installed and has RtcLocal database installed.
    Usage: Default behavior is to clean up orphaned data from the all the 
           Storage Service databases in the current pool.
    Additional Options:
    -Verbose    : Turn verbose output on.
    -LogPath    : The UNC path to which to write the log.
    ------------------------------------------------------------------------------
    Please wait while we initialize...
    Found 4 front end servers
    Replica Instances for LYSS Service
    Address: server2.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server1.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server3.vdomain.com - Primaries: 7 Secondaries: 14
    Primary Total Count = 28, Secondary Total Count = 56
    Finding and removing orphaned data for 28 routing groups
    Removing 1 stale groups from FE server.vdomain.com
    No stale routing groups detected on FE server2.vdomain.com
    No stale routing groups detected on FE server1.vdomain.com
    No stale routing groups detected on FE server3.vdomain.com
    Searching for stale queue items
    Removed 20 stale queue items for routing group 17D5435AE40259F7BBDF1866776386E4
    No stale queue items found for routing group 1975349662315F90B119DACB4F2AE3AD
    No stale queue items found for routing group 1A23E3D58BDB5A458A0B73F34AB7ACBE
    No stale queue items found for routing group 1AC91E3A1029535A80123121989CEADC
    No stale queue items found for routing group 3313935458E35B9B9759E08A15D251E6
    No stale queue items found for routing group 39BB0035B06B5427873FC6099720462A
    No stale queue items found for routing group 40721948E7B55CE893A53E911F76D185
    No stale queue items found for routing group 4501E04EAE4856059346949FF817C220
    No stale queue items found for routing group 4D833C98801F546F8E45E417EE028E2E
    No stale queue items found for routing group 5AD77443AD955A22A876749BE66D5317
    No stale queue items found for routing group 69844A271E6C5633A1F2B46A42287DD6
    No stale queue items found for routing group 69DA3BE407A95C7284EB4B1337718C93
    No stale queue items found for routing group 8437358AB34A5CC8967D5EF39494AB8D
    No stale queue items found for routing group 8ED455B1789655359816E1C5BF4C430F
    No stale queue items found for routing group 904F6C9B8AC951AE8B3C86684D3832E4
    No stale queue items found for routing group 90AAB3AE9A1950E0ADE7809A27021D63
    No stale queue items found for routing group 944F5724C65C5F93900DC1C8C898B102
    No stale queue items found for routing group 9E8A2630250C51769E39F63F0FB552BA
    No stale queue items found for routing group A11E27AE439A582288D4657EDA86B565
    No stale queue items found for routing group A9B10C76E764556FAEA3E47301EDF518
    No stale queue items found for routing group AEA2699E74ED59848ACEA7896699430D
    No stale queue items found for routing group B269961603E75065AFDA4F4F006DA5E4
    No stale queue items found for routing group BB873D9A3DA959DAB2FD743E5AA619F7
    No stale queue items found for routing group BCC6A48FBA2454B79B9EDB276657A404
    No stale queue items found for routing group C8EF4805722B5F6C876EBC0440B420FD
    No stale queue items found for routing group CA38EBDAC4845489ACE208C2240E4056
    No stale queue items found for routing group F5921887DB025C5F908CE42DB7F1AEE8
    No stale queue items found for routing group F9E606A825395422B3BF7A01ECBB7B1F
    Writing log: M:\Dev\Server\ResKit\StorageService\CleanupStorageServiceData.Log_20121009_151040
    Tool has finished execution.  Errors encountered: 0
    C:\Program Files\Microsoft Lync Server 2013\ResKit\StorageService>

</div>

</div>

<div>

## <a name="dbanalyze"></a>DBAnalyze

<div>

## <a name="description"></a>説明

DBAnalyze は、管理者が Lync Server 2013 データベースに関する分析レポートを収集するのに役立つコマンドラインツールです。 DBAnalyze には、診断モード、ユーザー データ モード、会議モード、MCU モード、ディスク断片化モードが用意されています。

  - **診断モード**   テーブル (レコード数) に関する情報を含むレポートを作成します。断片化、データサイズ、インデックスサイズ)、データとログファイルのサイズ、最後のバックアップ時間、連絡先の配布には、Microsoft Office Communications Server が実行されているサーバー間、アクセス許可の平均数、ユーザーごとに開催される電話会議の平均数、スケジュールされているユーザーあたりの会議の平均数、スケジュールが設定されます。会議、アクティブな会議、データベースのバージョン。
    
    <div>
    

    > [!NOTE]  
    > 診断モードを実行すると、サーバーのパフォーマンスに影響を与えることがあります。

    
    </div>

  - **ユーザーデータモード**  : 指定されたユーザーの連絡先、コンテナー、サブスクリプション、パブリケーション、アクセス許可、連絡先グループのデータ、あるいはそのユーザーを連絡先やアクセス許可の一覧に登録しているユーザーの情報をレポートします。 このモードでは、ユーザーが開催する、または招待された会議の概要データもレポートします。

  - **会議モード**   では、電話会議のすべてのスケジュールの詳細、出席者リスト、会議で許可されているメディアの種類の一覧、アクティブな mcu (multipoint control ユニット)、アクティブな参加者の一覧、各参加者のシグナリング状態など、特定の会議の詳細データが報告されます。

  - **会議 id**  のデコードは、 **/pstnid**スイッチで指定されている公衆交換電話網 (PSTN) 会議 id をデコードしますが、詳細情報についてはバックエンドに接続しません。

  - **会議を解決**   し、 **/pstnid**スイッチで指定されている PSTN 会議 ID をデコードし、ID で示されている会議に関する情報を表示します。

  - **Mcu モード**  では、プール内の各 MCU の ID、メディアの種類、URL、ハートビートの状態、会議のロード、参加者の負荷が報告されます。

  - **ディスクの最適化モード**  では、すべてのディスクの断片化の状態が表示されます。

このツールは、さまざまな問題を診断し、管理者の容量計画を支援するために使用できます。たとえば、サーバー A に所属する大多数のユーザーが、サーバー B に所属するユーザーを連絡先として選択した場合、管理者はサーバー A のユーザーをサーバー B に移動して、サーバー間のトラフィックを削減できます。

</div>

<div>

## <a name="output"></a>出力

このツールは、Lync Server 2013 データベースに関する定義済みレポートを出力します。 **パス:** % ProgramFiles%\\Microsoft Lync Server 2013\\Reskit

</div>

<div>

## <a name="purpose"></a>用途

Dbanalyze .exe をインストールするには、ローカルフォルダーにコピーし、ツールを実行します。 このツールを使用するには、コマンドラインから次のコマンドを実行します。`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` コマンドラインオプションの説明を以下に示します。

![Dbanalyze.exe のコマンド ライン オプション](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Dbanalyze.exe のコマンド ライン オプション")

</div>

<div>

## <a name="requirements"></a>要件

**コンピューター**DBAnalyze は、Lync Server 2013 がインストールされているドメインに参加しているコンピューターからのみ実行できます。

**ネットワーク** コンピューターは、バックエンド データベースに接続できる必要があります。

**ソフトウェア**DBAnalyze を実行する前に、Lync Server 2013 ソフトウェアコンポーネントをインストールする必要があります。

**ユーザー**次の表は、Lync Server 2013 データベースへのアクセスに必要な権限を持っている管理者を示しています。

![Dbanalyze.exe の権限のテーブル](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Dbanalyze.exe の権限のテーブル")

<div>


> [!NOTE]  
> <STRONG>/report:disk</STRONG> モードでは、ローカル管理者のアカウントが必要です。



</div>

</div>

<div>

## <a name="examples"></a>例

次に、有効な Dbanalyze.exe コマンドの例を示します。

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a>概要

DBAnalyzer を使用すると、管理者は Lync Server 2013 データベースの分析をすばやく簡単に行うことができます。

</div>

</div>

<div>

## <a name="importstorageservicedata"></a>ImportStorageServiceData

ImportStorageServiceData リソース キット ツールを使用すると、Storage Service (LYSS) からフラッシュされたキューやエンドポイントのデータを、ストレージ サービスに再インポートできます。

<div>

## <a name="description"></a>説明

Storage Service からのデータのフラッシュは、キュー アイテムの状態やデータベースのサイズに基づいて自動的 (定期的) に行われた可能性があります。 また、プール フェールオーバー コマンドレット、またはそれによって呼び出される StorageServiceFullFlush コマンドレットの手動呼び出しによって行われた可能性もあります。 フロントエンドのデータベースのサイズが通常のレベルよりも上にある場合は、データがより多くエクスポートされる可能性が高いため、データを再インポートしないことをお勧めします。さらに、ストレージサービスキューの増加を引き起こしたエラーの原因となった問題は、まず解決される必要があります (Exchange のエンドポイントエラー、ネットワークの問題、その他の問題など)。

**シナリオ 1:** プールのフェールオーバー中に、各フロントエンドのストレージ サービスからファイルがフラッシュされる場合があります。 フェールオーバーが完了したら、ツールを実行してデータを再インポートする必要があります。

**シナリオ 2:** データは毎日自動的にフラッシュされます。または、特定のサイズのしきい値を超える記憶域サービスデータベースに対応しています (たとえば、60%、80%、90%)。 この自動フラッシュデータは、管理者によって定期的に再インポートされる必要があります。 このような状況では、monitoring の SCOM パックが展開されていない場合、ストレージサービスからフラッシュされるデータに関連するイベントが Lync Server ストレージサービスにあります。 32075のイベント Id (完全なフラッシュ操作が開始されます)、32076 (完全なフラッシュが完了しました)、32082 (メンテナンスレベルのフラッシュ開始)、32083 (メンテナンスレベルのフラッシュの完了)、32089 (データベースの書き込みによるフラッシュ発生)。 注: これらのイベント Id は、RTM リリースに対応しています。 管理者にこれらのイベントが表示される場合は、フラッシュアウトされたファイルがあることを意味します。このデータは定期的にこのツールを使ってインポートし直す必要があります。たとえば、週ごとに1回。

オンラインサービスリリースの場合、Lync Server 用の正常性監視 SCOM pack が展開されていると、管理者に対して、フラッシュされたデータを記憶域サービスに再インポートするように求める新しい通知が表示されることがあります。 警告の原因に対応するイベントは、フロントエンド サーバーのイベント ログに出されます。 イベントの出力には、フラッシュされたデータ ファイルが置かれている親パスや、警告の条件に一致するファイルの個数などが記述されています。 警告の条件は、指定の親パスに Y 日以上前のファイルが X 個以上あることです (X と Y は StorageService 内に事前設定されていますが、APPCONFIG ファイルを変更して上書きできます)。 状態の警告が出されるイベントで、親パスが異なる場合の例を以下に 2 つ示します。 (たとえば、c:\\programdata\\Microsoft\\Lync Server\\storageservice)。 その後、管理者はこの reskit ツールを実行します。

このツールは、ツールが実行されているフロントエンドでデータが所有されていない場合に、このツールが実行されているフロントエンドの CPU と IO の負荷を、他のフロントエンドと共に増やします。 このツールは、フロントエンドの CPU と IO の負荷が高くない場合 (ピーク時間以外の場合など) に、このツールを実行することをお勧めします。 次に、このツールでは、1つのデータファイルをインポートするために 2 ~ 3 分間かかることがあります。 ツールの実行時間を見積もるときは、この点に注意してください。ツールによって生成される詳細ログファイルは、既定でファイルストアに表示されます。 ログファイルの数が MB 以上である可能性があるため、エラーが報告されていない場合は削除します。

![記憶域サーバーのイベント ログのサンプル イベント](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "記憶域サーバーのイベント ログのサンプル イベント")

</div>

<div>

## <a name="requirements"></a>要件

Lync Server 2013 のリソースキットツールをインストールします。 このツールは、Lync Server および Lync Server 管理シェルがインストールされているドメインに参加しているコンピューターで実行されます。 このツールは、管理シェルのコマンドレットを使用して、プール内のすべてのフロントエンドサーバーを特定します。 第二に、このツールは、 **Rtclocal**データベースがインストールされているプール内のコンピューターから実行する必要があります。 このデータベースは、ツールによって、プールの WEBSERVICE ファイル共有の場所を取得するために使用されます。さらに、このツールを使用する前に、各フロントエンドサーバーで、まず、各フロントエンドサーバーで**enable-PSRemoting**を使用して Windows PowerShell リモート処理を有効にする必要があります。また、このツールが実行されているコンピューターの場合もあります。 そうしないと、このツールのリモート Windows PowerShell コマンドが失敗します。 Windows PowerShell リモート処理は、プールの終了後、すべてのフロントエンドサーバーで無効にすることができます。 最後に、ツールを呼び出すアカウントまたは資格情報に、このツールを実行しているプールの webservice ファイル共有への読み取り/書き込みアクセス許可が必要です。 そうしないと、IO 権限のエラーでツールが失敗します。

<div>


> [!NOTE]  
> Windows Server 2012 では、windows PowerShell リモート処理は既定で有効になっていますが、Windows Server 2008 オペレーティングシステムでは有効になっていません。



</div>

</div>

<div>

## <a name="examples"></a>例

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

</div>

</div>

<div>

## <a name="lcssync"></a>LCSSync

LCSSync ツールを使用すると、複数のフォレスト環境に Lync Server 2013 通信ソフトウェアを展開することができます。 このツールは、さまざまなユーザーのフォレストのユーザーやグループを Active Directory ドメインサービスの連絡先オブジェクトとして、Lync Server 2013 がインストールされている中央フォレストに同期するために使用されます。

<div>

## <a name="description"></a>説明

LCSSync は、中央フォレストの同期された Active Directory ドメインサービスの連絡先オブジェクトを使用して、Lync Server のユーザーを有効にします。 シングルサインインを提供するには、プライマリユーザーアカウントが、Lync Server 2013 の中央フォレストの Active Directory ドメインサービスの連絡先オブジェクトにマップされている必要があります。 このツールは、そのマッピングを支援します。 このツールには、Microsoft Identity Integration Server で Management Agents を作成するためのテンプレートが用意されています。

</div>

<div>

## <a name="summary"></a>概要

LCSSync ツールは、マルチフォレスト環境で Lync Server を展開するのに役立ちます。

</div>

</div>

<div>

## <a name="lookupuserconsole"></a>LookupUserConsole

LookupUserConsole ツールは、特定のユーザーに関する内部の Lync Server ルーティング情報を表示します。 この情報は、Microsoft のサポート担当者が展開やルーティングの問題を解決するのに役立つ場合があります。

<div>

## <a name="description"></a>説明

LookupUserConsole を実行すると、SIP アドレスを受け取り、Lync Server の内部ルーティング情報を表示しようとしているコマンドプロンプトが開きます。 LookupUserConsole ツールを終了するには、「**exit**」 と入力します。

</div>

<div>

## <a name="requirements"></a>要件

Lync Server 2013 のリソースキットツールをインストールします。 このツールは、Lync Server がインストールされているドメインに参加しているコンピューターで実行されます。

</div>

<div>

## <a name="examples"></a>例

C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\>lookupuserconsole

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

</div>

</div>

<div>

## <a name="msturnping"></a>MsTurnPing

MSTurnPing ツールでは、Microsoft Lync Server 2013 通信ソフトウェアの管理者は、オーディオ/ビデオエッジとオーディオ/ビデオ認証サービスを実行しているサーバーと、トポロジで帯域幅ポリシーサービスを実行しているサーバーの状態を確認することができます。

<div>

## <a name="description"></a>説明

MSTurnPing ツールを使用すると、Lync Server 2013 通信ソフトウェアの管理者は、オーディオ/ビデオエッジとオーディオ/ビデオ認証サービスを実行しているサーバーと、トポロジで帯域幅ポリシーサービスを実行しているサーバーの状態を確認できます。

このツールを使用すると、管理者は次のテストを実行できます。

1.  音声ビデオ エッジ サーバー テスト: トポロジ内の音声ビデオ エッジ サーバーに対して次のテストを実行します。
    
      - Lync Server の音声/ビデオ認証サービスが開始されていて、適切な資格情報を発行できることを確認します。
    
      - Lync Server の音声/ビデオエッジサービスが開始されていることを確認し、外部境界にリソースを正常に割り当てることができます。

2.  帯域幅ポリシー サービス テスト: トポロジ内の帯域幅ポリシー サービスを実行しているすべてのサーバーに対して次のテストを実行します。
    
      - Lync Server 帯域幅ポリシーサービス (認証) が開始されていて、適切な資格情報を発行できることを確認します。
    
      - Lync Server 帯域幅ポリシーサービス (コア) が開始されていて、帯域幅の確認を正常に実行できることを確認します。

このツールは、トポロジの一部でありローカル ストアがインストールされているコンピューターから実行する必要があります。

</div>

<div>

## <a name="output"></a>出力

このツールでは、各操作の結果が出力されます。

  - **AudioVideoEdgeServer** テストを実行した場合、ツールの出力は次のようになります。
    
      - トポロジで Lync Server の音声/ビデオ認証サービスを提供するコンピューターのテスト結果
    
      - トポロジで Lync Server オーディオ/ビデオエッジサービスを提供するコンピューターのテスト結果

  - **BandwidthPolicyServer** テストを実行した場合、ツールの出力は次のようになります。
    
      - トポロジで Lync Server 帯域幅ポリシーサービス (認証) を提供するコンピューターのテスト結果
    
      - トポロジで Lync Server 帯域幅ポリシーサービス (コア) を提供するコンピューターのテスト結果

</div>

<div>

## <a name="requirements"></a>要件

  - このツールは、トポロジ内のローカル ストアを持つコンピューターから実行する必要があります。

  - このツールは、ローカル ストアへのアクセス権のある管理者として実行する必要があります。

</div>

<div>

## <a name="examples"></a>例

ツールの入力例は、次のとおりです。

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a>概要

このツールは、音声/ビデオおよび帯域幅ポリシーサービスを実行しているサーバーの状態を確認する、Lync Server 2013 管理者にとって有益なリソースになることがあります。

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a>Network Configuration Viewer

Microsoft Lync Server 2013 communication software 管理者は、ネットワーク構成ビューアーを使って、音声などのリアルタイム通信セッションを許可するようにプロビジョニングされている企業の通話受付制御 (CAC) ネットワークトポロジを表示できます。指定した帯域幅に基づいたビデオ通話。 Lync Server 2013 管理者は、Lync Server 2013 と共にインストールされている帯域幅ポリシーサービスによって適用される CAC ポリシーを定義します。

<div>

## <a name="description"></a>説明

Network Configuration Viewer (NetworkConfigurationViewer.exe) を使用すると、管理者は次のタスクを実行できます。

  - 画像形式での Lync Server 2013 展開からの CAC ネットワークトポロジの読み込みと表示。

  - 帯域幅ポリシー サーバー ログ ファイルの CAC ネットワーク トポロジを読み込み、図の形式で表示する。

  - CAC ネットワーク トポロジを XML 形式でディスクに保存、格納する。

  - CAC ネットワーク トポロジ図を JPG または BMP 形式で保存、格納する。

  - CAC ネットワーク トポロジ構成データを表示する。

  - CAC ネットワーク トポロジをツリー形式で表示する。

  - CAC ネットワーク トポロジ リンク (サイトから地域、地域から地域、サイトからサイトの各リンクなど) のカスタム コネクタを定義する。

  - CAC ネットワーク トポロジのサイト情報、地域情報、プロビジョニングされた帯域幅ポリシーとネットワーク リンクを表示する。

</div>

<div>

## <a name="purpose"></a>用途

企業の CAC ネットワーク トポロジ リンクをグラフィカル インターフェイスで表示します。

</div>

<div>

## <a name="examples"></a>例

**次のグラフィカルな形式の Lync Server 2013 展開からの CAC ネットワークトポロジの読み込みと表示を行います。** Lync Server 2013 管理者は、次の図に示すように、[**ネットワーク構成のダウンロード**] オプションを使用して、すべての lync server 2013 コンピューターで CAC ネットワークトポロジの構成を読み込んで表示することができます。 このツールでは、Lync 構成ストアへの接続がないコンピューターに展開すると、このような構成がダウンロードまたは表示されなくなります。

![ネットワーク構成のダウンロード](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "ネットワーク構成のダウンロード")

**帯域幅ポリシーサーバーログファイルからの CAC ネットワークトポロジを、グラフィカル形式で読み込み、表示します。** Lync Server 2013 帯域幅ポリシーサーバーは、CAC ネットワークトポロジを、Lync Server 2013 ファイル共有の場所にあるログメカニズムの一部として保存します。 Lync Server の管理者は、次に示すように、 **[ネットワーク構成を開く**] オプションを使用して、このようなファイルをグラフィカルな形式で表示できます。

![帯域幅ポリシー サーバーのログ ファイルを開く](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "帯域幅ポリシー サーバーのログ ファイルを開く")

次に示すように、ディスク上の XML 形式で CAC ネットワークトポロジを保存して保存します。 Lync Server 2013 管理者は、次のように [**ネットワーク構成のコピーを保存**] オプションを使用して、cac ネットワークトポロジ構成ファイルを xml 形式で保存することができます。 保存した構成ファイルはオフラインでのグラフィカルな表示に使用できます。

![ネットワーク構成の XML ファイルとしての保存](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "ネットワーク構成の XML ファイルとしての保存")

CAC ネットワークトポロジ図を JPG または BMP 形式で保存して保存します。 Lync Server 2013 管理者は、次に示すように**ネットワーク構成ダイアグラムを [画像として保存**] オプションを使って、cac ネットワークトポロジ構成をグラフィカルな形式 (JPG と bmp ファイル形式) で保存できます。

![ネットワーク構成の画像としての保存](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "ネットワーク構成の画像としての保存")

**CAC ネットワークトポロジ構成データを表示します。** Lync Server 2013 管理者は、以下に示すように [ネットワーク構成データの表示] オプションを使用して、ネットワーク領域、ネットワークサイト、帯域幅プロファイル、サイトサブネットの IP アドレスなどの関連ネットワーク構成データをテキスト形式で表示できます。

![ネットワーク構成データの表示](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "ネットワーク構成データの表示")

**ツリービュー形式で CAC ネットワークトポロジを表示します。** Lync Server 2013 管理者は、次に示すように、ツールウィンドウの左側にあるコントロールパネルを使用して、関連するネットワーク構成データをグラフィカルなツリービュースタイルで表示できます。

![ネットワーク構成データのツリー ビューでの表示](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "ネットワーク構成データのツリー ビューでの表示")

**CAC ネットワークトポロジリンク (サイト間、地域間、サイト間リンクなど) 用のカスタムコネクタを定義します (例:** Lync Server 2013 管理者は、以下に示すように [設定] オプションを使用して、CAC ネットワーク構成の WAN リンク用のカスタムグラフィカルコネクタを定義できます。 これは、ネットワーク構成にプロビジョニングされている各種ネットワーク リンクを区別するのに役立ちます。

![CAC ネットワークトポロジ用のカスタムコネクタを定義する](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "CAC ネットワークトポロジ用のカスタムコネクタを定義する")

**CAC ネットワークトポロジのサイト情報、地域情報、およびプロビジョニングされた帯域幅ポリシーを表示します。** Lync Server 2013 管理者は、以下に示すオプションを使用して、関連する CAC ネットワークの領域情報、サイト情報、および CAC 帯域幅プロビジョニングの情報を表示できます。 (たとえば、ネットワーク領域またはネットワークサイトオブジェクトの [**情報**] をクリックします)。

![ネットワークのカスタム コネクタの定義](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "ネットワークのカスタム コネクタの定義")

</div>

<div>

## <a name="summary"></a>概要

このツールは、Lync Server 2013 管理者が、グラフィック形式で展開するための CAC ネットワークトポロジを表示したい場合に役立ちます。

</div>

</div>

<div>

## <a name="response-group-agent-live"></a>Response Group Agent Live

応答グループ アプリケーションによって、エージェントは組み込みの Web サービスを使用してリアルタイムの有効な情報にアクセスできるようになります。 ただし、このデータのグラフィカル表示はアプリケーションの外部では使用できません。 応答グループエージェントのライブリソースキットツールでは、他のエージェントの存在など、リアルタイムの Microsoft Lync 2013 通信ソフトウェア情報を使用して、この情報に簡単かつグラフィカルな方法でアクセスできるため、この問題が解決されます。

<div>

## <a name="description"></a>説明

Response Group Agent Live は、サインインやサインアウト機能、リアルタイム情報 (グループのメンバーシップや現在の通話数など) を応答グループ エージェントに提供する Windows アプリケーションです。 これは、[エージェントグループ] ページの拡張バージョン (Lync 2013 からアクセス可能) であることを目的としています。

</div>

<div>

## <a name="purpose"></a>用途

着信通話は応答グループ アプリケーションによってキューに配置されてから、エージェント グループにルーティングされます。どの通話を処理するかについて十分な情報に基づいて判断するために、エージェントは他のエージェントの状態や各キューで待機中の通話数など、エージェント グループに関するリアルタイム情報にアクセスできます。このような情報は、当初は応答グループ サービスからのみアクセスが可能でしたが、Response Group Agent Live によって直感的な方法で利用できるようになりました。

<div>

## <a name="features"></a>機能

応答グループエージェント Live ツールは、応答グループサービスと Microsoft Lync 2013 SDK に基づいて構築されます。 このツールは応答グループ サービスから利用できる情報や機能 (グループのメンバーシップ、他のエージェントのプレゼンス、待機中の通話数など) を応答グループ エージェントに提供します。

下の図は、Response Group Agent Live のメイン インターフェイスを示しています。

![Response Group Agent Live ツール](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "Response Group Agent Live ツール")

Response Group Agent Live では、エージェントは次の主な 3 つの機能を使用できます。

  - **サインイン/チェックアウト:** Lync 2013 からアクセスできる [エージェントグループ] ページとは異なり、応答グループエージェントの Live では、エージェントのみが一度にサインインまたはサインアウトすることができます。 このアプリケーションでは、次の3つの簡単な方法でエージェントにサインインまたはサインアウトできます。
    
      - アプリケーション内でサインイン/サインアウト (緑色と赤色) ボタンをクリックします。
    
      - システム トレイ アイコンを右クリックし、サインインまたはサインアウトを選択します。
    
      - 構成可能なキーボード ショートカットを使用します。

  - **グループメンバーシップ:**[エージェント] グループが選択されている場合、[応答グループエージェント Live] は、右側のウィンドウにこのグループのエージェントの一覧を表示します。 Lync 2013 がこのアプリケーションと同じコンピューターで実行されている場合、プレゼンス情報と連絡先カードが応答グループエージェントの Live に表示されます。 担当者は、そこから直接 IM を送信したり、他のエージェントに直接通話を発信したりできます。

  - **リアルタイム統計情報:** Response Group Agent Live ではすべてのエージェント グループのリアルタイム統計情報を使用できます。更新間隔は 1 分です。応答グループが通話に応答すると、グループ名の横に視覚的なインジケーターが追加され、キュー内の現在の通話数が表示されます。グループにマウスを合わせると、最長の待機時間も表示されます。

</div>

</div>

<div>

## <a name="requirements"></a>要件

Response Group Agent Live には .NET Framework 4.0 が必要です。 さらに、プレゼンスと連絡先カードの機能を活用するには、Lync 2013 をローカルでインストールし (実行中) 必要があります。

<div>

## <a name="configuration"></a>構成

アプリケーションの [Options] ダイアログ ボックスを使用すると、Response Group Agent Live を個人の好みに合わせてカスタマイズできます。また、管理者は RGAgentLive.exe.config ファイルの defaultHostAddress プロパティを直接編集して既定のホスト アドレスを定義できます。

下の図は、エージェントがホスト アドレスやショートカット キーを構成できる [Options] ダイアログ ボックスを示しています。このダイアログを表示するには、メイン インターフェイスの右上にある [Options] ボタンをクリックします。

![[Response Group Agent Live Options] ダイアログ ボックス](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "[Response Group Agent Live Options] ダイアログ ボックス")

Response Group Agent Live の構成では次の 3 つの設定をカスタマイズできます。

  - [Host address]: これは通常、エージェントのホーム プールに属する Web プール FQDN です。この情報から、正確な応答グループ サービス アドレスがバックグラウンドで自動的に取得されます (ホストの後に適切なパスが付加されます)。

  - [Shortcuts]: サインイン/サインアウト用の厳密なショートカットをカスタマイズできます。唯一の制約として、ショートカットでは 1 つ以上のキーのほかに "Windows ロゴ" キーを使用する必要があります。

  - [Start with Windows]: Windows と共に自動的に起動するようにアプリケーションを構成できます。

</div>

</div>

<div>

## <a name="examples"></a>例

下の図は、右側のウィンドウで連絡先を右クリックして、他のエージェントに電話をかけたり IM を送信したりする方法を示しています。

![通話の発信または IM の送信](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "通話の発信または IM の送信")

下の図は、Response Group Agent Live に表示されるキュー内の現在の通話数と全着信通話内での最長待機時間を示しています。

![キュー情報の表示](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "キュー情報の表示")

</div>

<div>

## <a name="summary"></a>概要

迅速なサインインとサインアウト、グループのメンバーシップ、基本的なリアルタイム統計情報は、アプリケーション外部でのみ利用できる、応答グループ サービスに基づいた便利な応答グループ エージェント機能です。 応答グループエージェントのライブリソースキットツールを使用すると、Lync 管理者は、迅速かつグラフィカルな方法でタスクを実行できる Windows アプリケーションでエージェントを提供できます。

</div>

</div>

<div>

## <a name="sefautil"></a>SEFAUtil

SEFAUtil (セカンダリ拡張機能のアクティブ化) は、Microsoft Lync Server 2013 通信ソフトウェア管理者およびヘルプデスクエージェントが代理人の呼び出し、着信の転送、同時呼び出し、チーム呼び出しを構成できるようにするコマンドラインツールです。Lync Server 2013 ユーザーの代わりに、設定とグループの通話が集配されます。 このツールを使用すると、管理者は、特定のユーザーに対して公開されている通話ルーティング設定を照会することもできます。SEFAUtil ツールを使用すると、管理者は、ユーザーの代わりに着信の転送を有効または無効にしたり、変更したりすることができます。 管理者は、(SIP URI の形式で) ターゲットを指定するか、またはユーザーによって既に公開されているターゲットを使用できます。 このツールでは、管理者がユーザーに代わって代理人またはチーム呼び出しグループのメンバーを追加または削除することもできます。このツールは、Microsoft ユニファイドコミュニケーションマネージ API (UCMA) 3.0 に基づいて構築されており、管理者が SEFAUtil の中央管理ストアで信頼済みアプリケーションを作成する必要があります。

SEFAUtil (セカンダリ拡張機能のアクティブ化) lync Server 2013 管理者およびヘルプデスクエージェントは、Lync Server 2013 ユーザーの代わりに、代理人、着信の転送、同時呼び出し、チーム呼び出しの設定、グループの通話ピックアップを構成することができます。. また、管理者は特定のユーザー向けに公開されているコール ルーティング設定のクエリを実行できます。

<div>

## <a name="description"></a>説明

SEFAUtil の現在のバージョンは、コマンドラインツールにすぎません。グラフィカルユーザーインターフェイスはサポートされていません。 このツールは、Microsoft ユニファイドコミュニケーションマネージ API (UCMA) 3.0 に基づいています。 このツールの機能により、管理者やヘルプデスクの担当者は次の作業を行うことができます。

  - ユーザーのすべてのコール ルーティング設定を表示する (着信転送、代理人、同時呼び出し、チーム呼び出し、グループ通話ピックアップなど)

  - 着信転送設定を有効化、無効化、変更する (宛先や無応答タイマーなど)

  - 着信転送の即時構成を有効化、無効化、変更する

  - 代理人設定を有効化、無効化、変更する

  - チーム呼び出しグループ設定を有効化、無効化、変更する
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 SEFAUtil の新ツール

    
    </div>

  - 同時呼び出し設定を有効化、無効化、変更する (宛先など)
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 SEFAUtil の新ツール

    
    </div>

  - グループ通話ピックアップ設定を有効化、無効化、変更する
    
    <div>
    

    > [!WARNING]  
    > Lync Server 2013 SEFAUtil の新ツール

    
    </div>

このツールの制約は次のとおりです。

  - Lync Server プールに所属しているユーザーのみがサポートされます

  - 複数ユーザーのコール ルーティング設定の一括編集はサポートされていません。

</div>

<div>

## <a name="output"></a>出力

ツールの現在のバージョンでは、[コマンド プロンプト] ウィンドウでのみ結果が表示されます。詳しくは、このドキュメント後半の「例」をご覧ください。

</div>

<div>

## <a name="purpose"></a>用途

このツールを使用するいくつかの主なシナリオを次に示します。

  - Bob は役員で、Lync Server テレフォニーに移動されました。 彼の既存の PBX システムには代理人が設定されています。 Lync への移行の一環として、管理者は、Bob のルーティングを構成して、既存の委任構成を反映させることができます。

  - 西村さんは旅行中で、顧客からの重要な連絡を待っています。しかし、ホテル滞在中はコンピューターを使うことができません。彼女はヘルプデスクに電話して、勤務先電話番号にかかってきたすべての電話を携帯電話の番号に転送してもらうよう頼みました。ヘルプデスク担当者は、彼女のためにこのような構成を行うことができます。

  - 松本さんの勤務先電話番号にかかってくる電話は、勤務中は常に彼の携帯電話のボイスメールに送信されています。しかし、他の多くの場所では通話は問題なく機能しているようです。ヘルプデスクの技術者は松本さんのルーティング構成を確認できるので、彼の携帯電話に同時呼び出しが構成されていることを見つけます。技術者は松本さんにオフィスでの通信状態についてたずね、通信状態が良くない場合に着信通話を携帯電話のボイスメールへ送信しているのは同時呼び出しルールであることを特定できます。

  - Mike は Contoso の新入社員で、新しいチームに参加して、すべてのメンバーがチーム呼び出し用に構成されています。 Microsoft Lync が有効になっている場合、管理者はチーム呼び出しグループ設定を設定して、すべての新しいチームメンバーを含めることができます。さらに、管理者は、チームのメンバー全員のチーム呼び出しグループメンバーとして Mike を追加します。

  - Contoso の人事部門のカスタマー サービス プラクティスとは、すべての発信者に対して最初の電話から個人サービスを提供することです。 部門のメンバー全員がお互いのすぐそばに座っているとすれば、チーム呼び出しで全員の電話が一斉に鳴るのはチームにとって非常に混乱のもとになります。 チームメンバーを邪魔することなく最良のサービスを提供するために、Lync 管理者はグループ通話のピックアップ機能を利用します。 管理者は部門の全員をピックアップ グループに追加して、ピックアップ グループ番号を伝えます。 原田さんが席を外している場合は、彼女の電話が鳴っていることに気付いた松本さんが自分の席から電話に応答します。

</div>

<div>

## <a name="requirements"></a>要件

SEFAUtil ツールは信頼されたアプリケーション プールに属しているコンピューターでのみ実行できます。このコンピューターには UCMA 3.0 がインストールされている必要があります。ツールを実行するには、SEFAUtil アプリケーション ID を持つ新しい信頼されたアプリケーションをプール内に作成する必要があります。

**SEFAUtil ツール用の新しい信頼されたアプリケーションの作成**

1.  SEFAUTil ツールは信頼されたアプリケーション プールに属しているコンピューターでのみ実行できます。 必要に応じて、新しい信頼できるアプリケーションプールとしてプールを追加するには、次のコマンドレットを実行して、Lync Server 管理シェルを使用します。
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > SEFAUtil ツールを実行するコンピューターには UCMA 3.0 をインストールする必要があります。

    
    </div>

2.  信頼されたアプリケーションを SEFAUtil ツールのトポロジ内に定義する必要があります。 SEFAUtil を新しい信頼されたアプリケーションとして定義するには、Lync Server 管理シェルを使用して、次のコマンドレットを実行します。
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > 必要に応じて、別のポートを使用できます。

    
    </div>

3.  トポロジの変更を有効にする必要があります。 トポロジの変更を有効にするには、次のコマンドレットを実行します。
    
        Enable-CsToplogy

4.  必要に応じて、SEFAUtil ツールの実行に使用するサーバーに Lync Server 2013 リソースキットツールをインストールします (サーバーは、信頼されたアプリケーションプールの一部である必要があります)。

5.  SEFAUtil が正しく実行していることを確認します。 そのためには、Windows コマンド プロンプトから管理者権限でツールを実行し、展開内のユーザーの着信転送設定を表示します。 既定では、ツールは次の場所に配置されます: "...\\Program Files\\Microsoft Lync Server 2013\\Reskit "。 ユーザーの着信転送設定を表示するには、次のコマンドを実行します。
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    ユーザーの着信転送設定が表示されます。

<div>

## <a name="group-call-pickup"></a>グループ通話ピックアップ

グループ通話のピックアップ機能を完全に有効にするには、Lync Server で追加の構成を行う必要があります。 ユーザーにピックアップ グループを割り当てる前に、この機能の計画と展開の手順について、グループ通話ピックアップの製品ドキュメントを参照してください。

</div>

</div>

<div>

## <a name="examples"></a>例

<div>

## <a name="display-current-call-handling-settings"></a>現在の通話処理設定の表示

次のコマンドでは、ユーザーの通話処理が表示されます。 `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> この例では、 <STRONG>/server</STRONG>スイッチを使用して、接続先の Lync server を指定します。



</div>

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a>着信転送/応答なしの宛先の設定

この例では、着信転送/応答なしの宛先と呼び出しの遅延を設定します。 ここでは、/server スイッチは提供されません。SEFAUtil が Lync サーバーの自動検出を試みます。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a>着信転送の即時有効化

この例では、別のユーザーへの着信転送をすぐに有効にします。

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a>着信転送の即時無効化

この例では、別のユーザーへの着信転送をすぐに無効にします。

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>代理人としてのユーザーの追加と代理人の同時呼び出しの設定

この例では、ユーザーを代理人として追加し、代理人の同時呼び出しを設定します。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a>代理人の同時呼び出しルールの変更

この例では、前の例で設定した代理人の同時呼び出しルールを遅延呼び出しルールに変更します。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a>代理人の削除

この例では代理人を削除します。

<div>


> [!NOTE]  
> 最後の代理人が削除されると、代理人着信は自動的に無効になります。



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>代理人の追加と代理人への着信転送ルールの設定

この例では、代理人を追加し、代理人への着信転送ルールを設定します。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>同時呼び出しの有効化と宛先番号の設定

この例では、同時呼び出しを有効にして、同時呼び出しの宛先番号を設定します。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> 既に同時呼び出しを有効にしているユーザーの同時呼び出しの宛先番号を変更するには、コマンドに /enablesimulring スイッチを追加します。追加しない場合、宛先番号は変更されません。



</div>

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a>同時呼び出しの無効化

この例では、同時呼び出しを無効にします。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>チーム呼び出しのチーム メンバーの追加とチーム呼び出しメンバー グループへの同時呼び出しの設定

この例では、ユーザーのチーム呼び出しグループにチーム メンバーを追加し、チーム呼び出しグループへの同時呼び出しを有効にします。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> ユーザーのチーム呼び出しグループにチーム メンバーを追加すると、ユーザーの同時呼び出しの設定がチーム呼び出しグループを同時に呼び出すように自動的に切り替わります。



</div>

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a>チーム呼び出しグループからのメンバーの削除

この例では、ユーザーのチーム呼び出しグループからチーム メンバーを削除します。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> 削除対象のメンバーがチーム呼び出しグループで唯一のメンバーである場合、チーム呼び出しグループの同時呼び出しは自動的に無効になります。



</div>

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a>チーム呼び出しグループの遅延呼び出しの設定

この例では、チーム呼び出しグループの時間設定の遅延呼び出しを変更します。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a>チーム呼び出しの有効化

この例では、ユーザーのチーム呼び出しを有効にします。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> ユーザーのチーム呼び出しグループにメンバーがいない場合、チーム呼び出しは有効になりません。



</div>

**出力**

</div>

<div>

## <a name="disable-team-call"></a>チーム呼び出しの無効化

この例では、ユーザーのチーム呼び出しを無効にします。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>グループ通話ピックアップの有効化とユーザーへのピックアップ グループの割り当て

この例では、ユーザーにピックアップ グループを割り当て、グループ通話ピックアップを有効にします。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a>グループ通話ピックアップの無効化

この例では、特定のユーザーのグループ通話ピックアップを無効にします。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> ユーザーのグループ通話ピックアップを無効にした場合、ユーザーに割り当てられたグループ番号は保持されません。そのユーザーのグループ通話ピックアップを後からもう一度有効にする場合は、/enablegrouppickup スイッチでグループ番号をもう一度割り当てる必要があります。



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a>SYSPrep.ps1

<div>

## <a name="description"></a>説明

Sysprep.inf は、Windows Server 2008 オペレーティングシステムコンピューターに次の Lync Server 2013 の前提条件をインストールする Windows PowerShell スクリプトです。

  - Microsoft .Net Framework 4.5

  - Microsoft SQL Server Express

  - Windows Powershell バージョン 3.0

  - Visual C++ 2010 再頒布可能パッケージ

  - Internet Information Server の更新プログラム

  - Windows Identity Foundation

  - Lync Server 2013 コアファイル

このスクリプトは Microsoft Windows オペレーティング システム用のシステム準備ツールと名前は似ていますが、別のツールです。 このスクリプトでは、Lync Server 2013 に必要な前提条件のみをインストールします。 これらの必須コンポーネントをインストールしたら、Windows SYSPrep ツールを使用して、サーバーのイメージを作成できます。

</div>

<div>

## <a name="requirements"></a>要件

Sysprep.inf スクリプトを実行する前に、必須ファイルを Windows Server 2008 オペレーティングシステムコンピューター上のローカルフォルダー (例 **: D:\\Setup)** にコピーする必要があります。 このフォルダーには、Lync Server 2013 ファイルのコピー **(具体的に**は setup.exe) も含める必要があります。 必須ファイルは、次の場所からダウンロードできます。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>必須コンポーネント</th>
<th>場所</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft .Net Framework 4.5</p></td>
<td><p>http://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p>Microsoft SQL Server Express 2008 R2</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p>Windows Powershell バージョン 3.0</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p>Visual C++ 2010 再頒布可能パッケージ</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p>Internet Information Server の更新プログラム</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 Setup.exe</p></td>
<td><p>Lync Server 2013 メディアからのコピー</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a>パラメーター

**–SetupFolder** パラメーターは必須コンポーネント ファイルのディレクトリの場所を引数として受け取ります。

</div>

<div>

## <a name="examples"></a>例

Sysprep.inf スクリプトを実行して Lync Server 2013 の前提条件をインストールするには、管理者特権のコマンドプロンプトから次のコマンドを実行します。

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a>Unassigned Number Announcements Migration

未割り当ての番号のお知らせ移行ツールを使用すると、Lync 管理者は、アナウンスメントアプリケーションによって提供されている、割り当てられていない番号の構成を、ソースの Lync サーバーまたはプールから送信先の Lync サーバーまたはプールに移動できます。

<div>

## <a name="description"></a>説明

Unassigned Number Announcements Migration ツールは Windows PowerShell スクリプトであり、アナウンス アプリケーションによるサービスを受けている未使用の番号の構成を移行元のサーバーまたはプールから別のサーバーまたはプールに移行します。

Unassigned Number Announcements Migration スクリプトを実行すると、次の操作が行われます。

1.  移行元のサーバーまたはプールでホストされているアナウンス アプリケーションの未使用の番号のアナウンスが使用しているすべての音声ファイルを、移行先のサーバーまたはプールのファイル ストアに移行します。
    
    <div>
    

    > [!NOTE]  
    > オーディオファイルは、移行先のプールにコピーされると、ソースプールから削除されます。

    
    </div>

2.  移行元のサーバーまたはプールでホストされているアナウンス アプリケーションに構成されているすべての未使用の番号のアナウンスを、移行先のサーバーまたはプールに移行します。

3.  移行元のサーバーまたはプールでホストされているアナウンス アプリケーションによるサービスを受けているすべての未使用の番号の範囲を、移行先のサーバーまたはプールにもう一度割り当てます。

スクリプトの実行が成功すると、移行元のサーバーまたはプールでホストされているアナウンス アプリケーションによるサービスを受けていたすべての未使用の番号の範囲が、同じ構成を使用して移行先のサーバーまたはプールによるサービスを受けるようになります。

</div>

<div>

## <a name="output"></a>出力

**ムーブグループの移動 Ementconfiguration**スクリプトは、Lync 管理シェルウィンドウで、移行操作の成功または失敗を実行した場所を示します。

エラーによって操作の実行が中断した場合、移行に成功した未使用の番号の範囲は稼動状態で移行先に残り、移行する予定の残りの未使用の番号の範囲も稼動状態で移行元に残ります。残りの構成を完全に移行するには、エラーを修正してからもう一度スクリプトを実行します。

</div>

<div>

## <a name="purpose"></a>用途

Unassigned Number Announcements Migration スクリプトは、次の 3 つのシナリオで使用できます。

  - **構成設定を新しいバージョンの Lync Server に移行する:** Contoso は Lync Server 2013 への移行プロセス中であり、移行プロセスの一環として、lync server の管理者は、アナウンスメントアプリケーションによってサービスされている、割り当てられていない番号の構成を Lync Server 2010 の展開から新しい Lync Server 2013 の展開に移動することを希望しています。 設定を移動するには、Lync Server の管理者が、割り当てられていない番号のお知らせ移行ツールを使用します。

  - **Lync server 2013 から Lync server 2010 に展開をロールバックする:** 予期しない問題が発生したため、Contoso は移行を新しい Lync Server 2013 展開にロールバックする必要があります。 サービスの中断を最小限に抑えるため、Lync Server 管理者は、割り当てられていない番号のお知らせ移行ツールを使用して、Lync Server 2013 の展開から Lync Server 2010 の展開に構成をロールバックします。

  - **Lync の展開間でデータを移動する:** Contoso は、1つのプールのすべてのサーバーを新しいサーバーに置き換えるプロセスを進めています。 新しい Lync Server 2013 プールを展開し、古いプールから新しいプールにすべてのデータを移動して、古いプールを廃止するという戦略があります。 新しいプールを展開した後は、Unassigned Number Announcements Migration ツールを使用して、古いプールから新しいプールに構成を移行します。

<div>

## <a name="requirements"></a>要件

ツールの正常な実行に必要な主な要件は、次のとおりです。

1.  このスクリプトは、Lync Server 2013 管理シェルがインストールされているコンピューターから実行する必要があります。

2.  お知らせアプリケーションは、移行元と移行先の Lync サーバーまたはプールに正常に展開される必要があります。

<div>

## <a name="move-csannouncementconfiguration-script"></a>Move-CsAnnouncementConfiguration スクリプト

Move-CsAnnouncementConfiguration スクリプトでは、下の表に示す 2 つのパラメーターが必要です。

![Move-CsAnnouncementConfiguration のパラメーター](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration のパラメーター")

</div>

</div>

</div>

<div>

## <a name="examples"></a>例

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a>割り当てられていない番号のお知らせの構成を Lync Server 2010 プールから Lync Server 2013 プールに移動する

この例では、割り当てられていない番号のアナウンスをソースプール (Lync Server 2010) から移行先プール (Lync Server 2013) に移動します。

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a>割り当てられていない番号のお知らせの構成を Lync Server 2013 プールから Lync Server 2010 プールに移動する

この例では、割り当てられていない番号のアナウンスをソースプール (Lync Server 2013) から移行先プール (Lync Server 2010) に移動します。

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a>Web Conf Data

Web Conf データツールを使用すると、Lync Server 2013 通信ソフトウェアの管理者は開催者の Web 会議に関連付けられたデータをより詳細に制御できます。 特定のユーザーの会議データをタイムスタンプの条件に基づいて削除する場合などのシナリオが考えられます。

<div>

## <a name="description"></a>説明

このツールを使用すると、管理者は次の操作を実行できます。

1.  1 人のユーザーに関連付けられているすべての Web 会議データを検索する。

2.  1 人のユーザーに関連付けられているすべての Web 会議データを削除する。

3.  特定の日付よりも古い、1 人のユーザーに関連付けられているすべての Web 会議データを削除する。

4.  ユーザーがあるプールから別のプールに移行した場合に、その 1 人のユーザーに関連付けられているすべての Web 会議データを移行する。

<div>


> [!NOTE]  
> Lync Server 2010 用のリソースキットツールでは、1人のユーザーに関連付けられたすべての Web 会議データを別のプールに移動することができました。 このツールでは <STRONG>MoveConferenceData</STRONG> パラメーターのほうを優先して、この機能は現在廃止されています。 このパラメーターの詳細については、「<A href="https://technet.microsoft.com/en-us/library/gg398528(v=ocs.15)">移動-CsUser</A>コマンドレット」を参照してください。



</div>

このツールでは、非アクティブな会議の会議データのみが削除されます。アクティブな会議 (開催中の会議) は削除できません。

このツールはターゲット ユーザーと同じプール内にあるコンピューターから実行する必要があります。会議コンテンツ データをこのツールで管理しているユーザーは同じユーザー プールに所属している必要があります。

</div>

<div>

## <a name="output"></a>出力

このツールでは、次の各操作の結果が出力されます。

  - クエリを実行した場合は、該当のユーザーを開催者とする、すべての非アクティブな会議のデータ フォルダーの一覧が出力されます。

  - 削除を実行した場合は、削除対象のデータがあるすべての会議データ フォルダーの一覧が出力されます。

</div>

<div>

## <a name="requirements"></a>要件

このツールは、開催者が現在所属しているのと同じプール内で実行する必要があります。

このツールは、コンテンツ ファイル ストアへのアクセス権を持つ管理者特権を使用して実行する必要があります。

</div>

<div>

## <a name="examples"></a>例

下の表にパラメーターを示します (一部は例で使用されています)。

![Web Conf Data ツールのパラメーター](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web Conf Data ツールのパラメーター")

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

上の例は query コマンドの動作を示しています。このコマンドの出力は、ツールの影響を受けるすべての会議コンテンツ フォルダーの一覧になります。

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

上の例は delete コマンドの動作を示しています。delete コマンドにより、このユーザーのすべての非アクティブな会議フォルダーが削除されます。

</div>

<div>

## <a name="summary"></a>概要

このツールは、会議データをより正確に制御する必要のある管理者にとって役立つツールとなります。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>
