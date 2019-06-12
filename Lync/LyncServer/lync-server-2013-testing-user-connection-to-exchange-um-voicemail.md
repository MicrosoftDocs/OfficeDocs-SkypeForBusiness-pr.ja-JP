---
title: 'Lync Server 2013: Exchange UM ボイスメールへのユーザー接続のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing user connection to Exchange UM voicemail
ms:assetid: 574da104-8823-4061-9fb6-353639f1884d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727305(v=OCS.15)
ms:contentKeyID: 63969604
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f09921d62eddb1f1b426e0e3b1fc4984a0987a8e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a>Lync Server 2013 での Exchange UM ボイスメールへのユーザー接続のテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-11-01_


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
<p>Windows PowerShell のリモートインスタンスを使って実行する場合は、<strong>テスト-CsExUMVoiceMail メール</strong>コマンドレットを実行する権限を持つ RBAC の役割をユーザーに割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

**テスト-CsExUMVoiceMail メール**コマンドレットを使用すると、管理者は、ユーザーが Microsoft Exchange Server 2013 ユニファイドメッセージングサービスにアクセスして使用できることを確認できます。 これを行うために、コマンドレットはユニファイドメッセージングサービスに接続し、指定されたメールボックスにボイスメールを残します。 これは、システムによって提供されるボイスメールの場合もあれば、カスタムの場合もあります。自分で録音した WAV ファイル。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

次の例では、プール atl-cs-001.litwareinc.com の Exchange ユニファイドメッセージングのボイスメール接続をテストします。 このコマンドは、テストユーザーがプール atl-cs-001.litwareinc.com に対して定義されている場合にのみ機能します。 その場合、コマンドは、最初のテストユーザーがユニファイドメッセージングボイスメールを使用できるかどうかを決定します。 プールのテストユーザーが構成されていない場合、コマンドは失敗します。

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

次の例に示すコマンドは、ユーザー litwareinc\\Kenmyer の Exchange ユニファイドメッセージングのボイスメール接続のテストです。 これを行うには、この例の最初のコマンドでは、 **Credential**コマンドレットを使って、user litwareinc\\kenmyer の Windows PowerShell コマンドラインインターフェイスの credentials オブジェクトを作成します。 このアカウントのパスワードを入力して、有効な資格情報オブジェクトを作成し、**テスト用の CsExUMVoiceMail メール**コマンドレットでチェックを実行できるようにする必要があることに注意してください。

この例の2番目のコマンドでは、指定された資格情報オブジェクト ($x) と\\ユーザー litwareinc KENMYER の SIP アドレスを使って、Exchange ユニファイドメッセージングボイスメールに接続できるかどうかを決定します。

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

次の例に示すコマンドは、例1に示すコマンドの変形です。この例では、OutLoggerVariable パラメーターが含まれており、**テスト-CsExUMVoiceMail メール**レットによって実行されたすべての手順の詳細なログを生成し、それらの各手順の成功または失敗を生成します。 これを行うには、パラメーター値 ExumText と共に OutLoggerVariable パラメーターを追加します。これにより、詳細なログ情報が $ExumTest という名前の変数に格納されます。 この例の最後のコマンドでは、ToXML () メソッドを使ってログ情報を XML 形式に変換しています。 その XML データは、\\\\VoicemailTest コマンドレットを使用して、C: という名前のファイルに書き込まれます。

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

Exchange の統合が適切に構成されている場合は、次のような結果が返され、Result プロパティは**Success**とマークされます。

ターゲット Fqdn: atl-cs-001.litwareinc.com

結果: 成功

待ち時間:00:00: 02.9911345

エラーメッセージ:

診断

指定したユーザーがボイスメールに接続できない場合、結果は**** エラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。

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

次に **、テスト-CsExUMVoiceMail メール**が失敗する理由をいくつか示します。

  - 指定されたパラメーター値が正しくありません。 使用する場合は、オプションのパラメーターが正しく構成されている必要があります。または、テストが失敗します。 省略可能なパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。

  - このコマンドは、Exchange サーバーが正しく構成されていないか、まだ展開されていない場合に失敗します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

