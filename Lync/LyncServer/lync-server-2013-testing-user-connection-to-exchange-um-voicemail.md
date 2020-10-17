---
title: 'Lync Server 2013: Exchange UM ボイスメールへのユーザー接続のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM voicemail
ms:assetid: 574da104-8823-4061-9fb6-353639f1884d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727305(v=OCS.15)
ms:contentKeyID: 63969604
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4812f36d19f9645f926eb1aa4f017d70befa47a7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503894"
---
# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a>Lync Server 2013 での Exchange UM ボイスメールへのユーザー接続のテスト

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合は、 <strong>テスト-CsExUMVoiceMail メール</strong> コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

**Test-CsExUMVoiceMail**コマンドレットを使用すると、管理者はユーザーが Microsoft Exchange Server 2013 ユニファイドメッセージングサービスにアクセスして使用できることを確認できます。 このために、コマンドレットはユニファイド メッセージング サービスに接続し、指定されたメールボックスにボイス メールを残します。 このボイス メールは、システムが提供するボイス メールか、自分自身で録音したカスタムの .WAV ファイルです。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

次の例では、プール atl-cs-001.litwareinc.com の Exchange ユニファイドメッセージングボイスメール接続をテストします。 このコマンドは、atl-cs-001.litwareinc.com プールに対してテストユーザーが定義されている場合にのみ機能します。 その場合は、コマンドによって、最初のテストユーザーがユニファイドメッセージングボイスメールを使用できるかどうかが判断されます。 プールに対してテストユーザーが構成されていない場合、コマンドは失敗します。

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

次の例に示すコマンドは、ユーザー litwareinc kenmyer の Exchange ユニファイドメッセージングボイスメール接続をテストし \\ ます。 これを行うには、この例の最初のコマンド **は、litwareinc コマンドレットを** 使用して、user Kenmyer の Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成し \\ ます。 有効な資格情報オブジェクトを作成するには、このアカウントのパスワードを指定する必要があります。また、 **Test-CsExUMVoiceMail メール** コマンドレットでチェックを実行できることに注意してください。

この例の2番目のコマンドでは、指定された credentials オブジェクト ($x) とユーザー litwareinc kenmyer の SIP アドレスを使用して、 \\ このユーザーが Exchange ユニファイドメッセージングボイスメールに接続できるかどうかを判断します。

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

次の例に示すコマンドは、例1に示すコマンドのバリエーションです。この例では、OutLoggerVariable パラメーターが含まれています。このパラメーターは、 **テスト-CsExUMVoiceMail メール** レットによって実行されたすべてのステップの詳細ログを生成し、それらの各ステップの成功または失敗を生成します。 これを行うには、パラメーター値 ExumText の横に OutLoggerVariable パラメーターを追加します。これにより、詳細なログ情報が $ExumTest という名前の変数に格納されます。 この例の最後のコマンドでは、ToXML () メソッドを使用して、ログ情報を XML 形式に変換します。 その XML データは、 \\ \\ Out-File コマンドレットを使用して、C: LogsVoicemailTest.xml という名前のファイルに書き込まれます。

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

Exchange の統合が正しく構成されている場合は、次のような出力が得られ、Result プロパティは **Success**としてマークされます。

ターゲット Fqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間:00:00: 02.9911345

エラーメッセージ:

分析

指定したユーザーがボイスメールに接続できない場合、結果は **失敗**として表示され、エラーと診断のプロパティに追加情報が記録されます。

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

**テスト-CsExUMVoiceMail メール**が失敗する原因となる一般的な理由を次に示します。

  - 指定されたパラメーター値が正しくありません。 省略可能なパラメーターが使用されている場合、オプションのパラメーターが正しく構成されている必要があります。テストは失敗します。 オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。

  - Exchange サーバーが正しく構成されていないか、まだ展開されていない場合、このコマンドは失敗します。

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

