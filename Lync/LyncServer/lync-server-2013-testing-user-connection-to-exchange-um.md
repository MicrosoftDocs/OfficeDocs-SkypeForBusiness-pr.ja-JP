---
title: 'Lync Server 2013: Exchange UM へのユーザー接続のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87b6fd59ed0efb3a775017af1effd7bd022071fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503874"
---
# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a>Lync Server 2013 での Exchange UM へのユーザー接続のテスト

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-11-01_


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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、 <strong>Test-CsExUMConnectivity</strong> コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

**Test-CsExUMConnectivity**コマンドレットは、指定されたユーザーが Microsoft Exchange Server 2013 ユニファイドメッセージングサービスに接続できることを確認します。 このコマンドレットでは、サービスに接続できることを確認するだけであることに注意してください。 サービス自体はテストされません。 ユニファイドメッセージングサービス (ユーザーのメールボックスにボイスメールメッセージを実際に残している代理トランザクションコマンドレットを実行する) をテストするには、Test-CsExUMVoiceMail コマンドレットを使用します。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

次の例では、プール atl-cs-001.litwareinc.com の Exchange ユニファイドメッセージング接続をテストします。 このコマンドは、atl-cs-001.litwareinc.com プールに対してテストユーザーが定義されている場合にのみ機能します。 その場合は、コマンドによって、最初のテストユーザーがユニファイドメッセージングに接続できるかどうかが判断されます。 プールに対してテストユーザーが構成されていない場合、コマンドは失敗します。

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

次の例に示すコマンドは、ユーザー litwareinc kenmyer の Exchange ユニファイドメッセージング接続をテストし \\ ます。 これを行うには、この例の最初のコマンド **は、litwareinc コマンドレットを** 使用して、user Kenmyer の Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成し \\ ます。 有効な資格情報オブジェクトを作成するには、このアカウントのパスワードを指定する必要があり、 **テスト CsExUMConnectivity** コマンドレットでチェックを実行できることに注意してください。

この例の2番目のコマンドでは、指定された credentials オブジェクト ($x) とユーザー litwareinc kenmyer の SIP アドレスを使用して、 \\ このユーザーが Exchange ユニファイドメッセージングに接続できるかどうかを判断します。

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

次の例に示すコマンドは、表示されているコマンドのバリエーションです。 この例では、OutLoggerVariable パラメーターが含まれています。このパラメーターは、 **テスト用** に作成されたすべてのステップの詳細ログを生成するためのもので、これらの各ステップの成功または失敗を生成します。 これを行うには、OutLoggerVariable パラメーターをパラメーター値 ExumText と共に追加します。これにより、詳細なログ情報が $ExumTest という名前の変数に格納されます。 この例の最後のコマンドでは、ToXML () メソッドを使用して、ログ情報を XML 形式に変換します。 その XML データは、 \\ \\ Out-File コマンドレットを使用して、C: LogsExumTest.xml という名前のファイルに書き込まれます。

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

Exchange の統合が正しく構成されている場合は、次のような出力が得られ、Result プロパティは **Success**としてマークされます。

ターゲット Fqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間: 00:00:00

エラーメッセージ:

分析

指定したユーザーが通知を受信できない場合は、結果 **がエラーとして**表示され、追加情報が Error および診断プロパティに記録されます。

ターゲット Fqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間: 00:00:00

エラーメッセージ: 10060。接続しているパーティが原因で接続に失敗しました。

一定期間後に正しく応答しなかったか、または

接続されたホストの接続に失敗しました。

10.188.116.96: 5061 に応答できませんでした

内部例外: 接続の試行が失敗しました。

接続されたパーティは、一定期間の後に正しく応答しませんでした

接続されているホストが原因で、接続に失敗しました。

10.188.116.96: 5061 に応答できませんでした

分析

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

**テスト-CsExUMConnectivity**が失敗する主な理由を次に示します。

  - 指定されたパラメーター値が正しくありません。 省略可能なパラメーターが使用されている場合、オプションのパラメーターが正しく構成されている必要があります。テストは失敗します。 オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。

  - Exchange サーバーが正しく構成されていないか、まだ展開されていない場合、このコマンドは失敗します。

  - Exchange サーバーがネットワークを介して到達できない場合、このコマンドは失敗します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

