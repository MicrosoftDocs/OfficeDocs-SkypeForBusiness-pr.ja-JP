---
title: 'Lync Server 2013: モバイルユーザーアクセスのテスト'
description: 'Lync Server 2013: モバイルユーザーアクセスをテストします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e99a05e6ef9fe925126026452823e5edcc100ede
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541873"
---
# <a name="test-mobile-user-access-in-lync-server-2013"></a>Lync Server 2013 でのモバイルユーザーアクセスのテスト

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-06-07_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>検証スケジュール</p></td>
<td><p>毎月</p></td>
</tr>
<tr class="even">
<td><p>テストツール</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要なアクセス許可</p></td>
<td><p>Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</p>
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsMcxConference コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Mobility Service を使用すると、モバイルデバイスのユーザーは次のことを行うことができます。

1.  Exchange インスタントメッセージとプレゼンス情報。

2.  ボイスメールをワイヤレスプロバイダーではなく内部に保存および取得します。

3.  勤務先およびダイヤルアウト会議経由の通話など、Lync Server の機能を活用します。 Test-CsMcxConference コマンドレットを使用すると、ユーザーがモバイルデバイスを使用して Lync Server 会議に参加して参加できることを確認するための簡単な方法が提供されます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

このチェックを実行するには、3つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。 次の例に示すように、Test-CsMcxConference を呼び出すときに、これらの資格情報オブジェクトと2つのアカウントの SIP アドレスを含める必要があります。

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

詳細については、 [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

チェックに成功すると、Test-CsMcxConference は成功のテスト結果を報告します。

ターゲット Fqdn: atl-cs-001.litwareinc.com

ターゲット Uri: http://atl-cs-001.litwareinc.com:443/mcx

結果: 成功

待機時間: 00:00:00

エラーメッセージ:

分析

チェックが失敗した場合 Test-CsMcxConference は失敗のテスト結果を報告します。 通常、このテスト結果には、詳細なエラーメッセージと診断が伴います。 以下に例を示します。

ターゲット Fqdn: atl-cs-001.litwareinc.com

ターゲット Uri: https://atl-cs-001.litwareinc.com:443/mcx

結果: エラー

待機時間: 00:00:00

エラーメッセージ: Web-Ticket サービスの応答が受信されませんでした。

内部例外: HHTP 要求はクライアントによって承認されていません

ネゴシエーションスキーム ' Ntlm '。 受信した認証ヘッダー

サーバーから ' Negotiate ' が行われました。

内部例外: リモートサーバーがエラーを返しました: (401)

非.

分析

内部診断: atl-cs-001.litwareinc.com--サーバー-一方向の Db:

Cache-Control: private

コンテンツタイプ: text/html。charset = utf-8。

サーバー: Microsoft-IIS/8.5

WWW-Authenticate: Negotiate、NTLM

X-Powered By: ASP.NET

X-コンテンツタイプ-オプション: nosniff

日付: 水曜日、28月 2014 19:22:19 GMT

コンテンツの長さ: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

Test-CsMcxConference が失敗した場合は、mobility service が実行されていてアクセス可能であることを確認することから開始する必要があります。 これを行うには、web ブラウザーを使用して、Lync Server プールの mobility service URL にアクセスできることを確認します。 たとえば、次のコマンドを実行すると、プール atl-cs-001.litwareinc.com の URL が確認されます。

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

Mobility service にアクセスできる場合は、テストユーザーが有効な Lync Server アカウントを持っていることを確認する必要があります。 次のようなコマンドを使用して、アカウント情報を取得できます。

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Enabled プロパティが True と一致しない場合、またはコマンドが失敗した場合は、ユーザーが有効な Lync Server アカウントを持っていないことを意味します。また、各ユーザーアカウントがモビリティに対して有効になっていることも確認する必要があります。 そのためには、まず、アカウントに割り当てられているモビリティポリシーを特定します。

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

ポリシー名を確認したら、Get-CsMobilityPolicy コマンドレットを使用して、対象のポリシー (たとえば、RedmondMobilityPolicy) に EnableMobility プロパティが True に設定されていることを確認します。

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

Test-CsMcxConference を実行するときに "authentication header" というエラーメッセージが表示される場合は、有効なユーザーアカウントが指定されていないことを意味する場合は、ユーザー名とパスワードを確認して、もう一度テストを実行してください。 ユーザーアカウントが有効であることを確信する場合は、Get-CsWebServiceConfiguration コマンドレットを使用して、UseWindowsAuth プロパティの値を確認します。 これにより、組織内で有効になっている認証方法がわかります。

Mobility service のトラブルシューティング方法に関するその他のヒントについては、ブログ投稿の「 [外部 Lync モビリティ接続の問題のトラブルシューティング](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

