---
title: 'Lync Server 2013: PSTN ピアとピアの通話をテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f120747eb50e8c1c52bb14d0a8883db8133022c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a>Lync Server 2013 で PSTN ピアツーピア通話をテストする

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
<p>Windows PowerShell のリモートインスタンスを使って実行する場合は、テスト-CsPstnPeerToPeerCall コマンドレットを実行する権限を持つ RBAC の役割をユーザーに割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

テスト-CsPstnPeerToPeerCall コマンドレットを使って、ユーザーのペアが公衆交換電話網 (PSTN) ゲートウェイ経由でピアツーピア通話を実行することを許可しているかどうかを確認します。 テスト-CsPstnPeerToPeerCall を呼び出すと、コマンドレットは最初に2つのテストユーザーに Lync Server をログオンしようとします。 ログオンが成功したことを前提として、コマンドレットは、ユーザー1が PSTN ゲートウェイ経由でユーザー2に通話を試みていることを前提としています。 テスト-CsPstnPeerToPeerCall は、テストユーザに割り当てられているダイヤルプラン、ボイスポリシー、その他のポリシーと設定を使用して、この通話を行います。 テストが計画どおりに行われた場合、コマンドレットは、ユーザー2が通話に応答できることを確認した後、システムから両方のテストアカウントをログオフします。

テスト-CsPstnPeerToPeerCall は、接続を確立できることを確認する実際の電話を発信します。また、ネットワーク経由で DTMF コードを送信して、メディアを接続経由で送信できるかどうかを確認します。 この呼び出しはコマンドレット自体によって応答され、手動で通話を終了する必要はありません。 (つまり、通話に応答して電話を切る必要はありません)。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

テスト-CsPstnPeerToPeerCall コマンドレットは、定義済みのテストアカウントのペア (「Lync Server テストを実行するためのテストアカウントのセットアップ」をご覧ください)、または Lync Server を有効にしている2人のユーザーのアカウントを使って実行できます。 テストアカウントを使用してこの確認を実行するには、テストする Lync Server プールの FQDN を指定する必要があります。 次に例を示します。

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

実際のユーザーアカウントを使用してこのチェックを実行するには、2つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。 次に、テスト (CsPstnPeerToPeerCall) を呼び出す際に、これらの資格情報オブジェクトと2つのアカウントの SIP アドレスを含める必要があります。

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

詳細については、「[テスト-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) 」コマンドレットのヘルプドキュメントを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

指定したユーザーがピアツーピアの通話を完了できる場合は、次のような結果が返され、Result プロパティは Success とマークされ**ます。**

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待ち時間:00:00: 06.8630376

誤差

診断

指定したユーザーがピアツーピアの呼び出しを完了できなかった場合、結果は失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待ち時間: 00:00:0182361

エラー: 403、許可されていません

診断: ErrorCode = 12001、Source = atl-cs-001.litwareinc.com、

理由 = ユーザーポリシーに電話ルートの使用が含まれていません

前の出力では、指定されたユーザーの少なくとも1人に割り当てられているボイスポリシーに電話の使用が含まれていないため、テストが失敗したことが示されます。 (電話の使用状況によりボイスポリシーを音声ルートに関連付けます。 ボイスポリシーと、対応するボイスルートの両方がないと、PSTN 経由で通話を発信することはできません。)

テスト-CsPstnPeerToPeerCall が失敗した場合は、Verbose パラメーターも含めて、テストを再実行することをお勧めします。

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose パラメーターが含まれている場合、テスト-CsPstnPeerToPeerCall は、指定されたユーザーが Lync Server にログオンする機能をオンにしたときに実行された各操作のステップバイステップのアカウントを返します。 たとえば、次の出力は、ネットワークの問題によって PSTN との接続が妨げられていることを示しています。

' Sip: + 12065551219@litwareinc、ユーザー = 電話 ' への音声ビデオ通話を確立しています。

ネットワークから受信した例外 ' A 404 (見つからない) 応答は、操作に失敗しました。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

テスト-CsPstnPeerToPeerCall が失敗する一般的な理由を次に示します。

  - 無効なユーザーアカウントが指定されました。 次のようなコマンドを実行すると、ユーザーアカウントが存在するかどうかを確認できます。
    
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

