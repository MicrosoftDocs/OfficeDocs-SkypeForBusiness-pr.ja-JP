---
title: 'Lync Server 2013: 匿名 Web App アクセスのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9df6a040e71b0dfe82a52cf519357d058b78a1d7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a>Lync Server 2013 で匿名 Web アプリのアクセスをテストする

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合は、Test-cswebappanonymous コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Test-cswebappanonymous コマンドレットでは、匿名ユーザーが Lync Web App を使用して Lync Server 会議に参加できることを確認します。 コマンドレットを実行すると、Test-cswebappanonymous は Web チケットサービスに接続して、匿名ユーザーの web チケットを取得します。 コマンドレットがこのチケットの取得に成功すると、Test-cswebappanonymous は Lync Server に接続して、インスタントメッセージング、アプリケーション共有、およびデータコラボレーションのための個別の会議を確立しようとします。

Test-cswebappanonymous は、これらの会議を作成するために使用された Api と接続のみを検証することに注意してください。 コマンドレットは、実際には会議を作成して実施しません。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Test-cswebappanonymous コマンドレットは、構成済みのテストアカウントのペア、または Lync Server が有効になっている2人のユーザーのアカウントのいずれかを使用して実行できます。 このチェックをテストアカウントを使用して実行するには、テストする Lync Server プールの完全修飾ドメイン名を指定するだけで済みます。 次に例を示します。

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

実際のユーザーアカウントを使用してこのチェックを実行するには、Lync Server 管理シェルの資格情報オブジェクト (アカウント名とパスワードを含むオブジェクト) を、各アカウントに2つ作成する必要があります。 次に、Test-cswebappanonymous を呼び出すときに、これらの資格情報オブジェクトと2つのアカウントの SIP アドレスを含める必要があります。

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

詳細については、Test-cswebappanonymous コマンドレットのヘルプトピックを参照してください。 Test-cswebappanonymous は、Lync Server 2013 で使用する場合は推奨されていないことに注意してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

Test-cswebappanonymous が匿名ユーザーを自分の会議に参加できる場合、コマンドレットはテスト結果の成功を返します。

ターゲット Fqdn:

結果: 成功

待機時間: 00:00:00

エラーメッセージ:

分析

匿名ユーザーが必要な電話会議に参加できない場合は、テスト結果が [失敗] としてマークされます。 通常、Test-cswebappanonymous は、詳細なエラーメッセージと診断にも報告します。

ターゲット Fqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間:00:00: 05.9746266

エラーメッセージ: Web チケットサービスの応答が受信されていません

診断: HTTP 要求はクライアントによって承認されていません

認証スキーム ' Ntlm '。 認証

サーバーから送信されたヘッダーは ' Negotiate, NTLM ' でした。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

Test-cswebappanonymous の失敗は通常、ユーザー認証エラーを中心にしています。コマンドレットが Lync Server に接続する匿名ユーザーの機能をチェックしている場合でも、有効なユーザーアカウントを使用してテストを実行する必要があります。 Test-cswebappanonymous が失敗した場合は、指定されたユーザーの Lync Server ユーザーアカウントが有効であることを確認する必要があります。 Lync Server アカウント情報を取得するには、次のようなコマンドを使用します。

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Enabled プロパティが True と一致しない場合、またはコマンドが失敗した場合は、ユーザーが有効な Lync Server アカウントを持っていないことを意味します。

また、コマンドレットを実行するときに指定したパスワードが有効なパスワードであることも確認する必要があります。

Office Web Apps サーバーの構成の問題によっても、Test-cswebappanonymous が失敗することがあります。これは、次のような診断を受け取った場合によく当てはまります。

HTTP 要求は、クライアント認証スキーム ' Ntlm ' では許可されていません。 サーバーから受信した認証ヘッダーは ' Negotiate, NTLM ' でした。

Office Web Apps サーバーの問題の診断と解決の詳細については、「ブログ投稿の Office Web Apps サーバー2013」を参照してください。[コンピューターは常に異常として報告され](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy)ます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

