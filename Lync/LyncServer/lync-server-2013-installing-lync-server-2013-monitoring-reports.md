---
title: Lync Server 2013 監視レポートのインストール
TOCTitle: Lync Server 2013 監視レポートのインストール
ms:assetid: 6f417569-b100-442c-ad48-fdd794626cf7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204989(v=OCS.15)
ms:contentKeyID: 48272484
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 監視レポートのインストール

 

_**トピックの最終更新日:** 2015-03-09_

Microsoft Lync Server 2013 監視レポートは、組織内の通信セッションの品質と量に関するさまざまな情報を提供します。ただし、監視レポートは Lync Server 2013 のインストール時には自動的にインストールされません。監視レポートは、Lync Server がコンピューターにインストールされた後で個別にインストールする必要があります。

> [!NOTE]
> 監視レポートは、監視データベースがインストールされているのと同じコンピューターにインストールすることをお勧めします。これにより、レポートへのアクセス許可の割り当てプロセスが簡単になります。監視ストアをホストしているコンピューターに監視レポートをインストールすると、別のコンピューター上で実行されている Reporting Services とデータベースが対話できるようにするためのアクセス許可を構成する必要がなくなります。


Lync Server 監視レポートには、会議、ピアツーピア IM セッション、ユーザー登録、応答グループ アプリケーションなどについての詳細情報を提供するように設計された 30 種類以上のレポートが含まれます。2013 バージョンでは、Lync Server 監視レポートの多くの機能が強化されています。

  - **新しい音声品質レポート**: この新しいレポートには、異なる種類の通話 (たとえば有線通話とワイヤレス通話) 間で通話の品質を比較する[メディア品質比較レポート](lync-server-2013-media-quality-comparison-report.md)と、ユーザーが会議に参加するための所要時間の情報を提供する[会議参加時間レポート](lync-server-2013-conference-join-time-report.md)が含まれます。

  - **ビデオ セッションとアプリケーション共有セッションの両方の分析およびトラブルシューティングのためのレポートの改善**: [Lync Server 2013 のメディア品質概要レポート](lync-server-2013-media-quality-summary-report.md)を利用してビデオ通話とアプリケーション共有通話を分析でき、[Lync Server 2013 のサーバー パフォーマンス レポート](lync-server-2013-server-performance-report.md)にはこれらの通話が発生したサーバーのパフォーマンスの詳細が表示されます。また、ビデオおよびアプリケーション共有の指標が、[Lync Server 2013 ピアツーピア セッション詳細レポート](lync-server-2013-peer-to-peer-session-detail-report.md)と[会議詳細レポート](lync-server-2013-conference-detail-report.md)でも報告されるようになりました。

  - **レポートのパフォーマンスの向上**: 応答時間とデータ取得時間が短縮され、レポート間の移動をすばやく簡単に行えるようになりました。

個々のレポートの詳細については、監視レポートのドキュメントを参照してください。

> [!NOTE]
> Lync Server 2013 には、これ以外に、QoE 通話記録サブレポートという新しいレポートも含まれています。ただし、このレポートは主に内部用であり、直接アクセスするためのものではありません。


Lync Server 監視レポートをインストールするには、Lync Server 展開ウィザードを使用する方法と、Lync Server 2013 インストール ファイルに含まれている Windows PowerShell スクリプトを使用する方法の 2 つがあります。どちらの方法でレポートをインストールする場合でも、最初に次のことを確認する必要があります。

  - 監視データベースのユーザー アカウントにデータベースの役割を追加する権限を持っている。

  - SQL Server Reporting Services のコンテンツ マネージャーの役割を持っている。この役割では、SQL Server Reporting Services にレポートを展開する権限が付与されます。

展開ウィザードを使用して監視レポートをインストールするには、次の手順を実行します。

1.  \[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 展開ウィザード**\] の順にクリックします。

2.  展開ウィザードで \[**監視レポートの展開**\] をクリックして、監視レポートの展開ウィザードを開始します。

3.  監視レポートの展開ウィザードの \[**監視データベースの指定**\] ページで、\[**監視データベース**\] ドロップダウン リストに、監視ストアをホストしているコンピューターの完全修飾ドメイン名が表示されていることを確認します (複数の監視ストアがある場合は、ドロップダウン リストから適切なサーバーを選択する必要があります)。\[**SQL Server Reporting Services (SSRS) インスタンス**\] ボックスに正しい SQL Server インスタンス (たとえば **atl-sql-001.litwareinc.com/archinst**) が表示されていることを確認し、\[**次へ**\] をクリックします。

4.  \[**資格情報の指定**\] ページの \[**ユーザー名**\] ボックスに、監視レポートへのアクセス時に使用するアカウントのドメイン名とユーザー名 (たとえば **litwareinc\\kenmyer**) を入力します。この形式 (ドメイン\\ユーザー名) を使用しない場合はエラーが発生します。
    
    \[**パスワード**\] ボックスにユーザー アカウントのパスワードを入力し、\[**次へ**\] をクリックします。このアカウントに特別な権限は必要ありません。セットアップが完了すると、このアカウントには必要なログオンおよびデータベース アクセス許可が自動的に付与されます。

