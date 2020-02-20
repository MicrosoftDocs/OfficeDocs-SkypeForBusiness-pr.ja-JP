---
title: 'Lync Server 2013: モバイルユーザーがインスタントメッセージを交換できるかどうかをテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5885ed34fd28f06b9a7d8c4f95abc29d3b5e147
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a>モバイルユーザーが Lync Server 2013 でインスタントメッセージを交換できるかどうかをテストする

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合は、Test-csmcxp2pim コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Mobility Service を使用すると、モバイルデバイスのユーザーは次のことを行うことができます。

1.  Exchange インスタントメッセージとプレゼンス情報。

2.  ボイスメールをワイヤレスプロバイダーではなく内部に保存および取得します。

3.  勤務先およびダイヤルアウト会議経由の通話など、Lync Server の機能を活用します。

CsMxcP2PIM コマンドレットを使用すると、ユーザーがモビリティサービスを使用してインスタントメッセージを交換できることをすばやく簡単に確認できます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

このテストを実行するには、2つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。 次に、Test-csmcxp2pim を呼び出すときに、これらの資格情報オブジェクトと2つのアカウントの SIP アドレスを含める必要があります。

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

詳細については、 [test-csmcxp2pim](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM)コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

2つのテストユーザーが mobility service を使用してインスタントメッセージを交換できる場合、Test-csmcxp2pim はテスト結果成功を返します。

ターゲット Fqdn: atl-cs-001.litwareinc.com

ターゲット Uri:http://atl-cs-001.litwareinc.com:443/mcx

結果: 成功

待機時間: 00:00:00

エラーメッセージ:

分析

テストが失敗した場合、結果は [失敗] に設定され、詳細なエラーメッセージと診断が表示されます。

ターゲット Fqdn: atl-cs-001.litwareinc.com

ターゲット Uri:https://atl-cs-001.litwareinc.com:443/mcx

結果: エラー

待機時間: 00:00:00

エラーメッセージ: Web チケットサービスの応答が受信されていません。

内部例外: HHTP 要求はに許可されていません

クライアントネゴシエーションスキーム ' Ntlm '。 認証

サーバーから送信されたヘッダーは ' Negotiate, NTLM ' でした。

内部例外: リモートサーバーがエラーを返しました。

(401) 権限がありません。

分析

内部診断:-----------------------------

001.litwareinc.com

キャッシュ制御: プライベート

コンテンツタイプ: text/html。charset = utf-8。

サーバー: Microsoft-IIS/8.5

WWW-認証: Negotiate、NTLM

X-Powered By: ASP.NET

X-コンテンツタイプ-オプション: nosniff

日付: 水曜日、28月 2014 19:16:05 GMT

コンテンツの長さ: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

Test-csmcxp2pim が失敗した場合、最初の手順は mobility service が稼働していることを確認する必要があります。 これを行うには、web ブラウザーを使用して、Lync Server プールの mobility service URL にアクセスできることを確認します。 たとえば、次のコマンドを実行すると、プール atl-cs-001.litwareinc.com の URL が確認されます。

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

Mobility service が実行されているように見える場合は、2つのテストユーザーが有効な Lync Server アカウントを持っていることを確認してください。 次のようなコマンドを使用して、アカウント情報を取得できます。

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Enabled プロパティが True と一致しない場合、またはコマンドが失敗した場合は、ユーザーが有効な Lync Server アカウントを持っていないことを意味します。

また、ユーザーのモビリティが有効になっていることも確認する必要があります。 そのためには、まず、アカウントに割り当てられているモビリティポリシーを特定します。

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

ポリシー名がわかったら、Get-csmobilitypolicy コマンドレットを使用して、対象のポリシー (RedmondMobilityPolicy など) に EnableMobility プロパティが True に設定されていることを確認します。

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

認証ヘッダーを使用してエラーメッセージが表示される場合は、有効なユーザーアカウントが指定されていないことを意味します。 ユーザー名とパスワードを確認してから、もう一度テストを実行してください。 ユーザーアカウントが有効であることを確信する場合は、Set-cswebserviceconfiguration コマンドレットを使用して、UseWindowsAuth プロパティの値を確認します。 これにより、組織内で有効になっている認証方法がわかります。Mobility service のトラブルシューティング方法に関するその他のヒントについては、ブログ投稿の「[外部 Lync モビリティ接続の問題のトラブルシューティング](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

