---
title: 'Lync Server 2013: PSTN 通話のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 641b2f77079fee100d8f3ac85a1a7580d7cf7d84
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-in-lync-server-2013"></a>Lync Server 2013 での PSTN 通話のテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-06-05_


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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、CsRegistration コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

テスト-CsPstnOutboundCall コマンドレットを使って、ユーザーが PSTN 上にある電話番号に通話を発信できるかどうかをテストします。 テスト-CsPstnOutboundCall を実行するときに、コマンドレットはまずテストユーザーを Lync Server にログオンしようとします。 ログオンが成功すると、コマンドレットは PSTN ゲートウェイ間で電話をかけようとします。 この電話番号は、ダイヤルプラン、ボイスポリシー、テストアカウントに割り当てられたその他のポリシーと設定を使って発信されます。 通話に応答すると、コマンドレットはネットワーク経由でデュアルトーンマルチ周波数 (DTMF) コードを送信して、メディアの接続性を確認します。

テスト-CsPstnOutboundCall を実行すると、実際の電話がかけられます。ターゲットの電話が呼び出され、テストが成功するために応答する必要があります。 この通話は、管理者が手動で終了する必要もあります。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

テスト-CsPstnOutboundCall コマンドレットは、事前に定義されたテストアカウント (「Lync Server テストを実行するためのテストアカウントのセットアップ」をご覧ください)、または Lync Server を有効にしているユーザーのアカウントを使って実行できます。 テストアカウントを使用してこのチェックを実行するには、テスト対象の Lync Server プールの FQDN と、着信する PSTN 電話番号を指定する必要があります。 次に例を示します。

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

実際のユーザーアカウントを使用してこのチェックを実行するには、最初に、アカウント名とパスワードを含む Windows PowerShell 資格情報オブジェクトを作成する必要があります。 次に、資格情報オブジェクトと、テスト (CsPstnOutboundCall) を呼び出すときにアカウントに割り当てられた SIP アドレスを指定する必要があります。

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

詳細については、「[テスト-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) 」コマンドレットのヘルプドキュメントを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

指定したユーザーが通話を発信できる場合は、通話に応答すると、次のような結果が返されます。これには、Result プロパティが Success とマークされてい**ます。**

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待ち時間:00:00: 06.8630376

誤差

診断

指定したユーザーが通話を発信できない場合、または通話に応答しない場合は、結果が失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待ち時間: 00:00:0987365

エラー: 403、許可されていません

診断: ErrorCode = 12001、Source = atl-litwareinc、Reason = User:

ポリシーには電話ルートの使用が含まれない

指定したユーザーに割り当てられている音声ポリシーに電話の使用が含まれていないため、テストが失敗したことが示されます。 (電話の使用状況によりボイスポリシーを音声ルートに関連付けます。 ボイスポリシーと、対応する音声ルートの両方がないと、PSTN 経由で通話を発信することはできません。)

テスト-CsPstnOutboundCall 呼び出しが失敗した場合は、Verbose パラメーターなどのテストを再実行することをお勧めします。

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

Verbose パラメーターが含まれている場合、テスト-CsPstnOutboundCall は、指定されたユーザーが Lync Server にログオンする機能を確認したときに実行される各操作のステップバイステップのアカウントを返します。 たとえば、次の出力は、ネットワークの問題によって PSTN との接続が妨げられていることを示しています。

' Sip: +12065551219@litwareinc.com; user = phone ' への音声ビデオ通話を確立しています。

ネットワークから受信した例外 ' A 404 (見つからない) 応答は、操作に失敗しました。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

テスト-CsPstnOutboundCall 呼び出しが失敗する理由としては、次のようなものがあります。

  - 無効なユーザアカウントを指定しました。 次のようなコマンドを実行すると、ユーザーアカウントが存在するかどうかを確認できます。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。 Lync Server でユーザーアカウントが有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server を有効にしていないことを意味します。

  - 指定したユーザーに割り当てられている音声ポリシーに、有効な PSTN の使用状況がありません。 次のようなコマンドを使用して、ユーザーに割り当てられている音声ポリシーを確認できます。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    次のようなコマンドを使用して、そのポリシーに割り当てられている PSTN (存在する場合) を特定することができます。これにより、ユーザーごとの音声ポリシー RedmondVoicePolicy に関する情報を取得できます。
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

