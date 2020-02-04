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
ms.openlocfilehash: 6fcf6679481d4f35a457eb72960a8ae999b004d3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a>Lync Server 2013 でのデータベース構成のテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-07-07_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>確認のスケジュール</p></td>
<td><p>[毎日]</p></td>
</tr>
<tr class="even">
<td><p>テストツール</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要なアクセス許可</p></td>
<td><p>Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーであり、SQL Server の管理者権限を持っている必要があります。</p>
<p>Windows PowerShell のリモートインスタンスを使って実行する場合、ユーザーには、<strong>テスト用のデータベース</strong>コマンドレットを実行する権限を持つ RBAC の役割を割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

**テスト用のデータベース**コマンドレットは、1つ以上の Lync Server 2013 データベースへの接続を確認します。 **テスト用のデータベース**コマンドレットを実行すると、Lync Server トポロジを読み取り、関連データベースに接続しようとし、各試行の成功または失敗を報告します。 接続できる場合は、コマンドレットによって、データベース名、SQL Server のバージョン情報、インストールされているミラーデータベースの場所などの情報も報告されます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

例1に示すコマンドは、サーバーの全体管理データベースの構成を確認します。

    Test-CsDatabase -CentralManagementDatabase

使用例 2: コンピューター atl-sql-001.litwareinc.com にインストールされているすべての Lync Server データベースを確認します。

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

例3では、コンピューター atl-sql-001.litwareinc.com にインストールされているアーカイブデータベースに対してのみ確認が行われます。 SqlInstanceName パラメーターは、アーカイブデータベースが配置されている SQL Server インスタンス (アーキテクチャ) を指定するために含まれていることに注意してください。

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

例4に示すコマンドは、ローカルコンピューターにインストールされているデータベースを確認します。

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

データベース接続が適切に構成されている場合は、次のような出力が返されます。これは、成功プロパティが**True**とマークされていることになります。

SqlServerFqdn: atl-sql-001.litwareinc.com

SqlInstanceName: rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: xds

データソース

SQLServerVersion :

ExpectedVersion : 10.13.2

バージョン:

成功: True

SqlServerFqdn: atl-sql-001.litwareinc.com

SqlInstanceName: rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: lis

データソース

SQLServerVersion :

ExpectedVersion: 3.1.1

バージョン:

成功: True

データベースが正しく構成されていても利用可能な場合は、"成功" フィールドに**False**と表示され、追加の警告と情報が提供されます。

SqlServerFqdn: atl-sql-001.litwareinc.com

SqlInstanceName: rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: xds

データソース

SQLServerVersion :

ExpectedVersion : 10.13.2

バージョン:

成功: False

SqlServerFqdn: atl-cs-001.litwareinc.com

SqlInstanceName: rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: lis

データソース

SQLServerVersion :

ExpectedVersion: 3.1.1

バージョン:

成功: False

警告: テスト-CsDatabase でエラーが発生しました。 ログファイルを参照してください。

詳細な分析と、すべてのエラー (2) と警告 (0) が対応していることを確認する

続行してください。

警告: 詳細な結果は次のページでご覧いただけます。

"C:\\\\\\AppData\\ローカル\\Temp\\2\\テスト-csdatabase-b18d488a-8044-4679-bbf2-

04d593cce8e6 "。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に **、テスト用のデータベース**が失敗する一般的な理由をいくつか示します。

  - 指定されたパラメーター値が正しくありません。 使用する場合は、オプションのパラメーターが正しく構成されている必要があります。または、テストが失敗します。 省略可能なパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。

  - データベースが正しく構成されていないか、まだ配置されていない場合、このコマンドは失敗します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Get-CsDatabaseMirrorState](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[CsService の入手](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get-CsUserDatabaseState](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

