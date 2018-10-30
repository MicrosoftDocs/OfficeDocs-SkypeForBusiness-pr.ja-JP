---
title: Lync Server 2013 リソース キット ツール ドキュメント
TOCTitle: Lync Server 2013 リソース キット ツール ドキュメント
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945604(v=OCS.15)
ms:contentKeyID: 52056773
ms.date: 09/30/2014
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 リソース キット ツール ドキュメント

 

_**トピックの最終更新日:** 2014-01-09_

このトピックでは、Lync Server 2013 リソース キットを構成する各ツールの用途や例などについて説明します。Lync Server 2013、リソース キット ツール は、Lync Server 2013 を展開して管理する IT 管理者が日常的なタスクを遂行するのに役立ちます。たとえば、**Web Conf Data** ツールを使用すると、オンライン会議中にユーザーによってアップロードされたデータを簡単に制御できます。**SEFAUtil** ツールを使用すると、ユーザーの問い合わせに対して自動転送や自動応答を設定できます。IT 管理者はこれらのツールを活用して、Lync Server 2013 を効果的に管理することをお勧めします。

## リソース キット ツールのインストール

Lync Server 2013、リソース キット ツールをインストールするには、**OCSReskit.msi** をダウンロードします。リソース キット ツール インストーラーは、ダウンロード センター ([http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429)) からダウンロードしてください。

**OCSResKit.msi** を実行すると、簡易インストールが行われます。.msi によって、**%Program Files%\\Microsoft Lync Server 2013\\ResKit** のパスにすべてのツールがインストールされます。このフォルダーには、自己完結型のツールの実行可能ファイルが格納されます。各ツールのファイルは、それぞれのサブフォルダーに格納されます。

## サポートされる環境

最適なパフォーマンスの実現のため、Lync Server 2013、リソース キット ツール は Lync Server 2013 に求められる仕様を満たす同じ環境にインストールすることをお勧めします。

## リソース キット ツールの概要

次の一覧は、Lync Server 2013 リソース キットに用意されているツールを示します。各ツールの要件と例については、次のセクションで説明します。

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

## ABSConfig

アドレス帳サービス構成ツール (ABSConfig) は、管理者が Lync Server 2013 のアドレス帳サービス構成をカスタマイズするのに役立つ管理ツールです。また、このツールを使用すると、Lync Server 2013 の管理者はアドレス帳サービスの既定の設定を復元できます。

## 説明

ABSConfig は、管理者がアドレス帳サービスに関連する Active Directory ドメイン サービス の属性を構成できる、グラフィカル ユーザー インターフェイス アプリケーションです。

このツールを使用する主なシナリオは、次のとおりです。

  - 管理者は、Active Directory ドメイン サービスの属性を Lync Server 2013 の属性にマッピングできます。

  - 管理者は、Active Directory ドメイン サービスの属性をアドレス帳サービスのファイルに含めるか、ファイルから除外できます。

  - 管理者は、アドレス帳サービスの既定の設定を復元できます。

ABSConfig ツールは、absConfig.exe ファイルから起動します。ツールは、\[**Configure Attributes**\] タブに開きます。このテーブルでは、Active Directory ドメイン サービスの属性を Lync Server 2013 の属性フィールドにマッピングして、特定の属性フィルターに基づいてアドレス帳サービスのファイルに含める、またはファイルから除外するユーザーを指定できます。また、アドレス帳ファイルに含める電話番号の値をカスタマイズできます。\[**Restore Defaults**\] オプションを使用すると、アドレス帳サービスの設定を既定の値に復元できます。

## Lync Server 2010 からの変更点

Lync Server 2013 の ABS 構成ツールでは、属性の \[enable\] チェック ボックスをオフにして、属性 (行) を削除できます。これは、Lync Server 2010 で行を削除する操作と同じです。

> [!NOTE]
> [enable] チェック ボックスは、右端列にあります。列を表示するには、画面を右にスクロールする必要がある場合があります。


## 出力

ABSConfig は、データベースにアドレス帳サービスの構成を格納します。

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

## 用途

ABSConfig には、Lync Server 2013 のアドレス帳サービスをすばやく簡単にカスタマイズする機能が備わっています。

## 要件

## コンピューター

ABSConfig は、Lync Server 2013 がインストールされた、ドメインに参加しているコンピューターからのみ実行できます。Lync Server 2013 Enterprise Edition の場合、このツールはセットアップ中にアドレス帳サービスを有効にしたフロントエンド サーバーでのみ実行できます。

## ネットワーク

コンピューターは、フロントエンド プールとバックエンド データベースに接続できる必要があります。

## ソフトウェア

ABSConfig ツールを実行する前に、次のソフトウェア コンポーネントがインストールされている必要があります。

  - Microsoft Lync Server 2013

## ユーザー

Lync Server 2013 展開を更新する権限を持つ管理者。

## 例

ABSConfig は、コマンド プロンプトで **ABSConfig.exe** と入力して起動できます。ABSConfig ツールのユーザー インターフェイスを以下に示します。

![ABSConfig.exe ツール](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "ABSConfig.exe ツール")

## 要約

ABSConfig ツールには、管理者が Lync Server 2013 のアドレス帳サービスをすばやく簡単にカスタマイズできる機能が備わっています。

## Bandwidth Policy Service Monitor

Bandwidth Policy Service Monitor ツールを使用すると、管理者は次の情報を確認できます。

1.  トポロジ内の構成済みのすべての Lync Server 2013 帯域幅ポリシー サービス (認証とコア)

2.  各サービスの帯域幅ポリシー サービスとエッジ サーバーへの接続状況

3.  ネットワーク構成ドキュメントで構成されたすべてのリンクと、各帯域幅ポリシー サービスから報告されたリアルタイムの帯域幅の使用状況

## 説明

Bandwidth Policy Service Monitor ツールは、GUI ベースのアプリケーションとして実装されます。管理者は、PDPMonUI.exe を実行してツールを起動します。

ツールを起動すると、ツールはトポロジ内の帯域幅ポリシー サービスの一覧を検索します。初期アップデートが完了すると、ウィンドウの左ペインに、所属するクラスターによってグループ分けされたサービスの一覧が表示されます。

管理者が特定の帯域幅ポリシー サービスを選ぶと、右ペインにそのサービスの情報が表示されます。次の 2 つのメイン タブにそれぞれ情報が表示されます。

## \[Machine Info\] タブ

\[**Machine Info**\] タブには、選択した帯域幅ポリシー サービスの詳細と、選択した帯域幅ポリシー サービスから別のサービスへの接続の一覧と状態が表示されます。

## \[Topology Info\] タブ

\[**Topology Info**\] タブには、ネットワーク構成設定で構成されたすべてのリンクの一覧が表示されます。各リンクには、音声とビデオの帯域幅容量が表示されます。さらに、現在使用されている帯域幅が、Kbps と容量に対する割合で表示されます。ツールでは色分けが使用され、容量に近づいているリンクが強調表示されます。これにより、管理者は対象のリンクをすばやく分離できます。

> [!NOTE]
> Bandwidth Policy Service Monitor ツールを構成された任意の帯域幅ポリシー サービスに接続する際に問題が発生すると、[<strong>Machine Info</strong>] タブと [<strong>Topology Info</strong>] タブに情報が表示されません。ただし、最初は接続されたにもかかわらず、後にサービスへの接続が途切れることもあります。このような場合、管理者に古い情報が表示されることがあります。各タブには [<strong>Last Updated</strong>] タイムスタンプが用意されているため、管理者は特定の帯域幅ポリシー サービスのデータが最後に更新された時間を確認できます。


## 出力

コマンドラインの出力はありません。プログラムの出力は、メインのグラフィカル ユーザー インターフェイス (GUI) に含まれています。

## 用途

Bandwidth Policy Service Monitor ツールを使用すると、管理者はトポロジに定義された各帯域幅ポリシー サービスの詳細を確認できます。さらに、管理者はネットワーク構成ドキュメントに定義されたすべてのリンクの帯域幅の使用状況を、リアルタイムで確認できます。

## 要件

Bandwidth Policy Service Monitor ツールは、Lync Server トポロジを構成するコンピューター上で実行する必要があります。

## 要約

Bandwidth Policy Service Monitor ツールを使用すると、トポロジ内の帯域幅ポリシー サービスの状態を確認できます。さらに、ネットワーク構成設定で定義されたリンクの帯域幅のリアルタイムの使用状況を把握できるため、管理者にとって非常に重要なリソースです。

## Bandwidth Utilization Analyzer

Bandwidth Utilization Analyzer は、エンタープライズ ネットワークの WAN リンク全体の UC エンドポイントで消費される帯域幅を、さまざまな観点から確認できるレポートを作成するツールです。これらのレポートを使用すると、現在の帯域幅の消費パターンを把握して、帯域幅の容量計画に活用できます。

