---
title: 'Lync Server 2013: Lync Server 2013 の監視レポートのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync Server 2013 Monitoring Reports
ms:assetid: 6f417569-b100-442c-ad48-fdd794626cf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204989(v=OCS.15)
ms:contentKeyID: 48184445
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02be5b77ffc64ba7c206f141f1600ddfb858acfc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-server-2013-monitoring-reports"></a>Lync Server 2013 監視レポートのインストール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-02-27_

Microsoft Lync Server 2013 の監視レポートでは、組織内で発生する通信セッションの品質と量に関するさまざまな情報が提供されます。 ただし、Lync Server 2013 をインストールしても、監視レポートは自動的にはインストールされません。その代わりに、Lync Server がコンピューターにインストールされている場合にのみ、監視レポートを個別にインストールする必要があります。

<div>


> [!NOTE]  
> 監視レポートは、監視データベースがインストールされているのと同じコンピューターにインストールすることをお勧めします。これにより、レポートへのアクセス許可の割り当てプロセスが簡単になります。監視ストアをホストしているコンピューターに監視レポートをインストールすると、別のコンピューター上で実行されている Reporting Services とデータベースが対話できるようにするためのアクセス許可を構成する必要がなくなります。



</div>

Lync Server の監視レポートには、電話会議、ピアツーピア IM セッション、ユーザー登録、応答グループアプリケーションなどに関する詳細情報を提供するように設計された30個以上のレポートが含まれています。 2013バージョンでは、Lync Server の監視レポートにはいくつかの機能拡張が含まれています。

  - **新しい音声品質レポート**。 これらの新しいレポートには、 [Lync Server 2013 のメディア品質比較レポート](lync-server-2013-media-quality-comparison-report.md)が含まれています。これはさまざまな通話の種類 (たとえば、有線通話とワイヤレス呼び出しの間) で品質を比較します。また、 [Lync Server 2013 の電話会議参加時間レポート](lync-server-2013-conference-join-time-report.md)は、ユーザーが会議に参加するのに必要な時間に関する情報を提供します。

  - **ビデオおよびアプリケーション共有セッションの分析とトラブルシューティングのためのレポートが向上しました。** Lync [server 2013 のメディア品質概要レポート](lync-server-2013-media-quality-summary-report.md)では、ビデオおよびアプリケーション共有の通話を分析することができますが、 [lync Server 2013 のサーバーパフォーマンスレポートで](lync-server-2013-server-performance-report.md)は、これらの呼び出しを生成しているサーバーのパフォーマンスの詳細が示されています。 また、ビデオとアプリケーション共有の測定基準は、lync [server 2013 のピアツーピアセッション詳細レポート](lync-server-2013-peer-to-peer-session-detail-report.md)、および[lync Server 2013 の会議詳細レポート](lync-server-2013-conference-detail-report.md)によって報告されるようになりました。

  - **レポートのパフォーマンスの向上**: 応答時間とデータ取得時間が短縮され、レポート間の移動をすばやく簡単に行えるようになりました。

個々のレポートの詳細については、監視レポートのドキュメントを参照してください。

<div>


> [!NOTE]  
> もう1つの新しいレポートがあります。「QoE Call Detail サブレポート」– Lync Server 2013 に含まれています。 ただし、このレポートは主に内部用であり、直接アクセスするためのものではありません。



</div>

Lync Server の監視レポートをインストールするには、次の2つの方法があります。 lync server 展開ウィザードを使用するか、Lync Server 2013 のインストールファイルに付属する Windows PowerShell スクリプトを使用することができます。 どちらの方法でレポートをインストールする場合でも、最初に次のことを確認する必要があります。

  - 監視データベースのユーザー アカウントにデータベースの役割を追加する権限を持っている。

  - SQL Server Reporting Services のコンテンツ マネージャーの役割を持っている。この役割では、SQL Server Reporting Services にレポートを展開する権限が付与されます。

展開ウィザードを使用して監視レポートをインストールするには、次の手順を実行します。

1.  [**スタート**]、[**すべてのプログラム**]、[ **Microsoft lync Server 2013**]、[ **lync server 展開ウィザード**] の順にクリックします。

2.  展開ウィザードで [**監視レポートの展開**] をクリックして、監視レポートの展開ウィザードを開始します。

