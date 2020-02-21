---
title: 'Lync Server 2013: PSTN 通話のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7c9c0b0441ea31e2419101aba188c33b0bbfd70
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-in-lync-server-2013"></a>Lync Server 2013 での PSTN 通話のテスト

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テスト用の登録コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Test-CsPstnOutboundCall コマンドレットは、ユーザーが PSTN にある電話番号に電話をかけることができるかどうかをテストします。 テスト-CsPstnOutboundCall を実行すると、コマンドレットはまず、テストユーザーを Lync Server にログインしようとします。 ログオンに成功すると、コマンドレットは PSTN ゲートウェイを経由して電話をかけることになります。 この通話は、ダイヤルプラン、音声ポリシー、およびテストアカウントに割り当てられたその他のポリシーと設定を使用して行われます。 呼び出しに応答すると、コマンドレットはネットワーク経由でデュアルトーン多重周波数 (DTMF) コードを送信して、メディア接続を確認します。

テストを実行するときは、テスト-CsPstnOutboundCall が実際の電話を発信します。対象の電話は着信し、テストが成功するには応答する必要があります。 この呼び出しは、管理者が手動で終了する必要もあります。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

テスト-CsPstnOutboundCall コマンドレットは、事前構成されたテストアカウント (「Lync Server テストを実行するためのテストアカウントの設定」を参照)、または Lync Server が有効になっているユーザーのアカウントのいずれかを使用して実行できます。 このチェックをテストアカウントを使用して実行するには、テスト対象の Lync Server プールの FQDN と、着信される PSTN 電話番号を指定する必要があります。 次に例を示します。

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

実際のユーザーアカウントを使用してこのチェックを実行するには、まず、アカウント名とパスワードを含む Windows PowerShell credentials オブジェクトを作成する必要があります。 次に、その資格情報オブジェクトと、テスト-CsPstnOutboundCall を呼び出すときにアカウントに割り当てられた SIP アドレスを含める必要があります。

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

詳細については、「 [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

指定したユーザーが通話を行うことができ、応答がある場合は次のような出力が返され、Result プロパティは Success とマークされ**ます。**

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間:00:00: 06.8630376

エラー

分析

指定したユーザーが通話を行うことができない場合、または通話に応答がない場合、結果は失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間: 00:00:0987365

エラー: 403、禁止

診断: エラーコード = 12001、ソース = litwareinc、理由 = [ユーザー]

ポリシーには電話ルートの使用法は含まれていません

指定したユーザーに割り当てられている音声ポリシーに電話の使用法が含まれていないため、テストが失敗したことが前の出力に示されています。 (電話使用法は音声ポリシーを音声ルートに関連付けます。 音声ポリシーと対応する音声ルートの両方を使用しない場合、PSTN を介して通話を行うことはできません。

テスト-CsPstnOutboundCall に失敗した場合は、次のように詳細なパラメーターを含めて、テストを再実行することをお勧めします。

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

Verbose パラメーターが含まれている場合、テスト-CsPstnOutboundCall は、指定されたユーザーが Lync Server にログオンできるかどうかを確認したときに試行された各アクションのステップバイステップのアカウントを返します。 たとえば、次の出力は、ネットワークの問題によって PSTN との接続が妨げられていることを示しています。

音声ビデオ通話を ' sip: + 12065551219@litwareinc .com; ユーザー = 電話 ' に設定します。

例外 ' A 404 (見つかりません) 応答がネットワークから受信され、操作に失敗しました。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

テスト-CsPstnOutboundCall が失敗する主な理由を次に示します。

  - 無効なユーザーアカウントが指定されています。 ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。 ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが Lync Server に対して有効になっていないことを意味します。

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

