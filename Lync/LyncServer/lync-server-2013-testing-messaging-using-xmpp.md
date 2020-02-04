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
ms.openlocfilehash: d5a1840e344ee19114cca424822fa1df14028495
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a>Lync Server 2013 での XMPP を使ったメッセージングのテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-11-03_


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
<td><p>Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</p>
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、 <strong>CsXmppIM</strong>コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

拡張メッセージングとプレゼンスプロトコル (XMPP) は、インターネット経由でメッセージを送信するために使用される標準の通信プロトコル (XML に基づく) です。 XMPP は元々 Jabber という名称でしたが、いくつかのインターネットメッセージングやコミュニケーションアプリケーション (Google 通話、Facebook チャットなど) でサポートされています。 **テスト用の CsXmppIM**コマンドレットは、ユーザーが xmpp ネットワーク上のユーザーとインスタントメッセージをやり取りできることを確認します。 このテストを成功させるには、XMPP ユーザーの有効な SIP アドレスが必要であり、その SIP アドレスが許可されている XMPP パートナーとして構成されたネットワーク上にある必要があることに注意してください。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

次の例では、pool atl-cs-001.litwareinc.com の XMPP インスタントメッセージング機能を確認します。 このコマンドは、プール atl-cs-001.litwareinc.com に対してテストユーザーが定義されている場合にのみ機能します。 その場合、コマンドは、SIP アドレスが adelaney@contoso.com のユーザーに XMPP のインスタントメッセージを送信するかどうかを決定します。

テストユーザーが定義されていない場合は、どのユーザーとしてログオンするかがわからないため、コマンドは失敗します。 プールのテストユーザーを定義していない場合は、UserSipAddress パラメーターと、ログオンしようとしてコマンドで使用する必要があるユーザーの資格情報を含める必要があります。

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

次の例に示すコマンドは、特定のユーザー (litwareinc\\pilar) がログオンして、ユーザー adelaney@contoso.com に xmpp インスタントメッセージを送信する機能をテストします。 これを行うには、この例の最初のコマンドでは、Credential コマンドレットを使用して、user Pilar Ackerman の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成します。 (Logon name litwareinc\\pilar がパラメーターとして含まれているため、Windows PowerShell 資格情報の要求ダイアログボックスでは、管理者が Pilar Ackerman アカウントのパスワードを入力する必要があります)。結果として得られた資格情報オブジェクトは、$cred 1 という名前の変数に格納されます。

2番目のコマンドは、このユーザーがプール atl-cs-001.litwareinc.com にログオンして XMPP インスタントメッセージを送信できるかどうかを確認します。 このタスクを実行するために、次の4つのパラメーター (レジストラープールの FQDN) と共に、 **Test-CsXmppIm**コマンドレットが呼び出されます。受け手 (メッセージの宛先となっているユーザの SIP アドレス)。UserCredential (Pilar Ackerman のユーザー資格情報を格納する Windows PowerShell オブジェクト)UserSipAddress (提供されているユーザー資格情報に対応する SIP アドレス) を選びます。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

XMPP のインスタントメッセージングが正しく構成されている場合は、次のような出力が表示され、Result プロパティは Success とマークされ**ます。**

ターゲット Fqdn: atl-cs-001.litwareinc.com

結果: 成功

待ち時間:00:00: 02.5361946

エラーメッセージ:

診断

指定したユーザーが XMPP のインスタントメッセージングを使用できない場合は、結果**がエラーとして**表示され、エラーと診断のプロパティに追加情報が記録されます。

警告: 指定した完全修飾のレジストラーポート番号の読み取りに失敗しました

ドメイン名 (FQDN)。 既定のレジストラーポート番号を使用します。 エラー

InvalidOperationException: トポロジで一致するクラスターが見つかりませんでした。

自宅

SipSyntheticTransaction-TryRetri の同期を行います。

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

ターゲット Fqdn: atl-cs-001.litwareinc.com

結果: エラー

待ち時間: 00:00:00

エラーメッセージ: 10060、接続されているパーティのため、接続に失敗しました

一定の期間が経過した後に正しく応答しなかった場合、または

接続されているホストに、接続に失敗しました

10.188.116.96 に応答できませんでした: 5061

内部例外: 接続の試行が失敗したため、接続できませんでした。

しばらくしても、接続されているパーティが正しく応答しませんでした

接続されているホストが原因で、時刻、または接続に失敗しました

さんが10.188.116.96 に応答できませんでした: 5061

診断

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に **、テスト用の CsXmppIM**が失敗する一般的な理由をいくつか示します。

  - 指定されたパラメーター値が正しくありません。 使用する場合は、オプションのパラメーターが正しく構成されている必要があります。または、テストが失敗します。 省略可能なパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。

  - XMPP ゲートウェイの構成が正しく設定されていないか、まだ展開されていない場合、このコマンドは失敗します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Set-CsXmppGatewayConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

