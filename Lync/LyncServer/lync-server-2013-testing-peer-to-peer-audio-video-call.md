---
title: 'Lync Server 2013: ピアツーピア音声/ビデオ通話のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43fc4da7619dcc4cfd88417b52543dc23c447883
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a>Lync Server 2013 でピアツーピア音声/ビデオ通話をテストする

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
<p>Windows PowerShell のリモートインスタンスを使って実行する場合は、CsP2PAV コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

CsP2PAV は、テストユーザーのペアがピアツーピアの A/V の会話に参加できるかどうかを判断するために使用されます。 このシナリオをテストするために、このコマンドレットは、2人のユーザーを Lync Server にログオンして開始します。 2つのログオンが成功すると、最初のユーザーは、A/V 呼び出しに参加するように2番目のユーザーを招待します。 2人目のユーザーが通話を受け入れ、2人のユーザー間の接続がテストされた後、通話が終了し、テストユーザーがシステムからログオフされます。

CsP2PAV は、実際に A/V 通話を行いません。 マルチメディア情報は、テストユーザー間では交換されません。 代わりに、コマンドレットは、適切な接続を行うことができ、2人のユーザーがそのような呼び出しを実行できることを確認するだけです。

詳細については、「 [CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

CsP2PAV コマンドレットを実行するには、定義済みのテストアカウントのペア (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照) を使用するか、Lync Server を有効にしている2人のユーザーのアカウントを使用します。 テストアカウントを使用してこの確認を実行するには、テストする Lync Server プールの FQDN を指定する必要があります。 次に例を示します。

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

実際のユーザーアカウントを使用してこのチェックを実行するには、Lync Server credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) をそれぞれのアカウントに作成する必要があります。 次に、CsP2PAV を呼び出したときに、これらの資格情報オブジェクトと、2つのアカウントの SIP アドレスを含める必要があります。

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

2つのテストユーザーがピアツーピアの A/V の呼び出しを完了できる場合は、次のような結果として、Success とマークされた Result プロパティの出力が表示され**ます。**

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待ち時間:00:00: 06.8630376

誤差

診断

テストユーザーが通話を完了できなかった場合、結果は失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待ち時間: 00:00:00

エラー: 480、一時的に使用できません

診断: ErrorCode = 15030、Source = atl-litwareinc、Reason = Failed。

Exchange Server にルーティングするには

DiagnosticHeader の場合

たとえば、前回の出力では、Microsoft Exchange Server に接続できなかったため、テストが失敗したことが示されます。 このエラーメッセージは、通常、Exchange ユニファイドメッセージングの構成に問題があることを示します。

テスト-CsP2PAV が失敗した場合は、Verbose パラメーターも含めて、テストを再実行することをお勧めします。

CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose

Verbose パラメーターが含まれている場合、CsP2PAV は、指定されたユーザーが Lync Server にログオンする機能をチェックしたときに実行される各操作のステップバイステップのアカウントを返します。 たとえば、次のような診断でテストが失敗したとします。

ErrorCode = 6003、Source = atl-litwareinc、Reason = サポートされていないダイアログの要求

CsP2PAV を再実行し、Verbose パラメーターを含めると、次のような出力が表示されます。

VERBOSE: ' Register ' アクティビティが開始されました。

登録リクエストの送信:

ターゲット Fqdn = atl-cs-011.litwareinc.com

ユーザー Sip アドレス = sip:kenmyer@litwareinc.com

レジストラーポート = 5062。

認証の種類 ' IWA ' が選択されています。

"エンドポイントを登録できませんでした。" という例外が発生します。 具体的な理由については、「エラーコード」をご覧ください。 STP2PAVWorkflow の実行中に発生したワークフローのことです。

あまり明確でない場合もありますが、出力を慎重に確認すると、誤ったレジストラーポート (port 5062) が指定されていることがわかります。 これにより、テストが失敗する原因となります。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に、テスト-CsP2PAV が失敗する可能性がある一般的な理由を示します。

  - 無効なユーザーアカウントが指定されました。 次のようなコマンドを実行すると、ユーザーアカウントが存在するかどうかを確認できます。
    
    ユーザー "sip:kenmyer@litwareinc.com" を取得する

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。 Lync Server でユーザーアカウントが有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server を有効にしていないことを意味します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

