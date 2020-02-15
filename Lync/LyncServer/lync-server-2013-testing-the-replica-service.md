---
title: 'Lync Server 2013: レプリカサービスのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the replica service
ms:assetid: 4ff2cc91-0036-4c5a-9792-7bf43d8ce18d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727303(v=OCS.15)
ms:contentKeyID: 63969600
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ad585ab12d874b7689aab6442ac913a06c8792f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a>Lync Server 2013 でのレプリカサービスのテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-11-03_


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
<td><p>Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</p>
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、 <strong>Test-CsReplica</strong>コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

**Test-csreplica**コマンドレットは、Lync Server 2013 replica service がローカルコンピューター上で実行されているかどうかを確認します。 **Test-CsReplica**コマンドレットは、次のようなタスクを実行します。

  - レプリケーターエージェントサービスと集中ログエージェントサービスの状態を確認する

  - Windows ファイアウォールで必要なポートが開かれていることを確認する

  - 必要な Active Directory およびローカルコンピューターのセキュリティグループが存在することを確認します。

このコマンドレットはローカルで実行する必要があることに注意してください。 つまり、これは、レプリカサービスが実行されているのと同じコンピューター上で実行する必要があります。 リモートサーバーに対して**Test-CsReplica**コマンドレットを実行するためのオプションはありません。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

例1に示すコマンドは、ローカルコンピューター上の Lync Server 2013 レプリカサービスをテストします。 この例では、Verbose パラメーターを使用して、テストの最終的なエラーや成功を含むテストに関する情報、およびテストで生成されたレポートの場所が画面に表示されていることを保証します。

    Test-CsReplica -Verbose

例 2 は、例 1 に示したコマンドの変化形です。 この例では、Report パラメーターは、テストによって生成されるレポートのフォルダーパスと名前を指定するために含まれています。 レポートのパスを指定しない場合、レポートには次のような自動生成された名前が与えられます。

C:\\ユーザー\\管理者.\\Litwareinc\\AppData\\ローカル\\一時\\1 テスト-3db40ee0-4b5d-4f58-8d3d-b1e61253129e

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

ここにセクション本文を挿入します。

VERBOSE: 新しいログファイルを作成して\\い\\ます\\"\\C\\:\\ユーザーが AppData ローカル一時テスト-csreplica-3cb066b3-dd23-411a-8932-99f01c0f940c をテストしています。

VERBOSE: 新しいログファイルを作成して\\い\\ます\\"\\C\\:\\ユーザーが AppData ローカル一時テスト-csreplica-3cb066b3-dd23-411a-8932-99f01c0f940c をテストしています。

VERBOSE: "Test-CsReplica" 処理は正常に完了しました。

VERBOSE: 詳細な結果は、「C\\: ユーザー\\が AppData\\\\ローカル\\一時\\テスト-csreplica-3cb066b3-dd23-411a-8932-99f01c0f940c をテストする」に記載されています。

VERBOSE: 新しいログファイルを作成しています

"C:\\ユーザー\\が\\AppData\\ローカル\\一時\\2\\テスト-csreplica-29fddb35-f56e-4e3c-8f4c-e をテストします。

d3bd0e4a083 "。

VERBOSE: 新しいログファイルを作成しています

"C:\\ユーザー\\が\\AppData\\ローカル\\一時\\2\\テスト-csreplica-29fddb35-f56e-4e3c-8f4c-e をテストします。

d3bd0e4a083 "。

警告: Test-CsReplica が失敗しました。

警告: 詳細な結果は次の場所にあります。

"C:\\ユーザー\\が\\AppData\\ローカル\\一時\\2\\テスト-csreplica-29fddb35-f56e-4e3c-8f4c-e をテストします。

d3bd0e4a083 "。

テスト-CsReplica: コマンドの実行に失敗しました。要求されたレジストリアクセスがありません

れる.

行: 1 char: 1

\+テスト-CsReplica-Verbose

\+ ~~~~~~~~~~~~~~~~~~~~~~~

\+カテゴリ情報: InvalidOperation: (:)\[テスト-csreplica\]、セキュリティ

Exception

\+FullyQualifiedErrorId: ProcessingFailed、Microsoft. 管理

予約.TestReplicaCmdlet

PS C:\\ユーザー\\のテスト\>

PS C:\\Test-csucwaconference\\-\> targetfqdn "LyncTest" をテストします。

icrosoft.com "

警告: 指定された完全修飾のレジストラーポート番号を読み取ることができませんでした

ドメイン名 (FQDN)。 既定のレジストラーポート番号を使用します。 例外

System.invalidoperationexception: トポロジ内に一致するクラスターが見つかりませんでした。

下部

TryRetri を SipSyntheticTransaction していることを示します。

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Test-csucwaconference: に対してテストユーザーが割り当てられていません

\[LyncTest.SelfHost.Corp.Microsoft.com\]。 テストユーザーの構成を確認します。

行: 1 char: 1

\+Test-csucwaconference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+カテゴリ情報: ResourceUnavailable 不可: (:)\[Test-csucwaconference\]

、System.invalidoperationexception

\+FullyQualifiedErrorId: Notていない Testusers、Microsoft Rtc.

TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

以下に **、テスト用のレプリカ**が失敗する主な理由を示します。

  - レプリケーターエージェントサービスと集中ログエージェントサービスでは、さらに問題が発生する可能性があります。

  - Windows ファイアウォールで必要なポートが開かれていない可能性があります。

  - 必要な Active Directory およびローカルコンピューターのセキュリティグループが存在しない可能性があります

</div>

</div>

<span> </span>

</div>

</div>

</div>

