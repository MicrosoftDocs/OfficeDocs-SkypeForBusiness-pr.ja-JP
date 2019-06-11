---
title: 'Lync Server 2013: 常設チャットのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4f805984382388fd44904db746d818decb8871a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a>Lync Server 2013 での常設チャットのテスト

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
<p>Windows PowerShell のリモートインスタンスを使って実行する場合は、 <strong>CsPersistentChatMessage</strong>コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

**CsPersistentChatMessage**コマンドレットは、1組のテストユーザーが常設チャットサービスを使ってメッセージを交換できることを確認します。 これを行うには、コマンドレットは2人のユーザーを Lync Server 2013 に記録し、ユーザーを永続的なチャットルームに接続して、1組のメッセージを交換し、チャットルームを終了して2人のユーザーをログオフします。 チャットルームを作成していない場合、または2つのテストユーザーアカウントに常設チャットサービスへのアクセスを提供する常設チャットポリシーが割り当てられていない場合は、このコマンドレットの呼び出しは失敗します。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

次の例に示すコマンドは、一対のユーザー (litwareinc\\pilar と litwareinc\\Kenmyer) が Lync Server 2013 にログオンして、常設チャットサービスを使ってメッセージを交換する機能をテストします。 これを行うには、この例の最初のコマンドでは、 **Credential**コマンドレットを使用して、User Pilar Ackerman の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成します。 (Logon name、litwareinc\\pilar はパラメーターとして指定されているため、Windows PowerShell 資格情報の要求ダイアログボックスでは、管理者は Pilar Ackerman アカウントのパスワードを入力する必要があります)。結果として得られた資格情報オブジェクトは、$cred 1 という名前の変数に格納されます。 2番目のコマンドでも同じことが実行されますが、今回は Ken Myer アカウントの credential オブジェクトを返します。

資格情報オブジェクトが手元にある場合、3番目のコマンドは、これら2人のユーザーが Lync Server 2013 にログオンして、常設チャットを使ってメッセージを交換できるかどうかを決定します。 この処理を実行するには、 **CsPersistentChatMessage**コマンドレットは、次のパラメーターを使用して呼び出されます。 Targetfqdn (レジストラープールの FQDN)SenderSipAddress (最初のテストユーザーの SIP アドレス)SenderCredential (同じユーザーの資格情報を格納する Windows PowerShell オブジェクト)ReceiverSipAddress (他のテストユーザーの SIP アドレス)と ReceiverCredential (他のテストユーザーの資格情報を格納する Windows PowerShell オブジェクト)。

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

指定したユーザーが有効な場所のポリシーを持っている場合は、次のような結果が返され、Result プロパティは**Success**とマークされます。

ターゲット Fqdn: atl-cs-001.litwareinc.com

結果: 成功

待ち時間: 00:00:00

エラーメッセージ:

診断

指定したユーザーが常設チャットサービスを使用してメッセージを交換できない場合、 **** 結果はエラーとして表示され、その他の情報はエラーと診断のプロパティに記録されます。

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

2001: 4898 \[: f39e: 5c9a: ad83: 81b3: 9944\]: 5061 を応答できませんでした。

内部例外: 接続の試行が失敗したため、接続できませんでした。

しばらくしても、接続されているパーティが正しく応答しませんでした

接続されているホストが原因で、時刻、または接続に失敗しました

が応答しませんでした

\[2001: 4898: f39e: 5c9a: ad83: 81b3: 9944\]: 5061

診断

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に **、テスト-CsPersistentChatMessage**が失敗する可能性がある一般的な理由を示します。

  - 指定されたパラメーター値が正しくありません。 必須のテストアカウントが存在しないか、正しく作成されている可能性があります。

  - ネットワークの問題が原因で、予期しないテストの遅延が発生している可能性があります。

</div>

<div>

## <a name="see-also"></a>関連項目


[Grant-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[New-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[Set-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

