---
title: 'Lync Server 2013: PSTN ピアからピアへの通話のテスト'
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
ms.openlocfilehash: 33aa0447c90ea9c76a1956cb817f0e61ce0d626e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504044"
---
# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a>Lync Server 2013 での PSTN ピアツーピア通話のテスト

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsPstnPeerToPeerCall コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Test-CsPstnPeerToPeerCall コマンドレットは、ユーザーのペアが公衆交換電話網 (PSTN) ゲートウェイ経由でピアツーピア通話を行うことができるかどうかを検証します。 テスト-CsPstnPeerToPeerCall を呼び出すと、コマンドレットは最初に2つのテストユーザーを Lync Server にログオンしようとします。 ログオンが成功した場合、コマンドレットはユーザー1に PSTN ゲートウェイ経由のユーザー2の呼び出しを試行します。 Test-CsPstnPeerToPeerCall は、ダイヤルプラン、音声ポリシー、およびテストユーザーに割り当てられたその他のポリシーと構成設定を使用してこの呼び出しを行います。 テストが計画どおりに行われた場合、コマンドレットは、ユーザー2が通話に応答できたことを確認してから、両方のテストアカウントをシステムからログオフします。

Test-CsPstnPeerToPeerCall は、接続を確立できるかどうかを確認し、ネットワーク上で DTMF コードを送信して、接続を介してメディアを送信できるかどうかを判断するために、実際の電話を行います。 この呼び出しはコマンドレット自体によって応答され、呼び出しを手動で終了する必要はありません。 (つまり、電話をかけて通話を停止する必要はありません)。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Test-CsPstnPeerToPeerCall コマンドレットを実行するには、事前に構成された一連のテストアカウントを使用します (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照してください)。または、Lync Server が有効になっている2人のユーザーのアカウント。 このチェックをテストアカウントを使用して実行するには、テストする Lync Server プールの FQDN を指定するだけで済みます。 以下に例を示します。

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

実際のユーザーアカウントを使用してこのチェックを実行するには、2つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。 次に、テスト-CsPstnPeerToPeerCall を呼び出すときに、これらの資格情報オブジェクトと2つのアカウントの SIP アドレスを含める必要があります。

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

詳細については、「 [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

指定したユーザーがピアツーピア呼び出しを完了できる場合は、次のような出力が得られます。 Result プロパティは Success としてマークされてい **ます。**

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間:00:00: 06.8630376

エラー

分析

指定したユーザーがピアツーピア呼び出しを完了できなかった場合、結果は失敗として表示され、次の情報が Error および診断プロパティに記録されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間: 00:00:0182361

エラー: 403、禁止

診断: ErrorCode = 12001, Source = 001.litwareinc.com,

理由 = ユーザーポリシーに電話ルートの使用が含まれていません

指定したユーザーの少なくとも1人に割り当てられた音声ポリシーに電話の使用法が含まれていないためにテストが失敗したことを、上記の出力に記載しています。 (電話使用法は音声ポリシーを音声ルートに関連付けます。 音声ポリシーとそれに対応する音声ルートの両方を使用しない場合、PSTN を介して通話を行うことはできません。

Test-CsPstnPeerToPeerCall が失敗した場合は、次のようにして、Verbose パラメーターを含むテストを再実行することをお勧めします。

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose パラメーターが含まれている場合、Test-CsPstnPeerToPeerCall は、指定されたユーザーが Lync Server にログオンできるかどうかを確認したときに実行された各アクションのステップバイステップのアカウントを返します。 たとえば、次の出力は、ネットワークの問題によって PSTN との接続が妨げられていることを示しています。

音声ビデオ通話を ' sip: + 12065551219@litwareinc .com; ユーザー = 電話 ' に設定します。

例外 ' A 404 (見つかりません) 応答がネットワークから受信され、操作に失敗しました。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

Test-CsPstnPeerToPeerCall が失敗する可能性のある一般的な理由を次に示します。

  - 無効なユーザーアカウントが指定されました。 ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。 ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server に対して有効になっていないことを意味します。

  - 指定したユーザーに割り当てられている音声ポリシーに、有効な PSTN 使用法がありません。 次のようなコマンドを使用して、ユーザーに割り当てられている音声ポリシーを判別できます。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    その後、次のようなコマンドを使用して、そのポリシーに割り当てられている PSTN 使用法 (ある場合) を判別できます。これは、ユーザー単位の音声ポリシー RedmondVoicePolicy に関する情報を取得します。
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