5.  \[**読み取り専用グループの指定**\] ページの \[ユーザー グループ\] ボックスに、SQL Server Reporting Services への読み取り専用の管理者アクセス権を付与するセキュリティ グループの名前を入力します。たとえば、レポートへの読み取り専用の管理者アクセス権を付与するには、「**RTCUniversalReadOnlyAdmins**」と入力します。その後、\[**次へ**\] をクリックします。

6.  \[**コマンドを実行しています**\] ページで、\[**完了**\] をクリックします。

監視レポートは、Lync Server 管理シェルから DeployReports.ps1 スクリプトを実行してインストールすることもできます。この Windows PowerShell スクリプトは、\\Setup\\ReportingSetup フォルダーの Lync Server のインストール メディアにあります。DeployReports.ps1 を使用して監視レポートをインストールするには、管理シェル プロンプトで次のようなコマンドを入力します。

    D:\Setup\AMD64\Setp\ReportingSetup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

このコマンドで使用されているパラメーターの説明を次の表に示します。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>パラメーター名</th>
<th>必須かどうか</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>storedUserName</p></td>
<td><p>はい</p></td>
<td><p>監視ストアへのアクセスに使用するユーザーアカウント (形式はドメイン\ユーザー名)。次に例を示します。</p>
<pre><code>-storedUserName &quot;litwareinc\kenmyer&quot;</code></pre>
<p>このアカウントには、SQL Server と SQL Server Reporting Services のアクセス許可が事前に指定されている必要があります。指定されていない場合、スクリプトは失敗します。</p></td>
</tr>
<tr class="even">
<td><p>storedPassword</p></td>
<td><p>はい</p></td>
<td><p>監視ストアへのアクセスに使用するユーザー アカウントのパスワード。</p></td>
</tr>
<tr class="odd">
<td><p>readOnlyGroupName</p></td>
<td><p>いいえ</p></td>
<td><p>監視レポートへの読み取り専用アクセス権を付与するユーザーが属するドメインまたはローカル セキュリティ グループ。指定したグループが存在しない場合、スクリプトは失敗することに注意してください。後でこれらのアクセス権を無効にしたり他のユーザーまたはグループにアクセス権を付与したりする必要が生じた場合は、SQL Service Reporting Services レポート マネージャーを使用して実行できます。</p></td>
</tr>
<tr class="even">
<td><p>reportSqlServerInstance</p></td>
<td><p>いいえ</p></td>
<td><p>Reporting Service をホストする SQL Server インスタンス。Reporting インスタンスは、レポート サーバーの完全修飾ドメイン名を使用して指定する必要があります。次に例を示します。</p>
<pre><code>-reportServerSqlInstance atl-sql-001.litwareinc.com</code></pre>
<p>このパラメーターが指定されていない場合、スクリプトは、レポート サービスが監視データベースをホストしているのと同じ SQL Server インスタンスによってホストされていると見なします。</p></td>
</tr>
<tr class="odd">
<td><p>monitoringDatabaseId</p></td>
<td><p>いいえ</p></td>
<td><p>監視データベースのサービス ID。次のコマンドを実行することで、監視データベースの ID を取得できます。</p>
<pre><code>Get-CsService -MonitoringDatabase</code></pre></td>
</tr>
</tbody>
</table>


監視レポートのインストールが完了したら、Set-CsReportingConfiguration コマンドレットを使用して、これらのレポートへのアクセスに使用する URL を構成する必要があります。このタスクは、Lync Server 管理シェルから次の Windows PowerShell コマンドを実行することによって実行できます。レポート URL の構成時には、必須ではありませんが、HTTPS プロトコルを使用することをお勧めします。

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

上のコマンドでは、ReportingUrl プロパティを、SQL Server 2008 R2 Reporting Services で使用されているレポート マネージャー URL に設定する必要があります。レポート マネージャー URL は、SQL Server Reporting Services がインストールされているコンピューターで次の手順を実行することで確認できます。

1.  \[スタート\]、\[すべてのプログラム\]、\[Microsoft SQL Server 2008 R2\]、\[構成ツール\]、\[Reporting Services 構成マネージャー\] の順にクリックします。

2.  \[Reporting Services 構成の接続\] ダイアログ ボックスで、Reporting Services コンピューターの名前が \[サーバー名\] ボックスに表示されていることを確認します。\[レポート サーバー インスタンス\] ドロップダウン リストから SQL Server インスタンスを選択し、\[接続\] をクリックします。

3.  Reporting Services 構成マネージャーで、\[レポート マネージャー URL\] をクリックします。すると、\[レポート マネージャー URL\] ウィンドウに 1 つ以上の URL が表示されます。いずれの URL もレポート用 URL として使用できますが、上で説明したように ReportingUrl には HTTPS プロトコルを使用することをお勧めします。

監視データベースのミラー データベースを設定した場合は、監視レポートをミラー データベースとも関連付ける必要があります。詳細については、「[監視レポートとミラー データベースの関連付け](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md)」を参照してください。

