---
title: 'Lync Server 2013: モバイルユーザーがインスタントメッセージをやり取りする機能をテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7fd19f6ef2f4a44a61d56848b4bf845c79736ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a>Lync Server 2013 でモバイルユーザーがインスタントメッセージをやり取りする機能をテストする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-06-07_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>確認のスケジュール</p></td>
<td><p>毎月</p></td>
</tr>
<tr class="even">
<td><p>テストツール</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要なアクセス許可</p></td>
<td><p>Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</p>
<p>Windows PowerShell のリモートインスタンスを使って実行する場合は、CsMcxP2PIM コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

モバイルデバイスユーザーは、次のような操作を行うことができます。

1.  インスタントメッセージとプレゼンス情報を交換します。

2.  ワイヤレスプロバイダーではなく、内部でボイスメールを保存して取得します。

3.  職場やダイヤルアウト会議などの Lync Server 機能を利用できます。

CsMxcP2PIM コマンドレットを使うと、ユーザーがモビリティサービスを使用してインスタントメッセージを交換できることを簡単かつ簡単に確認することができます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

このテストを実行するには、2つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。 次に、CsMcxP2PIM を呼び出したときに、これらの資格情報オブジェクトと、2つのアカウントの SIP アドレスを含める必要があります。

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

詳細については、 [CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM)コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

2つのテストユーザーがモバイルサービスを使用してインスタントメッセージを交換できる場合は、CsMcxP2PIM によってテスト結果の成功が返されます。

ターゲット Fqdn: atl-cs-001.litwareinc.com

ターゲット Uri:http://atl-cs-001.litwareinc.com:443/mcx

結果: 成功

待ち時間: 00:00:00

エラーメッセージ:

診断

テストが失敗した場合、結果は "失敗" に設定され、詳細なエラーメッセージと診断が表示されます。

ターゲット Fqdn: atl-cs-001.litwareinc.com

ターゲット Uri:https://atl-cs-001.litwareinc.com:443/mcx

結果: エラー

待ち時間: 00:00:00

エラーメッセージ: Web チケットサービスの応答がありませんでした。

内部例外: HHTP 要求は、で許可されていません。

クライアントネゴシエーションスキーム ' Ntlm '。 認証

サーバーから受信したヘッダーは、"Negotiate、NTLM" でした。

内部例外: リモートサーバーからエラーが返されました:

(401) 承認されていません。

診断

内部診断: X-MS---------------------------

001.litwareinc.com

キャッシュ制御: プライベート

Content-type: text/html;charset = utf-8。

サーバー: Microsoft-IIS/8.5

WWW-認証: Negotiate、NTLM

X-電力: ASP.NET

X-コンテンツタイプ-オプション: nosniff

日付: 水曜日、28年5月 19:16:05 2014 日

Content-length: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

テスト-CsMcxP2PIM が失敗した場合は、最初の手順でモビリティサービスが起動して実行されていることを確認する必要があります。 この操作を行うには、web ブラウザーを使用して、Lync Server プールのモビリティサービスの URL にアクセスできることを確認します。 たとえば、次のコマンドは、プール atl-cs-001.litwareinc.com の URL を確認します。

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

モバイルサービスが実行されているように見える場合は、2つのテストユーザーが有効な Lync Server アカウントを持っていることを確認します。 次のようなコマンドを使用して、アカウント情報を取得できます。

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Enabled プロパティが True と等しくない場合、またはコマンドが失敗した場合は、ユーザーが有効な Lync Server アカウントを持っていないことを意味します。

また、ユーザーがモビリティを有効にしていることも確認する必要があります。 そのためには、まず、アカウントに割り当てられているモビリティポリシーを特定します。

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

ポリシー名がわかったら、Set-csmobilitypolicy コマンドレットを使用して、問題のポリシー (RedmondMobilityPolicy など) で EnableMobility プロパティが True に設定されていることを確認します。

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

認証ヘッダーを含むエラーメッセージが表示された場合は、それは、有効なユーザーアカウントを指定していないことを意味します。 ユーザー名とパスワードを確認して、もう一度テストしてみてください。 ユーザーアカウントが有効であると確信できる場合は、CsWebServiceConfiguration コマンドレットを使用して、UseWindowsAuth プロパティの値を確認します。 これにより、どの認証方法が組織で有効になっているかがわかります。モバイルサービスのトラブルシューティングのヒントについては、「ブログの投稿の[トラブルシューティング外部の Lync モバイル接続の問題のトラブルシューティング](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