## 説明

Bandwidth Utilization Analyzer は、GUI ベースのアプリケーションとして実装されます。このツールは、ネットワーク全体音声に限定した使用状況に関するレポートを作成し、容量の計画に活用できます。また、さまざまなリンクに割り当てられた帯域幅容量を反復処理します。

## 出力

Bandwidth Utilization Analyzer には、システムで構成されたすべての WAN リンクにおける、音声の帯域幅容量と使用状況に関するグラフィカル プロットが用意されています。

## 用途

音声やビデオを配布する際に、エンタープライズ ネットワーク全体のメディア トラフィックによる帯域幅の使用状況の傾向を把握することは重要です。Bandwidth Utilization Analyzer ツールを使用すると、管理者はそれを把握できます。このツールでは、次の操作を実行できます。

  - ネットワーク全体の音声の使用状況に関するレポートを生成する

  - より効果的な容量計画の立案とさまざまなリンクに割り当てられた帯域幅容量の反復処理をサポートする

Bandwidth Utilization Analyzer では、帯域幅容量のグラフィカル プロットと使用状況レポートを作成できます。その範囲と実行可能な操作は次のとおりです。

  - エンタープライズ ネットワーク内のすべての WAN リンク

  - 事前に指定した WAN リンクでフィルター処理

  - リンク容量を超過した WAN リンクでフィルター処理

  - 帯域幅の使用率が予測を下回る WAN リンクでフィルター処理

  - 重大レベル (WAN リンクの帯域幅使用率が容量の 90% を超過している) に達している WAN リンクでフィルター処理

  - WAN リンクの種類 (ネットワーク サイト リンク、地域間リンク、サイト内リンク) でフィルター処理

  - ネットワーク地域でフィルター処理

## アプリケーション

Bandwidth Utilization Analyzer には、次の 2 つのアプリケーション (ツール) が用意されています。

  - **WanLinkLogCollector.exe**   このツールを使用して、ユーザーは必要な情報を入力できます。

  - **BandwidthUtilizationAnalyzer.xlsm**  Microsoft Excel スプレッドシート ソフトウェアのレポートが WanLinkLogCollector.exe によって自動的に起動します。このアプリケーションでは、レポートにフィルターを適用できます (この記事の後半で説明します)。

## Bandwidth Utilization Analyzer の使用フェーズ

Bandwidth Utilization Analyzer の使用は、次の 2 つのフェーズに分けられます。

  - ログの収集 (WanLinkLogCollector.exe を使用)

  - レポートのカスタマイズ (BandwidthUtilizationAnalyzer.xlsm を使用)


> [!IMPORTANT]
> BandwidthUtilizationAnalyzer.xlsm はエンド ユーザーが手動で起動できないようにすることを強くお勧めします。



## Bandwidth Utilization Analyzer の起動

コマンド プロンプトで WanLinkLogCollector.exe を実行するか、Windows エクスプローラーを使用して起動します。

**WanLinkLogCollector.exe の使用**

WanLinkLogCollector.exe を使用するには、次の 3 つの手順を実行します。

1.  **ログのタイムラインを指定する**   レポートを生成するタイムラインを指定します。

2.  **ファイルのディレクトリを指定する**   ファイルの位置情報を指定します。

3.  **ログを収集してレポート ビューアーを起動する**   コマンドを実行してレポートを生成します。

## 手順 1 - ログのタイムラインを指定する

タイムラインのログを記録するには、以下の図に示すように、次の項目を指定します。

1.  **Start date** レポートを生成するタイムラインの開始日 (例: 2010 年 8 月 1 日)。