3.  監視レポートの展開ウィザードの [**監視データベースの指定**] ページで、[**監視データベース**] ドロップダウン リストに、監視ストアをホストしているコンピューターの完全修飾ドメイン名が表示されていることを確認します (複数の監視ストアがある場合は、ドロップダウン リストから適切なサーバーを選択する必要があります)。[**SQL Server Reporting Services (SSRS) インスタンス**] ボックスに正しい SQL Server インスタンス (たとえば **atl-sql-001.litwareinc.com/archinst**) が表示されていることを確認し、[**次へ**] をクリックします。

4.  [**資格情報の指定**] ページの [**ユーザー名**] ボックスに、監視レポートにアクセスするときに使用するアカウントのドメイン名とユーザー名を入力します (たとえば、 **\\litwareinc kenmyer**)。 この形式 (ドメイン\\ユーザー名) を使用しない場合は、エラーが発生します。
    
    [**パスワード**] ボックスにユーザー アカウントのパスワードを入力し、[**次へ**] をクリックします。 このアカウントには特別な権限は必要ないことに注意してください。 セットアップが完了すると、アカウントには必要なログオンおよびデータベースのアクセス許可が自動的に与えられます。

5.  [**読み取り専用グループの指定**] ページの [ユーザー グループ] ボックスに、SQL Server Reporting Services への読み取り専用の管理者アクセス権を付与するセキュリティ グループの名前を入力します。たとえば、レポートへの読み取り専用の管理者アクセス権を付与するには、「**RTCUniversalReadOnlyAdmins**」と入力します。その後、[**次へ**] をクリックします。

6.  [**コマンドを実行しています**] ページで、[**完了**] をクリックします。

監視レポートは、スクリプトの配置レポートを実行することによって、Lync Server 管理シェルからインストールすることもできます。 ps1;この Windows PowerShell スクリプトは、 \\Lync Server インストールメディアのセットアップ\\の [reportingsetup] フォルダーにあります。 DeployReports. ps1 を使用して監視レポートをインストールするには、管理シェルプロンプトで次のようなコマンドを入力します。

    C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

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
<th>必須</th>
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
<td><p>監視レポートへの読み取り専用アクセス権を付与するユーザーが属するドメインまたはローカル セキュリティ グループ。 指定したグループが存在しない場合、スクリプトは失敗することに注意してください。 後でこれらのアクセス権を無効にしたり他のユーザーまたはグループにアクセス権を付与したりする必要が生じた場合は、SQL Service Reporting Services レポート マネージャーを使用して実行できます。</p></td>
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


監視レポートのインストールが完了したら、Set-CsReportingConfiguration コマンドレットを使用して、これらのレポートへのアクセスに使用する URL を構成する必要があります。 このタスクは、次の Windows PowerShell コマンドを実行することによって、Lync Server 管理シェルから実行できます。 レポート URL の構成時には、必須ではありませんが、HTTPS プロトコルを使用することをお勧めします。

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

上のコマンドでは、ReportingUrl プロパティを、SQL Server 2008 R2 Reporting Services で使用されているレポート マネージャー URL に設定する必要があります。レポート マネージャー URL は、SQL Server Reporting Services がインストールされているコンピューターで次の手順を実行することで確認できます。

1.  [スタート]、[すべてのプログラム]、[Microsoft SQL Server 2008 R2] 、[構成ツール]、[Reporting Services 構成マネージャー] の順にクリックします。

2.  [Reporting Services 構成の接続] ダイアログ ボックスで、Reporting Services コンピューターの名前が [サーバー名] ボックスに表示されていることを確認します。[レポート サーバー インスタンス] ドロップダウン リストから SQL Server インスタンスを選択し、[接続] をクリックします。

3.  Reporting Services 構成マネージャーで、[レポート マネージャー URL] をクリックします。すると、[レポート マネージャー URL] ウィンドウに 1 つ以上の URL が表示されます。いずれの URL もレポート用 URL として使用できますが、上で説明したように ReportingUrl には HTTPS プロトコルを使用することをお勧めします。

監視データベースのミラーデータベースを設定した場合は、監視レポートをミラーデータベースにも関連付ける必要があります。 詳細については、「 [Lync Server 2013 での監視レポートとミラーデータベースの関連付け](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

