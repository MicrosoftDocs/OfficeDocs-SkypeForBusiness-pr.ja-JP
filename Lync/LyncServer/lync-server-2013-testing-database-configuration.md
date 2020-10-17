---
title: 'Lync Server 2013: データベース構成のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1d57659c93aa42392f5408721157df1d14b56b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504104"
---
# <a name="testing-database-configuration-in-lync-server-2013"></a>Lync Server 2013 でのデータベース構成のテスト

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-07-07_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>検証スケジュール</p></td>
<td><p>毎日</p></td>
</tr>
<tr class="even">
<td><p>テストツール</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要なアクセス許可</p></td>
<td><p>Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があり、SQL Server の管理者権限を持っている必要があります。</p>
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、 <strong>Test-CsDatabase</strong> コマンドレットを実行する権限を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

**Test-CsDatabase**コマンドレットは、1つまたは複数の Lync Server 2013 データベースへの接続を確認します。 このコマンドを実行すると、Lync Server トポロジが読み取られ、関連するデータベースへの接続が試行 **された** 後、試行の成功または失敗が報告されます。 接続されると、コマンドレットは、データベース名、SQL Server バージョン情報、およびインストールされたミラー データベースの場所のような情報のレポートを戻します。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

例 1 に示すコマンドは、中央管理データベースの構成を確認します。

    Test-CsDatabase -CentralManagementDatabase

例2では、コンピューター atl-sql-001.litwareinc.com にインストールされているすべての Lync Server データベースを確認します。

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

例 3 では、コンピューター atl-sql-001.litwareinc.com にインストールされているアーカイブ データベースに対してのみ確認が行われます。アーカイブ データベースが置かれている SQL Server インスタンス (Archinst) を指定するために、SqlInstanceName パラメーターが含まれています。

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

例 4 に示すコマンドは、ローカル コンピューター上にインストールされたデータベースを確認します。

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

データベース接続が正しく構成されていると、次のような出力が得られます。これは、Succeed プロパティが **True**として設定されています。

SqlServerFqdn: atl-sql-001.litwareinc.com

SqlInstanceName: rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: xds

データ

SQLServerVersion :

ExpectedVersion : 10.13.2

バージョン:

成功: True

SqlServerFqdn: atl-sql-001.litwareinc.com

SqlInstanceName: rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: lis

データ

SQLServerVersion :

ExpectedVersion: 3.1.1

バージョン:

成功: True

データベースが正しく構成されていても利用可能な場合は、[成功] フィールドが **False**と表示され、追加の警告と情報が提供されます。

SqlServerFqdn: atl-sql-001.litwareinc.com

SqlInstanceName: rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: xds

データ

SQLServerVersion :

ExpectedVersion : 10.13.2

バージョン:

成功: False

SqlServerFqdn: atl-cs-001.litwareinc.com

SqlInstanceName: rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: lis

データ

SQLServerVersion :

ExpectedVersion: 3.1.1

バージョン:

成功: False

警告: Test-CsDatabase にエラーが発生しました。 ログファイルを参照してください。

詳細な分析を行い、すべてのエラー (2) と警告 (0) が解決されていることを確認する

続行してください。

警告: 詳細な結果は次の場所にあります。

「C: \\ ユーザー \\ が \\ AppData \\ ローカル \\ 一時 \\ 2 \\ Test をテストする-csdatabase-b18d488a-8044-4679-bbf2-

04d593cce8e6.html "

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

**テスト用データベース**が失敗する主な理由を次に示します。

  - 指定されたパラメーター値が正しくありません。 省略可能なパラメーターが使用されている場合、オプションのパラメーターが正しく構成されている必要があります。テストは失敗します。 オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。

  - データベースが正しく構成されていないか、まだ展開されていない場合、このコマンドは失敗します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Get-csdatabasemirrorstate 戻し](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[取得-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[取得-CsUserDatabaseState](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

