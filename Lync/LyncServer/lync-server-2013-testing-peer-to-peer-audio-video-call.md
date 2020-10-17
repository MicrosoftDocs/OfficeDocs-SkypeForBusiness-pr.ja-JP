---
title: 'Lync Server 2013: ピアツーピア音声ビデオ通話のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8522a1f3a8aedd44a6d39faa0ba6f59ba773677
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504084"
---
# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a>Lync Server 2013 でのピアからピアへの音声/ビデオ通話のテスト

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsP2PAV コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Test-CsP2PAV は、テストユーザーのペアがピアツーピアの音声ビデオ会話に参加できるかどうかを判断するために使用されます。 このシナリオをテストするために、このコマンドレットは、Lync Server に2人のユーザーをログオンすることで開始します。 2 つのログオンが正常に行われたら、最初のユーザーが 2 人目のユーザーを A/V 通話に参加するように招待します。 2 人目のユーザーが通話を受諾すると、2 人のユーザー間の接続がテストされ、通話が終了した後、テスト ユーザーはシステムからログオフされます。

Test-CsP2PAV は、実際には音声ビデオ通話を行いません。 マルチメディア情報は、テストユーザー間で交換されません。 代わりに、このコマンドレットは単に適切な接続が確立されていることを確認し、2人のユーザーがそのような呼び出しを行えるようにします。

詳細については、 [test-csp2pav](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) コマンドレットのヘルプドキュメントを参照してください。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Test-CsP2PAV コマンドレットを実行するには、事前に構成された一連のテストアカウントを使用します (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照してください)。または、Lync Server が有効になっている2人のユーザーのアカウント。 このチェックをテストアカウントを使用して実行するには、テストする Lync Server プールの FQDN を指定するだけで済みます。 以下に例を示します。

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

実際のユーザーアカウントを使用してこのチェックを実行するには、2つの Lync Server credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。 次に、Test-csp2pav を呼び出すときに、これらの資格情報オブジェクトと2つのアカウントの SIP アドレスを含める必要があります。

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

2つのテストユーザーがピアツーピアの音声ビデオ呼び出しを完了できる場合は、次のような出力が得られ、Result プロパティは Success としてマークされ **ます。**

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間:00:00: 06.8630376

エラー

分析

テストユーザーが通話を完了できない場合、結果は失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間: 00:00:00

エラー: 480、一時的に使用できません

診断: ErrorCode = 15030, Source = litwareinc, Reason = Failed (エラー)

Exchange Server にルーティングするには

DiagnosticHeader ()

たとえば、Microsoft Exchange Server に接続できなかったため、テストが失敗したことが前の出力に示されています。 このエラーメッセージは、通常、Exchange ユニファイドメッセージングの構成に問題があることを示します。

Test-CsP2PAV が失敗した場合は、次のように詳細パラメーターを含めて、テストを再実行することをお勧めします。

Test-CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose

Verbose パラメーターが含まれている場合、Test-CsP2PAV は、指定されたユーザーが Lync Server にログオンする機能をチェックしたときに実行された各操作のステップごとのアカウントを返します。 たとえば、次の診断によってテストが失敗したとします。

ErrorCode = 6003, Source = litwareinc, Reason = サポートされていないダイアログの要求

Test-CsP2PAV を再実行して Verbose パラメーターを含めると、次のような出力が得られます。

VERBOSE: ' Register ' アクティビティが開始されました。

登録要求の送信:

ターゲット Fqdn = atl-cs-011.litwareinc.com

ユーザー Sip アドレス = sip:kenmyer@litwareinc.com

レジストラーポート = 5062。

認証の種類 ' IWA ' が選択されています。

例外 ' エンドポイントを登録できませんでした。 具体的な理由については、「エラーコード」を参照してください。 ' STP2PAVWorkflow のワークフローの実行中に発生しました。

すぐにわかるかもしれませんが、出力を注意深く調べると、誤ったレジストラーポート (ポート 5062) が指定されていることがわかります。 その結果、テストが失敗したことが発生しました。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

Test-CsP2PAV が失敗する可能性のある一般的な理由を次に示します。

  - 無効なユーザーアカウントが指定されました。 ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。
    
    Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。 ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server に対して有効になっていないことを意味します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

