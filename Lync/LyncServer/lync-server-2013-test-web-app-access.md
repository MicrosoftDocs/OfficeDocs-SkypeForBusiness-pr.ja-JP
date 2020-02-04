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
ms.openlocfilehash: 7618bcc9a69d177950bae64354106a67721e822a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-web-app-access-in-lync-server-2013"></a>Lync Server 2013 で Web アプリへのアクセスをテストする

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
<p>Windows PowerShell のリモートインスタンスを使って実行する場合、ユーザーには、テスト用の CsWebApp コマンドレットを実行するアクセス許可が与えられた RBAC の役割を割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

テスト用の Web コマンドレットは、認証されたユーザーが Lync Web App を使って Lync Server 会議に参加できることを確認します。 コマンドレットを実行するときに、テスト用の Web チケットサービスに連絡して、指定されたユーザーの web チケットを取得します。 これらのチケットは、Lync Server 会議の "受付チケット" として効果的に機能します。 チケットを取得できる場合に、ユーザーを認証できる場合は、ユーザーは Lync Server に連絡し、インスタントメッセージング、アプリケーション共有、データの共同作業のために個別の会議を確立しようとします。

このテストでは、これらの会議を作成するために使用された Api と接続を確認するだけであることに注意してください。 このコマンドレットは、Lync Web App を使用して会議を作成して参加できることを確認するように設計されています。 ただし、実際には会議を作成して実施するわけではありません。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

テスト用の Webapp コマンドレットを実行するには、構成済みのテストアカウントのペア、または Lync Server を有効にしている2人のユーザーのアカウントのいずれかを使用します。 テストアカウントを使用してこのチェックを実行するには、テスト対象の Lync サーバープールの完全修飾ドメイン名を指定する必要があります。 次に例を示します。

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

実際のユーザーアカウントを使用してこのチェックを実行するには、2つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。 次に、これらの資格情報オブジェクトと、次に記載されている2つのアカウントの SIP アドレスを、テスト用の Webapp の作成時に含める必要があります。

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

詳細については、「[テスト-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp)コマンドレットのヘルプ」を参照してください。 テスト用 CsWebApp は、Lync Server 2013 で使用するために廃止されたことに注意してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

テスト用の Webapp をユーザーが会議に参加できる場合、コマンドレットによってテスト結果の成功が返されます。

ターゲット Fqdn:

結果: 成功

待ち時間: 00:00:00

エラーメッセージ:

診断

ユーザーが必要な会議に参加できない場合、テスト結果は [エラー] としてマークされます。 通常、テスト用の Webapp は、詳細なエラーメッセージと診断についても報告します。

ターゲット Fqdn: atl-cs-001.litwareinc.com

結果: エラー

待ち時間: 00:00:00

エラーメッセージ: Web チケットサービスの応答がありません

診断: HTTP 要求はクライアントで承認されていません

認証スキーム ' Ntlm '。 認証

サーバーから受信したヘッダーは、"Negotiate、NTLM" でした。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

通常、テスト用の Webapp のエラーには、ユーザー認証エラーが含まれます。 テスト用の作成に失敗した場合は、最初に、指定したユーザーに有効なユーザーアカウントがあり、Lync Server が有効になっていることを確認する必要があります。 次のようなコマンドを使用して、アカウント情報を取得できます。

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Enabled プロパティが True と等しくない場合、またはコマンドが失敗した場合は、ユーザーが有効な Lync Server アカウントを持っていないことを意味します。また、コマンドレットに指定したパスワードが有効であることも確認する必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

