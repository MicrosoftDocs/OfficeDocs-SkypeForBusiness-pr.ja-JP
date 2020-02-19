---
title: 'Lync Server 2013: XMPP を使用したメッセージングのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3ee4dc939ae0fbc1e62c30bb7dd431d3d940f6c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a>Lync Server 2013 での XMPP を使用したメッセージングのテスト

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、 <strong>Test-CsXmppIM</strong>コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

XMPP (Extensible Messaging and Presence Protocol) は、インターネットでメッセージを送信するための標準通信プロトコル (XML ベース) です。 XMPP は元々 Jabber という名前でしたが、Google Talk や Facebook のチャットなど、いくつかのインターネットメッセージングおよびコミュニケーションアプリケーションでサポートされています。 **Test-CsXmppIM**コマンドレットは、ユーザーが xmpp ネットワーク上のユーザーとインスタントメッセージを交換できることを確認します。 このテストが成功するには、XMPP ユーザーの有効な SIP アドレスを持ち、その SIP アドレスが許可された XMPP パートナーとして構成されたネットワーク上にある必要があることに注意してください。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

次の例では、プール atl-cs-001.litwareinc.com の XMPP インスタントメッセージング機能を確認します。 このコマンドは、プール atl-cs-001.litwareinc.com に対してテストユーザーが定義されている場合にのみ機能します。 その場合は、コマンドによって、最初のテストユーザーが SIP アドレス adelaney@contoso.com を持つユーザーに XMPP インスタントメッセージを送信できるかどうかが判断されます。

テストユーザーが定義されていない場合は、どのユーザーがどのユーザーとしてログオンするかがわからないため、コマンドは失敗します。 プールに対してテストユーザーが定義されていない場合は、UserSipAddress パラメーターと、そのコマンドがログオンを試行するときに使用するユーザーの資格情報を含める必要があります。

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

次の例に示すコマンドは、特定のユーザー (litwareinc\\pilar) がログオンして、ユーザー adelaney@contoso.com に xmpp インスタントメッセージを送信する機能をテストします。 これを行うには、例の最初のコマンドは、資格情報コマンドレットを使用して、user Pilar Ackerman の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成します。 (ログオン名 litwareinc\\pilar がパラメーターとして含まれているため、Windows PowerShell の資格情報の要求] ダイアログボックスでは、管理者のみが Pilar Ackerman アカウントのパスワードを入力する必要があります。)その後、結果として得られる資格情報オブジェクトは $cred 1 という名前の変数に格納されます。

2番目のコマンドは、このユーザーがプール atl-cs-001.litwareinc.com にログオンして XMPP インスタントメッセージを送信できるかどうかをチェックします。 このタスクを実行するには、次の4つのパラメーターと共に、 **Test-CsXmppIm**コマンドレットを呼び出します。 targetfqdn (レジストラープールの FQDN)。受信者 (メッセージの宛先のユーザーの SIP アドレス)。UserCredential (Pilar Ackerman のユーザー資格情報を含む Windows PowerShell オブジェクト)。UserSipAddress (指定されたユーザー資格情報に対応する SIP アドレス)。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

XMPP instant messaging が正しく構成されている場合は、次のような出力が得られ、Result プロパティは Success としてマークされ**ます。**

ターゲット Fqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間:00:00: 02.5361946

エラーメッセージ:

分析

指定されたユーザーが XMPP instant messaging を使用できない場合、結果は**失敗**として表示され、エラーと診断のプロパティに次のような追加情報が記録されます。

警告: 指定された完全修飾のレジストラーポート番号を読み取ることができませんでした

ドメイン名 (FQDN)。 既定のレジストラーポート番号を使用します。 例外

System.invalidoperationexception: トポロジ内に一致するクラスターが見つかりませんでした。

下部

TryRetri を SipSyntheticTransaction していることを示します。

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

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

次に **、Test-CsXmppIM**が失敗する可能性がある一般的な理由を示します。

  - 指定されたパラメーター値が正しくありません。 省略可能なパラメーターが使用されている場合、オプションのパラメーターが正しく構成されている必要があります。テストは失敗します。 オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。

  - XMPP ゲートウェイの構成が正しく構成されていないか、まだ展開されていない場合、このコマンドは失敗します。

</div>

<div>

## <a name="see-also"></a>関連項目


[-CsXmppGatewayConfiguration の設定](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