2.  **End date** レポートを生成するタイムラインの終了日 (例: 2010 年 9 月 30 日)。
    
    ![Bandwidth Utilization Analyzer の開始日/終了日](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Bandwidth Utilization Analyzer の開始日/終了日")  

## 手順 2 - ファイルのディレクトリを指定する

以下の図に示すように、ユーザーは次のディレクトリを指定します。

  - **Server log files location** 帯域幅ポリシー サーバーのログが格納されるフォルダーの場所。通常は、\<fileserver\>\\\<choice of FE\>\\AppServerFiles\\PDP です。

  - **Temporary file storage location** レポート生成中に中間ファイルを格納する一時ファイルの保管場所。

![Bandwidth Utilization Analyzer のファイル ディレクトリ](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "Bandwidth Utilization Analyzer のファイル ディレクトリ")

> [!NOTE]
> サーバー ログや一時ファイルを格納するフォルダーにアクセスできる十分な権限が、ツールのユーザーに割り当てられるようにしてください。


## 手順 3 - ログを収集してレポート ビューアーを起動する

ログを収集してレポート ビューアーを起動するには、以下の図に示す \[**Execute**\] をクリックします。この手順により、必要なデータが収集されます。

![Bandwidth Utilization Analyzer でのデータの収集](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Bandwidth Utilization Analyzer でのデータの収集")

入力の検証が正常に行われると、以下のメッセージが表示されます。

![BandwidthUtilizationAnalyzer でログに収集された通知](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "BandwidthUtilizationAnalyzer でログに収集された通知")

\[**OK**\] をクリックします。BandwidthUtilizationAnalyzer.xlsm は自動的に起動します。メッセージ ボックスの手順に従います。詳しくは、次のセクション「**BandwidthUtilizationAnalyzer.xlsm の使用**」をご覧ください。


**BandwidthUtilizationAnalyzer.xlsm の使用**

1.  BandwidthUtilizationAnalyzer.xlsm が自動的に起動したら、以下の図に示す \[**Refresh**\] をクリックします。
    
    ![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")

2.  ファイルのフォルダーが開かれたら、メッセージ ボックスで指定された場所にある consolidated.csv を選びます。以下の図に示すように、場所は **C:\\Temp** です。
    
    ![BandwidthUtilizationAnalyzer でフォルダーを開く](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "BandwidthUtilizationAnalyzer でフォルダーを開く")

3.  \[**Import**\] をクリックします。

4.  グラフィカル プロットが自動的に生成されます。バックグラウンドで作業中のポインターが表示されなくなると、使用できます。
    
    ![レポート ビューでのフィルターの適用](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "レポート ビューでのフィルターの適用")

## レポート ビューにフィルターを適用する

レポート ビューに適用できるフィルター (以下の図を参照) を紹介します。

![レポート ビューでのフィルターの適用](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "レポート ビューでのフィルターの適用")

1.  **Name** WAN リンクでフィルター処理 (グラフの右側のフィルター)。プレフィックス (縦長の青いボックスを参照) は、次のようなリンクの種類を示します。
    
      - **S: Site** ネットワーク サイトからネットワーク地域への WAN リンク
    
      - **IS: Inter-Site** 2 つのネットワーク サイト間の WAN リンク
    
      - **R: Inter-Region** 2 つのネットワーク地域間の WAN リンク

2.  **Exceeded limit** 帯域幅の使用率が帯域幅容量を超過している WAN リンクでフィルター処理

3.  **Critical levels** 帯域幅の使用率が帯域幅容量の 90% 以上に達した WAN リンクでフィルター処理

4.  **Under-utilized** 帯域幅の使用率が帯域幅容量の 25% に達していない WAN リンクでフィルター処理

5.  **Link type** 次に示す WAN リンクの種類でフィルター処理します。
    
      - **Network site**
    
      - **Inter-site**
    
      - **Inter-Region** リンクの種類

6.  **Region** ネットワーク地域でフィルター処理

次の図は、これまでに紹介したフィルターを示します。

\[**Name**\] でフィルター処理します。グラフに表示するリンクのリストを選びます。

![BandwidthUtilizationAnalyzer での \[Name\] でのフィルター処理](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "BandwidthUtilizationAnalyzer での [Name] でのフィルター処理")

\[**Exceeded limit**\] でフィルター処理します。フィルターを適用するには、\[**TRUE**\] を選びます。

![\[Exceeded Limit\] でのフィルター処理](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "[Exceeded Limit] でのフィルター処理")

\[**Critical levels**\] でフィルター処理します。フィルターを適用するには、\[**TRUE**\] を選びます。

![\[Critical Levels\] でのフィルター処理](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "[Critical Levels] でのフィルター処理")

\[**Under-utilized**\] でフィルター処理します。フィルターを適用するには、\[**TRUE**\] を選びます。

![\[Under Utilized\] でのフィルター処理](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "[Under Utilized] でのフィルター処理")

\[**Link Type**\] でフィルター処理します。表示する種類を 1 つ以上選びます。

![\[Link Type\] でのフィルター処理](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "[Link Type] でのフィルター処理")

\[**Region**\] でフィルター処理します。リンクを表示する地域のリストを選びます。

![\[Region\] でのフィルター処理](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "[Region] でのフィルター処理")

## 要件

  - .NET Framework 3.5

  - Microsoft Excel 2010 または Excel 2007

## 要約

Bandwidth Utilization Analyzer は、ネットワーク全体の UC トラフィックにおける音声の帯域幅の使用状況をプロットするために使用します。このツールは、ビデオの帯域幅の使用状況を報告する場合にも同様に使用できます。

## Call Parkometer

Call Parkometer は、コール パーク オービット デバイスに簡単にアクセスできるコマンドライン アプリケーションです。

## 説明

Call Parkometer は、現在保留されている通話を追跡するツールです。オービットやコール パーク サーバー (CPS) の使用状況に関する統計情報も収集します。このコマンドライン ツールは、ローカルまたはリモート接続のコンピューターから CPS オービット SQL Server データベースへの読み取りアクセスと書き込みアクセスを提供します。

すべてのオプションは同時に使用できません。コマンドライン構文は次のとおりです。

  - **-o** パラメーター - このプールで構成されたすべてのオービット範囲を一覧表示します。

  - **–n** パラメーター - このプールで現在使用されているすべてのオービットを一覧表示します。情報は次のように表示されます。
    
      - 保留元と保留先の SIP Uniform Resource Identifier (URI)。
    
      - 通話の保留先の CPS のホスト名。
    
      - 通話が保留された時点のタイムスタンプ。

  - **–f** パラメーター - プールで現在使用されていないオービットの数を一覧表示します。

  - **–r \<n\>** パラメーター - 最後に保留された \<n\> 個の通話を表示します。情報は次のように表示されます。
    
      - 保留先の SIP URI.
    
      - 保留元の SIP URI.
    
      - 通話の保留先の CPS のホスト名。
    
      - 通話が取得または破棄された時点のタイムスタンプ。

  - **-t\<n\>** パラメーター - データベースへのオービットの予約をテストして、ランダムに割り当てられたオービット番号を表示します。

## 出力

コマンド プロンプトで指定された入力パラメーターによっては、Call Parkometer に次の出力が表示されます。

  - このプールで構成されたすべてのオービット範囲

  - 現在保留されている通話

  - 有効な (使用されていない) オービットの数

  - 最近保留された通話

  - 一定およびランダムなオービットの値をテストするために予約されたオービット

## 用途

CPS ツールを使用すると、CPS データベースへのコマンドライン アクセスを確立できます。管理者は、CPS の使用状況を確認して、プールに割り当てられているオービットの数を把握できます。

## 要件

CPS が実行されている同じコンピューターで実行する場合、このツールの使用に必要な条件はありません。このツールをリモート コンピューターで実行する場合、Lync Server 2013 で使用される SQL Server データベースのリモート アクセスを有効にする必要があります。Call Parkometer をプールの SQL Server に接続するには、SQL Server データベース接続文字列を使用して構成する必要があります。この SQL Server データベース接続文字列は、構成ファイル **parkometer.exe.config** で定義されます。この構成ファイルは、parkometer.exe と同じディレクトリに配置する必要があります。次の XML ファイルは、parkometer.exe.config の例を示します。構成する必要があるパラメーターは、ユーザー名 (例: mydomain\\Administrator)、パスワード (例: mypassword)、ホスト名 (例: myserver) です。

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

## 例

展開されたオービット範囲: –o パラメーターによって、このプールで構成されたすべてのオービット範囲が次のように一覧表示されます。

![Call Parkometer のオービット範囲](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Call Parkometer のオービット範囲")

現在保留されている通話: –n パラメーターによって、このプールで現在使用されているすべてのオービットが次のように一覧表示されます。

![Call Parkometer で現在保留されている通話](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Call Parkometer で現在保留されている通話")

使用されていないオービットの数: –f パラメーターによって、プールで現在使用されていないオービットの数が次のように一覧表示されます。

![Call Parkometer の使用されていないオービット](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Call Parkometer の使用されていないオービット")

最近保留された通話: –r \<n\> パラメーターによって、最後に保留された \<n\> 件の通話が次のように一覧表示されます。

![Call Parkometer で最近保留された通話](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Call Parkometer で最近保留された通話")

オービット予約のテスト: –t \<n\> パラメーターによって、データベース内のオービットを予約するテストが次のように行われます。

![Call Parkometer のオービット予約のテスト](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Call Parkometer のオービット予約のテスト")

## 要約

Call Parkometer は、コール パーク サーバーに関する詳しい情報を提供するコマンドライン ツールです。

## CleanupStorageServiceData

CleanupStorageServiceData リソース キットを使用すると、Lync Server Storage Service (LYSS) によって使用された、孤立したデータをデータベースから削除できます。このストレージ サービスには、Lync Server と、SQL Server や Exchange などのさまざまなバックエンド データ ストレージ エンドポイントの間の通信を調整する機能があります。

## 説明

高可用性を確保するために、LYSS は一時的にプール内の複数のフロントエンド サーバーからデータを受け入れてそのコピーを保存し、長期的に格納される最終的な保存場所に届けられた時点でそのデータを削除します。通常の動作中の例外により、サーバーや処理に問題が発生し、一部のデータが適切にクリーンアップされないことがあります。このようなデータに害はありませんが、限りある処理リソースを消費します。通常必要とされるデータ保守のほとんどは自動化されていますが、このツールを使用すると、自動的には削除できないこのような孤立したデータを安全に検出して削除できます。このツールを使用するタイミングは、状態を監視する System Center Operations Manager (SCOM) から、ローカル LYSS データベースのプール内の不要なデータを削除するように管理者に要請する警告が出されることによって示されます。警告の原因に対応するイベントは、フロントエンドのイベント ログに出されます。イベントの詳細にはフロントエンドに含まれる孤立したデータ量の情報が含まれ、事前に設定したしきい値を孤立したデータ量が超過すると警告が出されます。

## 要件

Lync Server 2013、リソース キット ツール をインストールします。ツールは、Lync Server と Lync Server 2013 管理シェル がインストールされた、ドメインに参加しているコンピューターで動作します。ツールは管理シェルのコマンドレットを使用して、プール内のすべてのフロントエンド サーバーを識別します。次に、ツールは **RtcLocal** データベースがインストールされた、プール内のマシンから実行する必要があります。このデータベースは、Lync Server ルーティング サービスとの通信に必要な接続の詳細を取得するために、CleanupStorageServiceData ツールで使用されます。最後に、ツールを呼び出すアカウントや資格情報には、出力ログの書き込みのために、ファイル共有への読み取り/書き込みアクセスが設定されている必要があります。また、このツールは安定した状態にあるプールに依存します。つまり、すべてのフロントエンド サーバーが稼動していること、SQL Server LYNCLOCAL インスタンスと LYSS データベースに接続されていること、各ルーティング グループに 1 つのプライマリ フロントエンド サーバーと 2 つのセカンダリ フロントエンド サーバーの完全なセットが含まれていることが必要です。

## 例

C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\\StorageService\> ImportStorageServiceData.exe

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

## DBAnalyze

## 説明

DBAnalyze は、管理者が Lync Server 2013 データベースに関する分析レポートを収集するのに役立つ、コマンドライン ツールです。DBAnalyze には、診断モード、ユーザー データ モード、会議モード、MCU モード、ディスク断片化モードが用意されています。

  - **診断モード**   テーブル (レコード数、断片化、データ サイズ、インデックス サイズ)、データとログ ファイルのサイズ、最後にバックアップした時間、Microsoft Office Communications Server を実行しているサーバー間の連絡先の分散、ユーザーごとのアクセス権限、連絡先、コンテナー、サブスクリプション、発行、エンドポイントの平均数、所属が不適切なユーザー、ルーティングできないユーザー、ユーザーごとの開催した会議、スケジュールが設定された会議、アクティブな会議の平均数、データベースのバージョンなどの情報が含まれるレポートを作成します。
    
    > [!NOTE]
    > 診断モードを実行すると、サーバーのパフォーマンスに影響を与えることがあります。


  - **ユーザー データ モード**  指定のユーザーまたはそのユーザーが連絡先一覧やアクセス権限一覧に含まれているユーザーの連絡先、コンテナー、サブスクリプション、発行、アクセス権限、連絡先グループのデータのレポートを作成します。また、このモードではユーザーが開催または招待された会議の集計データのレポートを作成します。

  - **会議モード**   特定の会議について、会議全体のスケジュール時間の詳細、招待者のリスト、会議で使用できるメディア種類のリスト、アクティブな MCU (Multipoint Control Unit)、アクティブな参加者リスト、各参加者の信号の状態などの詳細データのレポートを作成します。

  - **会議 ID のデコード**  **/pstnid** スイッチで指定された公衆交換電話網 (PSTN) の会議 ID をデコードします。バックエンドには接続されず、詳しい情報は表示されません。

  - **会議の解決**   **/pstnid** スイッチで指定された PSTN の会議 ID をデコードし、ID で指定された会議に関する情報を表示します。

  - **MCU モード**  プール内の各 MCU の ID、メディア種類、URL、ハートビートの状態、会議の負荷、参加者の負荷などのレポートを作成します。

  - **ディスク断片化モード**  すべてのディスクの断片化状態を表示します。

このツールは、さまざまな問題を診断し、管理者の容量計画を支援するために使用できます。たとえば、サーバー A に所属する大多数のユーザーが、サーバー B に所属するユーザーを連絡先として選択した場合、管理者はサーバー A のユーザーをサーバー B に移動して、サーバー間のトラフィックを削減できます。

## 出力

このツールは、Lync Server 2013 データベースに関する、定義済みレポートを出力します。**パス:** %ProgramFiles%\\Microsoft Lync Server 2013\\Reskit

## 用途

ツールをインストールするには、Dbanalyze.exe をローカル フォルダーに移動して、ツールを実行します。ツールを使用するには、コマンドラインから次のコマンドを実行します。`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` コマンドラインのオプションの説明は、以下のとおりです。

![Dbanalyze.exe のコマンド ライン オプション](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Dbanalyze.exe のコマンド ライン オプション")

## 要件

**コンピューター** DBAnalyze は、Lync Server 2013 がインストールされた、ドメインに参加しているコンピューターからのみ実行できます。

**ネットワーク** コンピューターは、バックエンド データベースに接続できる必要があります。

**ソフトウェア** DBAnalyze を実行する前に、Lync Server 2013 のソフトウェア コンポーネントがインストールされている必要があります。

**ユーザー** 次の表は、Lync Server 2013 データベースにアクセスするために必要な権限を持っている管理者を示します。

![Dbanalyze.exe の権限のテーブル](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Dbanalyze.exe の権限のテーブル")

> [!NOTE]
> <strong>/report:disk</strong> モードでは、ローカル管理者のアカウントが必要です。


## 例

次に、有効な Dbanalyze.exe コマンドの例を示します。

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

## 要約

DBAnalyzer を使用すると、管理者は Lync Server 2013 データベースをすばやく簡単に分析できます。

## ImportStorageServiceData

ImportStorageServiceData リソース キット ツールを使用すると、Storage Service (LYSS) からフラッシュされたキューやエンドポイントのデータを、Storage Service に再インポートできます。

## 説明

Storage Service からのデータのフラッシュは、キュー アイテムの状態やデータベースのサイズに基づいて自動的 (定期的) に行われた可能性があります。また、プール フェールオーバー コマンドレット、またはそれによって呼び出される StorageServiceFullFlush コマンドレットの手動呼び出しによって行われた可能性もあります。フロントエンドの Storage Service (LYSS) のデータベース サイズのいずれかが通常のレベルを上回っている場合は、データを再びインポートしてもより多くのデータがエクスポートされて戻る可能性があるため、行わないことをお勧めします。さらに、Storage Service のキューが肥大化する原因と考えられる問題 (Exchange のエンドポイントのエラー、ネットワークの問題など) は、あらかじめ解決することをお勧めします。

**シナリオ 1:** プールのフェールオーバー中に、各フロントエンドのストレージ サービスからファイルがフラッシュされる場合があります。フェールオーバーが完了したら、ツールを実行してデータを再インポートする必要があります。

**シナリオ 2:** Storage Service データベースで一定のしきい値 (全体の 60%、80%、90% など) を超えると、毎日自動的にデータがフラッシュされます。このように定期的に自動でフラッシュされたデータは、管理者が手動で再インポートする必要があります。前述の状況では、SCOM の監視パックが展開されていない場合、Lync Server Storage Service のイベントにより、Storage Service からデータがフラッシュされたことを知らせます。イベント ID は、32075 (フル フラッシュ操作の開始)、32076 (フル フラッシュの完了)、32082 (メンテナンス レベル フラッシュの開始)、32083 (メンテナンス レベル フラッシュの完了)、32089 (データベースがいっぱいになったことによるフラッシュの発生) です。これらのイベント ID は、RTM リリースに対応します。これらのイベントが出力されることによって、管理者はファイルがフラッシュされたことを認識します。このようなデータは、このツールを使用して定期的 (週に 1 回など) に再インポートする必要があります。

Online Service リリースの場合、Lync Server 用の SCOM 状態監視パックが展開されると、フラッシュされたデータを Storage Service に再インポートすることを管理者に要求する新しい警告が出されることがあります。警告の原因に対応するイベントは、フロントエンド サーバーのイベント ログに出されます。イベントの出力には、フラッシュされたデータ ファイルが置かれている親パスや、警告の条件に一致するファイルの個数などが記述されています。警告の条件は、指定の親パスに Y 日以上前のファイルが X 個以上あることです (X と Y は StorageService 内に事前設定されていますが、APPCONFIG ファイルを変更して上書きできます)。状態の警告が出されるイベントで、親パスが異なる場合の例を以下に 2 つ示します。1 つは Web サービスのファイル共有で、もう 1 つは各フロントエンドのローカルの Application Data ディレクトリ (例: c:\\ProgramData\\Microsoft\\Lync Server\\StorageService) です。その後、管理者はこの reskit ツールを実行します。

このツールが実行されると、フロントエンドの CPU と IO の負荷が増大します。データが別のフロントエンドにある場合は、ツールが実行されるフロントエンド以外の負荷も増大します。このツールは、フロントエンドの CPU と IO の負荷が高いピーク時間を外して実行することをお勧めします。また、このツールで 1 つのデータ ファイルをインポートするのに 2、3 分かかる場合があります。ツールが実行される時間を予測する際には、この点にご注意ください。このツールによって生成される詳しいログ ファイルは、既定でファイル ストアに表示されます。ログ ファイルは数十 MB に達することがあるため、エラーが報告されなかった場合は削除してください。

![記憶域サーバーのイベント ログのサンプル イベント](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "記憶域サーバーのイベント ログのサンプル イベント")

## 要件

Lync Server 2013、リソース キット ツール をインストールします。ツールは、Lync Server と Lync Server 管理シェル がインストールされた、ドメインに参加しているコンピューターで動作します。ツールは管理シェルのコマンドレットを使用して、プール内のすべてのフロントエンド サーバーを識別します。次に、ツールは **RtcLocal** データベースがインストールされた、プール内のマシンから実行する必要があります。このデータベースは、プールの Web サービス ファイル共有の場所を取得するために、このツールで使用されます。さらに、このツールを使用する前に、各フロントエンド サーバーで、このツールが実行されるコンピューターを有効にするほか、**Enable-PSRemoting** を各フロントエンド サーバーで使用して Windows PowerShell Remoting を有効にする必要があります。有効にしないと、このツールから実行されるリモートの Windows PowerShell コマンドが失敗します。コマンドを実行したら、プール内のすべてのフロントエンド サーバーで Windows PowerShell Remoting をオフにできます。最後に、このツールを呼び出すアカウントや資格情報には、出力ログの書き込みのために、Web サービス ファイル共有への読み取り/書き込みアクセスが設定されている必要があります。設定されていないと、IO アクセスに関するエラーでツールが失敗します。

> [!NOTE]
> Windows PowerShell Remoting は、Windows Server 2012 では既定で有効ですが、Windows Server 2008 オペレーティング システム では有効ではありません。


## 例

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

## LCSSync

LCSSync ツールは、Lync Server 2013 の通信ソフトウェアを複数フォレスト環境に展開するのに役立ちます。このツールを使用すると、異なるユーザー フォレストのユーザーやグループを、Active Directory ドメイン サービスの連絡先オブジェクトとして、Lync Server 2013 がインストールされた中央フォレストに同期できます。

## 説明

LCSSync は中央フォレストにある同期された Active Directory ドメイン サービスの連絡先オブジェクトを使用して、Lync Server 用にユーザーを有効にします。シングル サインインを有効にするには、Lync Server 2013 用にプライマリ ユーザー アカウントを中央フォレストの Active Directory ドメイン サービスの連絡先オブジェクトにマッピングする必要があります。このツールは、そのマッピングを支援します。このツールには、Microsoft Identity Integration Server で Management Agents を作成するためのテンプレートが用意されています。

## 要約

LCSSync ツールは、Lync Server を複数フォレスト環境に展開するのに役立ちます。

## LookupUserConsole

LookupUserConsole ツールは、特定のユーザーに関する Lync Server の内部ルーティング情報を表示します。この情報は、Microsoft のサポート担当者が展開やルーティングの問題を解決するのに役立つ場合があります。

## 説明

LookupUserConsole.exe を実行するとコマンド プロンプトが開き、SIP アドレスに関する Lync Server の内部ルーティング情報を表示します。LookupUserConsole ツールを終了するには、**exit** と入力します。

## 要件

Lync Server 2013、リソース キット ツール をインストールします。ツールは、Lync Server がインストールされた、ドメインに参加しているコンピューターで動作します。

## 例

C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\>LookupUserConsole.exe

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

## MsTurnPing

MSTurnPing ツールを使用すると、Microsoft Lync Server 2013 の通信ソフトウェアの管理者が音声ビデオ エッジ サービスおよび音声ビデオ認証サービスを実行しているサーバーや、トポロジで帯域幅ポリシー サービスを実行しているサーバーの状態を確認できます。

## 説明

MSTurnPing ツールを使用すると、Lync Server 2013 の通信ソフトウェアの管理者が音声ビデオ エッジ サービスおよび音声ビデオ認証サービスを実行しているサーバーや、トポロジで帯域幅ポリシー サービスを実行しているサーバーの状態を確認できます。

このツールを使用すると、管理者は次のテストを実行できます。

1.  音声ビデオ エッジ サーバー テスト: トポロジ内の音声ビデオ エッジ サーバーに対して次のテストを実行します。
    
      - Lync Server の音声ビデオ認証サービスが開始されており、適切な資格情報が発行されることを確認する。
    
      - Lync Server の音声ビデオ エッジ サービスが開始されており、外部エッジにリソースが正しく割り当てられることを確認する。

2.  帯域幅ポリシー サービス テスト: トポロジ内の帯域幅ポリシー サービスを実行しているすべてのサーバーに対して次のテストを実行します。
    
      - Lync Server の帯域幅ポリシー サービス (認証) が開始されており、適切な資格情報が発行されることを確認する。
    
      - Lync Server の帯域幅ポリシー サービス (コア) が開始されており、帯域幅の確認が正しく行われることを確認する。

このツールは、トポロジの一部でありローカル ストアがインストールされているコンピューターから実行する必要があります。

## 出力

このツールでは、各操作の結果が出力されます。

  - **AudioVideoEdgeServer** テストを実行した場合、ツールの出力は次のようになります。
    
      - トポロジ内で Lync Server 音声ビデオ認証サービスを提供するコンピューターのテスト結果。
    
      - トポロジ内で Lync Server 音声ビデオ エッジ サービスを提供するコンピューターのテスト結果。

  - **BandwidthPolicyServer** テストを実行した場合、ツールの出力は次のようになります。
    
      - トポロジ内で Lync Server 帯域幅ポリシー サービス (認証) を提供するコンピューターのテスト結果。
    
      - トポロジ内で Lync Server 帯域幅ポリシー サービス (コア) を提供するコンピューターのテスト結果。

## 要件

  - このツールは、トポロジ内のローカル ストアを持つコンピューターから実行する必要があります。

  - このツールは、ローカル ストアへのアクセス権のある管理者として実行する必要があります。

## 例

ツールの入力例は、次のとおりです。

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

## 要約

このツールは、音声ビデオ サービスや帯域幅ポリシー サービスを実行するサーバーのステータスを確認する必要がある Lync Server 2013 管理者にとって役立つリソースになります。

## Network Configuration Viewer

Network Configuration Viewer では、Microsoft Lync Server 2013 通信ソフトウェア管理者が、指定された帯域幅容量に基づく音声通話やビデオ通話などのリアルタイム通信セッションを許可するようにプロビジョニングされた、企業の通話受付管理サービス (CAC) ネットワーク トポロジを確認できます。Lync Server 2013 管理者が定義した CAC ポリシーは、Lync Server 2013 でインストールされた帯域幅ポリシー サービスによって適用されます。

## 説明

Network Configuration Viewer (NetworkConfigurationViewer.exe) を使用すると、管理者は次のタスクを実行できます。

  - Lync Server 2013 展開の CAC ネットワーク トポロジを読み込み、図の形式で表示する。

  - 帯域幅ポリシー サーバー ログ ファイルの CAC ネットワーク トポロジを読み込み、図の形式で表示する。

  - CAC ネットワーク トポロジを XML 形式でディスクに保存、格納する。

  - CAC ネットワーク トポロジ図を JPG または BMP 形式で保存、格納する。

  - CAC ネットワーク トポロジ構成データを表示する。

  - CAC ネットワーク トポロジをツリー形式で表示する。

  - CAC ネットワーク トポロジ リンク (サイトから地域、地域から地域、サイトからサイトの各リンクなど) のカスタム コネクタを定義する。

  - CAC ネットワーク トポロジのサイト情報、地域情報、プロビジョニングされた帯域幅ポリシーとネットワーク リンクを表示する。

## 用途

企業の CAC ネットワーク トポロジ リンクをグラフィカル インターフェイスで表示します。

## 例

**Lync Server 2013 展開の CAC ネットワーク トポロジを読み込み、図の形式で表示する:** 下の図に示すように、Lync Server 2013 管理者は \[**Download Network Configuration**\] オプションを使用して、任意の Lync Server 2013 コンピューターの CAC ネットワーク トポロジ構成を読み込んで表示できます。Lync 構成ストアと接続されていないコンピューターに展開されている場合は、構成のダウンロードまたは表示が失敗します。

![ネットワーク構成のダウンロード](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "ネットワーク構成のダウンロード")

**帯域幅ポリシー サーバー ログ ファイルの CAC ネットワーク トポロジを読み込み、図の形式で表示する:** Lync Server 2013 帯域幅ポリシー サーバーでは、CAC ネットワーク トポロジがログ メカニズムの一部として Lync Server 2013 ファイル共有の場所に保存されます。下に示すように、Lync Server 管理者は \[**Open Network Configuration**\] オプションを使用して、それらのファイルを図の形式で表示できます。

![帯域幅ポリシー サーバーのログ ファイルを開く](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "帯域幅ポリシー サーバーのログ ファイルを開く")

CAC ネットワーク トポロジを XML 形式でディスクに保存、格納する: 下に示すように、Lync Server 2013 管理者は \[**Save a copy of Network Configuration**\] オプションを使用して、CAC ネットワーク トポロジ構成ファイルを XML 形式で保存できます。保存した構成ファイルはオフラインでのグラフィカルな表示に使用できます。

![ネットワーク構成の XML ファイルとしての保存](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "ネットワーク構成の XML ファイルとしての保存")

CAC ネットワーク トポロジ図を JPG または BMP 形式で保存、格納する: 下に示すように、Lync Server 2013 管理者は \[**Save Network Configuration diagram as picture**\] オプションを使用して、CAC ネットワーク トポロジ構成をグラフィカル形式 (JPG および BMP ファイル形式) で保存できます。

![ネットワーク構成の画像としての保存](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "ネットワーク構成の画像としての保存")

**CAC ネットワーク トポロジ構成データを表示する:** 下に示すように、Lync Server 2013 管理者は \[View Network Configuration data\] オプションを使用して、ネットワーク地域、ネットワーク サイト、帯域幅プロファイル、サイトのサブネット IP アドレスなど、関連するネットワーク構成データをテキスト形式で表示できます。

![ネットワーク構成データの表示](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "ネットワーク構成データの表示")

**CAC ネットワーク トポロジをツリー形式で表示する:** 下に示すように、Lync Server 2013 管理者はツール ウィンドウの左側にあるコントロール パネルを使用して、関連するネットワーク構成データをグラフィカルなツリー形式で表示できます。

![ネットワーク構成データのツリー ビューでの表示](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "ネットワーク構成データのツリー ビューでの表示")

**CAC ネットワーク トポロジ リンク (サイトから地域、地域から地域、サイトからサイトの各リンクなど) のカスタム コネクタを定義する:** 下に示すように、Lync Server 2013 管理者は \[Settings\] オプションを使用して、CAC ネットワーク構成の WAN リンクのカスタム グラフィカル コネクタを定義できます。これは、ネットワーク構成にプロビジョニングされている各種ネットワーク リンクを区別するのに役立ちます。

![CAC ネットワーク トポロジのカスタム コネクタの定義](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "CAC ネットワーク トポロジのカスタム コネクタの定義")

**CAC ネットワーク トポロジのサイト情報、地域情報、プロビジョニングされた帯域幅ポリシーを表示する:** Lync Server 2013 管理者は下に示すオプションを使用すると、関連する CAC ネットワーク地域情報、サイト情報、CAC 帯域幅プロビジョニング情報を表示できます (たとえば、ネットワーク地域またはネットワーク サイト オブジェクトの \[**Info**\] をクリックします)。

![ネットワークのカスタム コネクタの定義](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "ネットワークのカスタム コネクタの定義")

## 要約

このツールは、展開の CAC ネットワーク トポロジを図の形式で表示することを望む Lync Server 2013 管理者にとって役立つリソースになります。

## Response Group Agent Live

応答グループ アプリケーションによって、エージェントは組み込みの Web サービスを使用してリアルタイムの有効な情報にアクセスできるようになります。ただし、このデータのグラフィカル表示はアプリケーションの外部では使用できません。Response Group Agent Live リソース キット ツールは、他のエージェントのプレゼンスなど、Microsoft Lync 2013 通信ソフトウェアのリアルタイム情報で強化された、これらの情報にアクセスするための簡単かつグラフィカルな方法を提供してこの問題を解決します。

## 説明

Response Group Agent Live は、サインインやサインアウト機能、リアルタイム情報 (グループのメンバーシップや現在の通話数など) を応答グループ エージェントに提供する Windows アプリケーションです。これは、(Lync 2013 からアクセス可能な) \[Agent Groups\] ページの拡張版として用意されています。

## 用途

着信通話は応答グループ アプリケーションによってキューに配置されてから、エージェント グループにルーティングされます。どの通話を処理するかについて十分な情報に基づいて判断するために、エージェントは他のエージェントの状態や各キューで待機中の通話数など、エージェント グループに関するリアルタイム情報にアクセスできます。このような情報は、当初は応答グループ サービスからのみアクセスが可能でしたが、Response Group Agent Live によって直感的な方法で利用できるようになりました。

## 機能

Response Group Agent Live ツールは応答グループ サービスと Microsoft Lync 2013 SDK に基づいて構築されています。このツールは応答グループ サービスから利用できる情報や機能 (グループのメンバーシップ、他のエージェントのプレゼンス、待機中の通話数など) を応答グループ エージェントに提供します。

下の図は、Response Group Agent Live のメイン インターフェイスを示しています。

![Response Group Agent Live ツール](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "Response Group Agent Live ツール")

Response Group Agent Live では、エージェントは次の主な 3 つの機能を使用できます。

  - **サインイン/サインアウト:** (Lync 2013 からアクセス可能な) \[Agent Groups\] ページとは異なり、Response Group Agent Live ではすべてのエージェント グループから一度にサインインまたはサインアウトする機能がエージェントにのみ許可されます。エージェントは次の 3 つの方法ですばやくサインインまたはサインアウトできます。
    
      - アプリケーション内でサインイン/サインアウト (緑色と赤色) ボタンをクリックします。
    
      - システム トレイ アイコンを右クリックし、サインインまたはサインアウトを選択します。
    
      - 構成可能なキーボード ショートカットを使用します。

  - **グループのメンバーシップ:** エージェント グループを選択すると、Response Group Agent Live ではこのグループ内のエージェントのリストが右側のウィンドウに表示されます。Lync 2013 がこのアプリケーションと同じコンピューター上で実行中の場合、プレゼンス情報と連絡先カードが Response Group Agent Live に表示されます。エージェントはそこから直接他のエージェントに IM を送信したり電話をかけたりできます。

  - **リアルタイム統計情報:** Response Group Agent Live ではすべてのエージェント グループのリアルタイム統計情報を使用できます。更新間隔は 1 分です。応答グループが通話に応答すると、グループ名の横に視覚的なインジケーターが追加され、キュー内の現在の通話数が表示されます。グループにマウスを合わせると、最長の待機時間も表示されます。

## 要件

Response Group Agent Live には .NET Framework 4.0 が必要です。また、プレゼンスや連絡先カードの機能を利用するには、Lync 2013 がローカルにインストールされ、実行中である必要があります。

## 構成

アプリケーションの \[Options\] ダイアログ ボックスを使用すると、Response Group Agent Live を個人の好みに合わせてカスタマイズできます。また、管理者は RGAgentLive.exe.構成ファイルの defaultHostAddress プロパティを直接編集して既定のホスト アドレスを定義できます。

下の図は、エージェントがホスト アドレスやショートカット キーを構成できる \[Options\] ダイアログ ボックスを示しています。このダイアログを表示するには、メイン インターフェイスの右上にある \[Options\] ボタンをクリックします。

![\[Response Group Agent Live Options\] ダイアログ ボックス](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "[Response Group Agent Live Options] ダイアログ ボックス")

Response Group Agent Live の構成では次の 3 つの設定をカスタマイズできます。

  - \[Host address\]: これは通常、エージェントのホーム プールに属する Web プール FQDN です。この情報から、正確な応答グループ サービス アドレスがバックグラウンドで自動的に取得されます (ホストの後に適切なパスが付加されます)。

  - \[Shortcuts\]: サインイン/サインアウト用の厳密なショートカットをカスタマイズできます。唯一の制約として、ショートカットでは 1 つ以上のキーのほかに "Windows ロゴ" キーを使用する必要があります。

  - \[Start with Windows\]: Windows と共に自動的に起動するようにアプリケーションを構成できます。

## 例

下の図は、右側のウィンドウで連絡先を右クリックして、他のエージェントに電話をかけたり IM を送信する方法を示しています。

![通話の発信または IM の送信](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "通話の発信または IM の送信")

下の図は、Response Group Agent Live に表示されるキュー内の現在の通話数と全着信通話内での最長待機時間を示しています。

![キュー情報の表示](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "キュー情報の表示")

## 要約

迅速なサインインとサインアウト、グループのメンバーシップ、基本的なリアルタイム統計情報は、アプリケーション外部でのみ利用できる、応答グループ サービスに基づいた便利な応答グループ エージェント機能です。Response Group Agent Live リソース キット ツールを使用すれば、Lync 管理者はグラフィカルな方法でより迅速にタスクを実行できる Windows アプリケーションをエージェントに提供できます。

## SEFAUtil

SEFAUtil (secondary extension feature activation) は、Microsoft Lync Server 2013 通信ソフトウェア管理者やヘルプデスク エージェントが、代理人着信、着信転送、同時呼び出し、チーム呼び出し設定、グループ通話ピックアップを Lync Server 2013 ユーザーの代わりに構成できるコマンドライン ツールです。また、管理者は特定のユーザー向けに公開されているコール ルーティング設定のクエリを実行できます。SEFAUtil ツールを使用すると、管理者は着信転送または同時呼び出しをユーザーの代わりに有効化、無効化、変更できます。管理者はターゲットを (SIP URI の形式で) 指定したり、ユーザーによって既に公開されているターゲットを使用できます。管理者はまた、代理人やチーム呼び出しグループのメンバーをユーザーの代わりに追加または削除できます。このツールは Microsoft Unified Communications Managed API (UCMA) 3.0 に基づいており、管理者は信頼されたアプリケーションを SEFAUtil 用の中央管理ストアに作成する必要があります。

SEFAUtil (secondary extension feature activation) を使用すると、Lync Server 2013 管理者やヘルプデスク エージェントは代理人着信、着信転送、同時呼び出し、チーム呼び出し設定、グループ通話ピックアップを Lync Server 2013 ユーザーの代わりに構成できます。また、管理者は特定のユーザー向けに公開されているコール ルーティング設定のクエリを実行できます。

## 説明

最新バージョンの SEFAUtil はコマンドライン ツールでのみ提供されています。サポートされているグラフィカル ユーザー インターフェイスはありません。このツールは Microsoft Unified Communications Managed API (UCMA) 3.0 に基づいています。このツールの機能を使用すると、管理者やヘルプデスク エージェントは次の作業を実行できます。

  - ユーザーのすべてのコール ルーティング設定を表示する (着信転送、代理人、同時呼び出し、チーム呼び出し、グループ通話ピックアップなど)

  - 着信転送設定を有効化、無効化、変更する (宛先や無応答タイマーなど)

  - 着信転送の即時構成を有効化、無効化、変更する

  - 代理人設定を有効化、無効化、変更する

  - チーム呼び出しグループ設定を有効化、無効化、変更する
    
    > [!NOTE]
    > Lync Server 2013 SEFAUtil ツールの新機能


  - 同時呼び出し設定を有効化、無効化、変更する (宛先など)
    
    > [!NOTE]
    > Lync Server 2013 SEFAUtil ツールの新機能


  - グループ通話ピックアップ設定を有効化、無効化、変更する
    

    > [!WARNING]
    > Lync Server 2013 SEFAUtil ツールの新機能



このツールの制約は次のとおりです。

  - Lync Server プールに属しているユーザーのみをサポートしています。

  - 複数ユーザーのコール ルーティング設定の一括編集はサポートされていません。

## 出力

ツールの現在のバージョンでは、\[コマンド プロンプト\] ウィンドウでのみ結果が表示されます。詳しくは、このドキュメント後半の「例」をご覧ください。

## 用途

このツールを使用するいくつかの主なシナリオを次に示します。

  - 役員の内田さんは Lync Server テレフォニーに移行しました。彼の既存の PBX システムには代理人が設定されています。Lync への移行の一環として、管理者は既存の代理人の構成が反映されるように内田さんのルーティングを構成できます。

  - 西村さんは旅行中で、顧客からの重要な連絡を待っています。しかし、ホテル滞在中はコンピューターを使うことができません。彼女はヘルプデスクに電話して、勤務先電話番号にかかってきたすべての電話を携帯電話の番号に転送してもらうよう頼みました。ヘルプデスク担当者は、彼女のためにこのような構成を行うことができます。

  - 松本さんの勤務先電話番号にかかってくる電話は、勤務中は常に彼の携帯電話のボイスメールに送信されています。しかし、他の多くの場所では通話は問題なく機能しているようです。ヘルプデスクの技術者は松本さんのルーティング構成を確認できるので、彼の携帯電話に同時呼び出しが構成されていることを見つけます。技術者は松本さんにオフィスでの通信状態についてたずね、通信状態が良くない場合に着信通話を携帯電話のボイスメールへ送信しているのは同時呼び出しルールであることを特定できます。

  - 金子さんは Contoso の新入社員です。彼が参加する新しいチームでは、Microsoft Lync を有効にした場合のメンバー全員のチーム呼び出しが構成されています。管理者は金子さんのチーム呼び出しグループ設定に新しいチーム メンバー全員を含めることができます。また、チームの各メンバーに対して、金子さんをチーム呼び出しグループ メンバーとして追加できます。

  - Contoso の人事部門のカスタマー サービス プラクティスとは、すべての発信者に対して最初の電話から個人サービスを提供することです。部門のメンバー全員がお互いのすぐそばに座っているとすれば、チーム呼び出しで全員の電話が一斉に鳴るのはチームにとって非常に混乱のもとになります。チーム メンバー間の混乱を避けて最高のサービスを提供するために、Lync 管理者はグループ通話ピックアップ機能を利用します。管理者は部門の全員をピックアップ グループに追加して、ピックアップ グループ番号を伝えます。原田さんが席を外している場合は、彼女の電話が鳴っていることに気付いた松本さんが自分の席から電話に応答します。

## 要件

SEFAUtil ツールは信頼されたアプリケーション プールに属しているコンピューターでのみ実行できます。このコンピューターには UCMA 3.0 がインストールされている必要があります。ツールを実行するには、SEFAUtil アプリケーション ID を持つ新しい信頼されたアプリケーションをプール内に作成する必要があります。

**SEFAUtil ツール用の新しい信頼されたアプリケーションの作成**

1.  SEFAUTil ツールは信頼されたアプリケーション プールに属しているコンピューターでのみ実行できます。必要に応じて、Lync Server 管理シェルで次のコマンドレットを使用して、プールを新しい信頼されたアプリケーション プールとして追加できます。
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    > [!NOTE]
    > SEFAUtil ツールを実行するコンピューターには UCMA 3.0 をインストールする必要があります。


2.  信頼されたアプリケーションを SEFAUtil ツールのトポロジ内に定義する必要があります。SEFAUtil を新しい信頼されたアプリケーションとして定義するには、Lync Server 管理シェルで次のコマンドレットを実行します。
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    > [!NOTE]
    > 必要に応じて、別のポートを使用できます。


3.  トポロジの変更を有効にする必要があります。トポロジの変更を有効にするには、Lync Server 管理シェルで次のコマンドレットを実行します。
    
        Enable-CsToplogy

4.  必要に応じて、SEFAUtil ツールを実行するサーバーに Lync Server 2013 Resource Kit Tools をインストールします (サーバーは信頼されたアプリケーション プールに属している必要があります)。

5.  SEFAUtil が正しく実行していることを確認します。そのためには、Windows コマンド プロンプトから管理者権限でツールを実行し、展開内のユーザーの着信転送設定を表示します。既定では、ツールの場所は "…\\Program Files\\Microsoft Lync Server 2013\\Reskit" です。ユーザーの着信転送設定を表示するには、次のコマンドを実行します。
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    ユーザーの着信転送設定が表示されます。

## グループ通話ピックアップ

グループ通話ピックアップの機能を完全に有効にするには、Lync Server で追加の構成が必要です。ユーザーにピックアップ グループを割り当てる前に、この機能の計画と展開の手順について、グループ通話ピックアップの製品ドキュメントを参照してください。

## 例

## 現在の通話処理設定の表示

次のコマンドでは、ユーザーの通話処理が表示されます。`SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

> [!NOTE]
> この例では、<strong>/server</strong> スイッチで接続先の Lync Server を指定しています。


**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

## 着信転送/応答なしの宛先

この例では、着信転送/応答なしの宛先と呼び出しの遅延を設定します。ここでは /server スイッチを指定していないので、SEFAUtil では Lync Server の自動検出が試行されます。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

## 着信転送の即時有効化

この例では、別のユーザーへの着信転送をすぐに有効にします。

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

## 着信転送の即時無効化

この例では、別のユーザーへの着信転送をすぐに無効にします。

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## 代理人としてのユーザーの追加と代理人の同時呼び出しの設定

この例では、ユーザーを代理人として追加し、代理人の同時呼び出しを設定します。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

## 代理人の同時呼び出しルールの変更

この例では、前の例で設定した代理人の同時呼び出しルールを遅延呼び出しルールに変更します。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

## 代理人の削除

この例では代理人を削除します。

> [!NOTE]
> 最後の代理人が削除されると、代理人着信は自動的に無効になります。


    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## 代理人の追加と代理人への着信転送ルールの設定

この例では、代理人を追加し、代理人への着信転送ルールを設定します。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

## 同時呼び出しの有効化と宛先番号の設定

この例では、同時呼び出しを有効にして、同時呼び出しの宛先番号を設定します。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

> [!NOTE]
> 既に同時呼び出しを有効にしているユーザーの同時呼び出しの宛先番号を変更するには、コマンドに /enablesimulring スイッチを追加します。追加しない場合、宛先番号は変更されません。


**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

## 同時呼び出しの無効化

この例では、同時呼び出しを無効にします。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## チーム呼び出しのチーム メンバーの追加とチーム呼び出しメンバー グループへの同時呼び出しの設定

この例では、ユーザーのチーム呼び出しグループにチーム メンバーを追加し、チーム呼び出しグループへの同時呼び出しを有効にします。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

> [!NOTE]
> ユーザーのチーム呼び出しグループにチーム メンバーを追加すると、ユーザーの同時呼び出しの設定がチーム呼び出しグループを同時に呼び出すように自動的に切り替わります。


**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

## チーム呼び出しグループからのメンバーの削除

この例では、ユーザーのチーム呼び出しグループからチーム メンバーを削除します。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

> [!NOTE]
> 削除対象のメンバーがチーム呼び出しグループで唯一のメンバーである場合、チーム呼び出しグループの同時呼び出しは自動的に無効になります。


**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## チーム呼び出しグループの遅延呼び出しの設定

この例では、チーム呼び出しグループの時間設定の遅延呼び出しを変更します。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

## チーム呼び出しの有効化

この例では、ユーザーのチーム呼び出しを有効にします。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

> [!NOTE]
> ユーザーのチーム呼び出しグループにメンバーがいない場合、チーム呼び出しは有効になりません。


**出力**

## チーム呼び出しの無効化

この例では、ユーザーのチーム呼び出しを無効にします。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## グループ通話ピックアップの有効化とユーザーへのピックアップ グループの割り当て

この例では、ユーザーにピックアップ グループを割り当て、グループ通話ピックアップを有効にします。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

**出力**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

## グループ通話ピックアップの無効化

この例では、特定のユーザーのグループ通話ピックアップを無効にします。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

> [!NOTE]
> ユーザーのグループ通話ピックアップを無効にした場合、ユーザーに割り当てられたグループ番号は保持されません。そのユーザーのグループ通話ピックアップを後からもう一度有効にする場合は、/enablegrouppickup スイッチでグループ番号をもう一度割り当てる必要があります。


    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

## SYSPrep.ps1

## 説明

SYSPrep.ps1 は Windows PowerShell スクリプトであり、次の Lync Server 2013 必須コンポーネントを Windows Server 2008 オペレーティング システム コンピューターにインストールします。

  - Microsoft .Net Framework 4.5

  - Microsoft SQL Server Express

  - Windows Powershell Version 3.0

  - Visual C++ 2010 再頒布可能パッケージ

  - Internet Information Server の更新プログラム

  - Windows Identity Foundation

  - Lync Server 2013 のコア ファイル

このスクリプトは Microsoft Windows オペレーティング システム用のシステム準備ツールと名前は似ていますが、別のツールです。このスクリプトでは、Lync Server 2013 に必要なコンポーネントだけがインストールされます。これらの必須コンポーネントをインストールしたら、Windows SYSPrep ツールを使用して、サーバーのイメージを作成できます。

## 要件

SYSPrep.ps1 スクリプトを実行する前に、Windows Server 2008 オペレーティング システム コンピューター上のローカル フォルダー (**D:\\Setup** など) に必須コンポーネント ファイルをコピーする必要があります。このフォルダーには Lync Server 2013 ファイルのコピー (具体的には **Setup.exe.**) も含める必要があります。必須コンポーネント ファイルは次の場所からダウンロードできます。


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
<td><p>Windows Powershell Version 3.0</p></td>
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
<td><p>Lync Server 2013 メディアからコピー</p></td>
</tr>
</tbody>
</table>


## パラメーター

**–SetupFolder** パラメーターは必須コンポーネント ファイルのディレクトリの場所を引数として受け取ります。

## 例

SYSPrep.ps1 スクリプトを実行して Lync Server 2013 必須コンポーネントをインストールするには、管理者特権で実行しているコマンド プロンプトから次のコマンドを実行します。

    ./SysPrep.PS1 -SetupFolder D:\Setup

## Unassigned Number Announcements Migration

Unassigned Number Announcements Migration ツールを使用すると、Lync 管理者はアナウンス アプリケーションによるサービスを受けている未使用の番号の構成を移行元の Lync Server またはプールから移行先の Lync Server またはプールに移行できます。

## 説明

Unassigned Number Announcements Migration ツールは Windows PowerShell スクリプトであり、アナウンス アプリケーションによるサービスを受けている未使用の番号の構成を移行元のサーバーまたはプールから別のサーバーまたはプールに移行します。

Unassigned Number Announcements Migration スクリプトを実行すると、次の操作が行われます。

1.  移行元のサーバーまたはプールでホストされているアナウンス アプリケーションの未使用の番号のアナウンスが使用しているすべての音声ファイルを、移行先のサーバーまたはプールのファイル ストアに移行します。
    
    > [!NOTE]
    > 移行先のプールへのコピーが完了すると、音声ファイルは移行元のプールから削除されます。


2.  移行元のサーバーまたはプールでホストされているアナウンス アプリケーションに構成されているすべての未使用の番号のアナウンスを、移行先のサーバーまたはプールに移行します。

3.  移行元のサーバーまたはプールでホストされているアナウンス アプリケーションによるサービスを受けているすべての未使用の番号の範囲を、移行先のサーバーまたはプールにもう一度割り当てます。

スクリプトの実行が成功すると、移行元のサーバーまたはプールでホストされているアナウンス アプリケーションによるサービスを受けていたすべての未使用の番号の範囲が、同じ構成を使用して移行先のサーバーまたはプールによるサービスを受けるようになります。

## 出力

**Move-CsAnnouncementConfiguration** スクリプトでは、スクリプトを実行した Lync 管理シェル ウィンドウに移行操作の成功または失敗が示されます。

エラーによって操作の実行が中断した場合、移行に成功した未使用の番号の範囲は稼動状態で移行先に残り、移行する予定の残りの未使用の番号の範囲も稼動状態で移行元に残ります。残りの構成を完全に移行するには、エラーを修正してからもう一度スクリプトを実行します。

## 用途

Unassigned Number Announcements Migration スクリプトは、次の 3 つのシナリオで使用できます。

  - **構成の設定を新しいバージョンの Lync Server に移行する:** Contoso では Lync Server 2013 に移行している最中ですが、Lync Server 管理者は移行手順の一環として、アナウンス アプリケーションによるサービスを受けていた未使用の番号の構成を Lync Server 2010 展開から新しい Lync Server 2013 展開に移行したいと考えています。構成の設定を移行するために、Lync Server 管理者は Unassigned Number Announcements Migration ツールを使用します。

  - **Lync Server 2013 から Lync Server 2010 に展開をロールバックする:** 予期しない要因により、Contoso では新しい Lync Server 2013 展開への移行をロールバックする必要が生じました。サービスの中断を最小限に抑えるため、Lync Server 管理者は Unassigned Number Announcements Migration ツールを使用して、Lync Server 2013 展開から Lync Server 2010 展開に構成をロールバックします。

  - **Lync 展開間でデータを移行する:** Contoso では、あるプールのすべてのサーバーを新しいサーバーに置き換えている最中です。この計画では、新しい Lync Server 2013 プールを展開し、すべてのデータを古いプールから新しいプールに移行し、古いプールを廃止します。新しいプールを展開した後は、Unassigned Number Announcements Migration ツールを使用して、古いプールから新しいプールに構成を移行します。

## 要件

ツールの正常な実行に必要な主な要件は、次のとおりです。

1.  Lync Server 2013 管理シェル をインストールしたコンピューターでスクリプトを実行する必要があります。

2.  移行元と移行先の Lync Server またはプールでアナウンス アプリケーションが正常に展開されている必要があります。

## Move-CsAnnouncementConfiguration スクリプト

Move-CsAnnouncementConfiguration スクリプトに必要な 2 つのパラメーターを下の表に示します。

![Move-CsAnnouncementConfiguration のパラメーター](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration のパラメーター")

## 例

## Lync Server 2010 プールから Lync Server 2013 プールに未使用の番号のアナウンスの構成を移行する

この例では、移行元のプール (Lync Server 2010) から移行先のプール (Lync Server 2013) に未使用の番号のアナウンスを移行します。

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

## Lync Server 2013 プールから Lync Server 2010 プールに未使用の番号のアナウンスの構成を移行する

この例では、移行元のプール (Lync Server 2013) から移行先のプール (Lync Server 2010) に未使用の番号のアナウンスを移行します。

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

## Web Conf Data

Web Conf Data ツールを使用すると、Lync Server 2013 通信ソフトウェアの管理者は、開催者の Web 会議に関連付けられているデータをよりきめ細かく管理できます。特定のユーザーの会議データをタイムスタンプの条件に基づいて削除する場合などのシナリオが考えられます。

## 説明

このツールを使用すると、管理者は次の操作を実行できます。

1.  1 人のユーザーに関連付けられているすべての Web 会議データを検索する。

2.  1 人のユーザーに関連付けられているすべての Web 会議データを削除する。

3.  特定の日付よりも古い、1 人のユーザーに関連付けられているすべての Web 会議データを削除する。

4.  ユーザーがあるプールから別のプールに移行した場合に、その 1 人のユーザーに関連付けられているすべての Web 会議データを移行する。

> [!NOTE]
> Lync Server 2010 用の リソース キット ツール では、ユーザーがあるプールから別のプールに移行した場合にその 1 人のユーザーに関連付けられているすべての Web 会議データの移行がサポートされていました。このツールでは <strong>MoveConferenceData</strong> パラメーターのほうを優先して、この機能は現在廃止されています。このパラメーターについて詳しくは、<a href="https://technet.microsoft.com/ja-jp/library/gg398528(v=ocs.15)">Move-CsUser</a> コマンドレットを参照してください。


このツールでは、非アクティブな会議の会議データのみが削除されます。アクティブな会議 (開催中の会議) は削除できません。

このツールはターゲット ユーザーと同じプール内にあるコンピューターから実行する必要があります。会議コンテンツ データをこのツールで管理しているユーザーは同じユーザー プールに所属している必要があります。

## 出力

このツールでは、次の各操作結果が出力されます。

  - クエリを実行した場合は、該当のユーザーを開催者とする、すべての非アクティブな会議のデータ フォルダーのリストが出力されます。

  - 削除を実行した場合は、削除対象のデータがあるすべての会議データ フォルダーのリストが出力されます。

## 要件

このツールは、開催者が現在所属しているのと同じプール内で実行する必要があります。

このツールは、コンテンツ ファイル ストアへのアクセス権を持つ管理者特権を使用して実行する必要があります。

## 例

下の表にパラメーターを示します (一部は例で使用されています)。

![Web Conf Data ツールのパラメーター](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web Conf Data ツールのパラメーター")

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

上の例は query コマンドの動作を示しています。このコマンドの出力は、ツールの影響を受けるすべての会議コンテンツ フォルダーのリストになります。

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

上の例は delete コマンドの動作を示しています。delete コマンドにより、このユーザーのすべての非アクティブな会議フォルダーが削除されます。

## 要約

このツールは、会議データをより正確に管理する必要のある管理者にとって役立つツールとなります。
