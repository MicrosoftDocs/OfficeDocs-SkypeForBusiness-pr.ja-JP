---
title: 'Lync Server 2013: 音声/ビデオ会議を検証する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89bb8f38ea650bf64179b917b227d7ccaaf10791
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a>Lync Server 2013 での音声/ビデオ会議の検証

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
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>確認のスケジュール</p></td>
<td><p>[毎日]</p></td>
</tr>
<tr class="odd">
<td><p>テストツール</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="even">
<td><p>必要なアクセス許可</p></td>
<td><p>Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</p>
<p>Windows PowerShell のリモートインスタンスを使って実行する場合、ユーザーには、テスト-CsAVConference コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

テスト-CsAVConference コマンドレットは、2つのテストユーザーが音声/ビデオ (A/V) 会議に参加できるかどうかを確認します。 コマンドレットが実行されると、2人のユーザーがシステムにログオンします。 ログオンが正常に完了したら、最初のユーザーは A/V 会議を作成し、2人目のユーザーがその会議に参加するのを待ちます。 データを簡単に交換した後、会議が削除され、2つのテストユーザーがログオフします。

ただし、テスト-CsAVConference では、2つのテストユーザー間で実際の A/V 会議が行われることに注意してください。 代わりに、このコマンドレットは、2人のユーザーが会議の開催に必要なすべての接続を確立できることを確認します。

このコマンドのその他の例については、「テスト用の[CsAVConference 会議](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)」を参照してください。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

テスト用の CsAVConference コマンドレットを実行するには、定義済みのテストアカウントのペア (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照) を使用するか、Lync Server を有効にしている2人のユーザーのアカウントを使用します。 テストアカウントを使用してこの確認を実行するには、テストする Lync Server プールの FQDN を指定する必要があります。 次に例を示します。

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

実際のユーザーアカウントを使用してこのチェックを実行するには、2つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。 次に、これらの資格情報オブジェクトと、テスト用 Cgi 会議を呼び出すときに2つのアカウントの SIP アドレスを含める必要があります。

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

詳細については、「[テスト-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

指定したユーザーが A/V 会議を正常に完了できた場合は、次のような結果が返され、Result プロパティは Success とマークされ**ます。**

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待ち時間:00:00: 02.6841765

誤差

診断

ユーザーが会議を完了できなかった場合は、結果がエラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待ち時間: 00:00:00

エラー: 404、見つかりません

診断: ErrorCode = 4005、Source = atl-cs-001.litwareinc.com、

理由 = ターゲット URI が SIP で有効になっていないか、

残っ.

DiagnosticHeader の場合

たとえば、前回の出力には、アカウントが存在しないか、アカウントが Lync Server に対して有効になっていないために、2つ以上のユーザーアカウントが無効であったためにテストが失敗したことが示されます。 次のようなコマンドを実行することにより、2つのテストアカウントが存在するかどうか、および Lync Server 用に有効になっているかどうかを確認できます。

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

テスト用の CsAVConference に失敗した場合は、Verbose パラメーターも含めて、テストを再実行することをお勧めします。

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose パラメーターが含まれている場合は、指定したユーザーが AV 会議に参加できるかどうかを確認したときに実行される各操作のステップバイステップのアカウントが返されます。 たとえば、テストが失敗し、次のような診断が表示されたとします。

ErrorCode = 1008、Source = accessproxy、Reason = DNS SRV レコードを解決できませんでした

Verbose パラメーターを使用してテストを再実行する場合、返される手順ごとの情報には、次のような出力が含まれます。

VERBOSE: ' Register ' アクティビティが開始されました。

登録リクエストの送信:

ターゲット Fqdn = atl-cs-001.litwareinc.com

ユーザー Sip アドレス = sip:davidlongmire@litwareinc.com

レジストラーポート = 5061。

[Authentication Type ' Trusted '] が選択されています。

' Register ' アクティビティが開始されました。

登録リクエストの送信:

ターゲット Fqdn = atl-cs-001.litwareinc.com

ユーザー Sip アドレス = sip:kenmyer@litwareinc.com

レジストラーポート = 5061。

[Authentication Type ' Trusted '] が選択されています。

"エンドポイントを登録できませんでした。" という例外が発生します。 具体的な理由については、「エラーコード」をご覧ください。 ワークフローの実行中に発生

この出力の最後の行は、ユーザー sip:kenmyer@litwareinc.com が Lync Server に登録できなかったことを示します。 つまり、SIP アドレス sip:kenmyer@litwareinc.com が有効であること、および関連付けられたユーザーが Lync Server に対して有効になっていることを確認する必要があります。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に、テスト用の CsAVConference が正常に機能しない場合の一般的な理由を示します。

  - 無効なユーザーアカウントが指定されました。 次のようなコマンドを実行すると、ユーザーアカウントが存在するかどうかを確認できます。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。 Lync Server でユーザーアカウントが有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server を有効にしていないことを意味します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

