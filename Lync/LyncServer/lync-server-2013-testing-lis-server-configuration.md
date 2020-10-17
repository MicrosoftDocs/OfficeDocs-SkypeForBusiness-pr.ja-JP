---
title: 'Lync Server 2013: LIS サーバーの構成のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8893964ce1982c67dc97ed93bca9ba19ec2f24e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536020"
---
# <a name="testing-lis-server-configuration-in-lync-server-2013"></a>Lync Server 2013 での LIS サーバーの構成のテスト

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-06-05_


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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsLisConfiguration コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Test-CsLisConfiguration コマンドレットでは、LIS web サービスに接続できるかどうかを検証します。 Web サービスに接続できる場合は、特定の場所が見つからないかどうかに関係なく、テストは成功したと見なされます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Test-CsLisConfguration コマンドレットを実行するには、事前に構成されたテストアカウントを使用するか (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照)、Lync Server が有効になっているすべてのユーザーのアカウントを使用します。 テストアカウントを使用してこのチェックを実行するには、テストする Lync Server プールの FQDN を指定するだけで済みます。 以下に例を示します。

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

実際のユーザーアカウントを使用してこのチェックを実行するには、まず、アカウント名とパスワードを含む Windows PowerShell credentials オブジェクトを作成する必要があります。 その資格情報オブジェクトと、Export-cslisconfiguration を呼び出すときにアカウントに割り当てられた SIP アドレスを含める必要があります。

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

詳細については、 [export-cslisconfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) コマンドレットのヘルプドキュメントを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

LIS が正しく構成されている場合は、次のような出力が得られ、Result プロパティは Success としてマークされ **ます。**

TargetUri https://atl-cs-001.litwareinc.com:443/locationinformation/

liservice svc

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間:00:00: 06.1616913

エラー

分析

指定したユーザーがログオンまたはログオフできない場合は、結果がエラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。

TargetUri

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間: 00:00:00

エラー: 11004、要求された名前は有効ですが、要求されたデータがありません

種類が見つかりました

分析

Test-CsLisConfiguration: トポロジ内に一致するクラスターが見つかりませんでした。

たとえば、前の出力には「トポロジ内に一致するクラスターが見つかりません」というメモが含まれています。 これは通常、エッジサーバーに問題があることを示しています: LIS は、サービスプロバイダーに接続し、アドレスを検証します。

Test-CsLisConfiguration が失敗した場合は、次のように詳細パラメーターを含めて、テストを再実行することをお勧めします。

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose パラメーターが含まれている場合、Test-CsLisConfiguration は、指定されたユーザーが Lync Server にログオンできるかどうかを確認したときに実行された各アクションのステップバイステップのアカウントを返します。 以下に例を示します。

場所情報サービスを呼び出しています。

サービスパス = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc

Subnet =

BssId = 5

Ch/Sid =

PortId =

PortIdSubType = 未定義の種類

Mac

例外 ' 場所情報 Web サービス要求が応答コード Item400 で失敗しました。 ' ワークフローの STLisConfigurationWorkflow の実行中に発生しました。この操作は、ワークフローの実行中に発生します。

以前の出力を詳しく調べると、場所情報サービスを呼び出した後にコマンドレットが失敗したことがわかります。 その呼び出しで使用されたパラメーターの1つは次のとおりです。

BssId = 5

これは、基本サービスセット識別子 (BssID) の有効な値ではありません。 代わりに、BssID は次のようになります。

12-34-56-78-90-ab

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

Test-CsLisConfiguration が失敗する可能性のある一般的な理由を次に示します。

  - 指定されたパラメーター値が正しくありません。 前の例で示されているように、オプションのパラメーターが正しく構成されている必要があります。または、テストが失敗します。 オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

