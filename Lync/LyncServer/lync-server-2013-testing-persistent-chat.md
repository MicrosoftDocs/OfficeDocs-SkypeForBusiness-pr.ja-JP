---
title: 'Lync Server 2013: 常設チャットのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee9869d5e7a5e3a48451478de334ee656543f6f5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a>Lync Server 2013 での常設チャットのテスト

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合は、 <strong>test-cspersistentchatmessage</strong>コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

**Test-cspersistentchatmessage**コマンドレットでは、テストユーザーのペアが常設チャットサービスを使用してメッセージを交換できることを確認します。 これを行うために、コマンドレットは、Lync Server 2013 に2人のユーザーを記録し、ユーザーを常設チャットルームに接続し、メッセージのペアを交換して、チャットルームを終了し、2人のユーザーをログオフします。 ただし、チャットルームを作成していない場合や、2つのテストユーザーアカウントに常設チャットサービスへのアクセスを許可する常設チャットポリシーが割り当てられていない場合は、このコマンドレットの呼び出しは失敗します。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

次の例に示すコマンドは、ユーザーのペア (litwareinc\\pilar と litwareinc\\Kenmyer) が Lync Server 2013 にログオンし、常設チャットサービスを使用してメッセージを交換できるかどうかをテストします。 これを行うには、例の最初のコマンドは、**資格情報**コマンドレットを使用して、User Pilar Ackerman の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成します。 (ログオン名 litwareinc\\pilar がパラメーターとして含まれているため、[Windows PowerShell 資格情報の要求] ダイアログボックスでは、管理者のみが Pilar Ackerman アカウントのパスワードを入力する必要があります)。その後、結果の資格情報オブジェクトは $cred 1 という名前の変数に格納されます。 2番目のコマンドは同じことを行いますが、今度は Ken Myer アカウントの credential オブジェクトを返します。

資格情報オブジェクトが手元にある場合、3番目のコマンドは、これら2人のユーザーが Lync Server 2013 にログオンして、常設チャットを使用して exchange メッセージにログオンできるかどうかを判断します。 このタスクを実行するには、次のパラメーターを使用して**test-cspersistentchatmessage**コマンドレットを呼び出します。 targetfqdn (レジストラープールの FQDN)。SenderSipAddress (最初のテストユーザーの SIP アドレス)。SenderCredential (同じユーザーの資格情報を含む Windows PowerShell オブジェクト)。ReceiverSipAddress (他のテストユーザーの SIP アドレス)。と ReceiverCredential (他のテストユーザーの資格情報を含む Windows PowerShell オブジェクト)。

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

指定したユーザーに有効な場所ポリシーがある場合は、次のような出力が得られ、Result プロパティは**Success**としてマークされます。

ターゲット Fqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間: 00:00:00

エラーメッセージ:

分析

指定したユーザーが常設チャットサービスを使用してメッセージを交換できない場合は、結果**がエラーとして**表示され、追加情報が Error および診断プロパティに記録されます。

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

2001年に\[応答できませんでした: 4898: e8: f39e: 5c9a: ad83:\]81b3: 9944: 5061

内部例外: 接続の試行が失敗しました。

接続されたパーティは、一定期間の後に正しく応答しませんでした

接続されているホストが原因で、接続に失敗しました。

応答に失敗した

\[2001年: 4898: e8: f39e: 5c9a: ad83: 81b3:\]9944: 5061

分析

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

**Test-cspersistentchatmessage**が失敗する可能性のある一般的な原因を次に示します。

  - 指定されたパラメーター値が正しくありません。 必要なテストアカウントが存在しないか、正しく作成されている可能性があります。

  - ネットワークの問題が原因で、テストのタイムアウトによる予期しない遅延が発生している可能性があります。

</div>

<div>

## <a name="see-also"></a>関連項目


[Get-cspersistentchatpolicy 戻し](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[Get-cspersistentchatpolicy 戻し](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[Get-cspersistentchatpolicy 戻し](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

