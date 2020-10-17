---
title: 'Lync Server 2013: Web アプリへのアクセスのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test Web App access
ms:assetid: 17d67ea3-f74d-4952-ac2b-92c0dacc8014
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767944(v=OCS.15)
ms:contentKeyID: 63969584
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cdf0c4d974732b75a7ff83022c6bfbf1c4d8e80
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532934"
---
# <a name="test-web-app-access-in-lync-server-2013"></a>Lync Server 2013 での Web アプリケーションアクセスのテスト

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsWebApp コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Test-CsWebApp コマンドレットは、認証されたユーザーが lync Web App を使用して Lync Server 会議に参加できることを確認します。 コマンドレットを実行すると、Test-CsWebApp は Web チケットサービスに接続して、指定されたユーザーの web チケットを取得します。 これらのチケットは、Lync Server 会議の「受付チケット」として効果的に機能します。 チケットを取得でき、ユーザーが認証されている場合、Test-CsWebApp は Lync Server に接続して、インスタントメッセージング、アプリケーション共有、およびデータコラボレーションのための個別の会議を確立しようとします。

Test-CsWebApp、これらの会議の作成に使用された Api と接続を確認するだけであることに注意してください。 コマンドレットは、Lync Web App を使用して会議の作成と参加を行うことができることを確認するように設計されています。 ただし、実際には会議を作成して実施することはありません。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Test-CsWebApp コマンドレットは、構成済みのテストアカウントのペア、または Lync Server が有効になっている2人のユーザーのアカウントのいずれかを使用して実行できます。 このチェックをテストアカウントを使用して実行するには、テストする Lync Server プールの完全修飾ドメイン名を指定するだけで済みます。 以下に例を示します。

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

実際のユーザーアカウントを使用してこのチェックを実行するには、2つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。 次に、Test-CsWebApp を呼び出すときに、これらの資格情報オブジェクトと2つのアカウントの SIP アドレスを含める必要があります。

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

詳細については、 [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) コマンドレットのヘルプトピックを参照してください。 Test-CsWebApp は、Lync Server 2013 で使用するために廃止されたことに注意してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

Test-CsWebApp がユーザーを会議に参加させると、コマンドレットはテスト結果の成功を返します。

ターゲット Fqdn:

結果: 成功

待機時間: 00:00:00

エラーメッセージ:

分析

ユーザーが必要な電話会議に参加できない場合は、テスト結果が [失敗] としてマークされます。 通常 Test-CsWebApp は、詳細なエラーメッセージと診断にも報告します。

ターゲット Fqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間: 00:00:00

エラーメッセージ: Web-Ticket サービスの応答が受信されませんでした

診断: HTTP 要求はクライアントによって承認されていません

認証スキーム ' Ntlm '。 認証

サーバーから送信されたヘッダーは ' Negotiate, NTLM ' でした。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

通常、Test-CsWebApp エラーには、ユーザー認証エラーが含まれます。 Test-CsWebApp が失敗した場合は、まず、指定されたユーザーが有効なユーザーアカウントを持っていて、Lync Server が有効になっていることを確認する必要があります。 次のようなコマンドを使用して、アカウント情報を取得できます。

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Enabled プロパティが True と一致しない場合、またはコマンドが失敗した場合は、ユーザーが有効な Lync Server アカウントを持っていないことを意味します。また、コマンドレットに指定したパスワードが有効であることも確認する必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

