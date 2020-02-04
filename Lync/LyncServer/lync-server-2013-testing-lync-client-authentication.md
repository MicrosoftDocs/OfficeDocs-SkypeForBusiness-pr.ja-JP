---
title: 'Lync Server 2013: Lync クライアント認証のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e24f579a4fcaca2651c0225b515241db00ff990
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-client-authentication-in-lync-server-2013"></a>Lync Server 2013 での Lync クライアント認証のテスト

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
<p>Windows PowerShell のリモートインスタンスを使って実行する場合、ユーザーには、CsClientAuth コマンドレットを実行する権限を持つ RBAC の役割を割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

ユーザーがクライアント証明書を使って Lync サーバーにログオンできるかどうかを判断するには、csclientauth コマンドレットを使用します。このコマンドレットを実行します。 テスト用の CsClientAuth を呼び出すと、コマンドレットは証明書プロビジョニングサービスに問い合わせ、指定されたユーザーのクライアント証明書のコピーをダウンロードします。 クライアント証明書を見つけてダウンロードできる場合は、その証明書を使用してログオンしようとします。 ログインに成功した場合、テスト-CsClientAuth はログオフし、テストが成功したことを報告します。 証明書が見つからないか、ダウンロードできない場合、またはコマンドレットがその証明書を使用してログオンできない場合は、テストに不合格になったことがテストによって報告されます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Lync Server を有効にしているユーザーのアカウントを使用して、CsClientAuth コマンドレットを実行します。 実際のユーザーアカウントを使用してこのチェックを実行するには、最初に、アカウント名とパスワードを含む Windows PowerShell 資格情報オブジェクトを作成する必要があります。 次に、資格情報オブジェクトと、システムが Test CsClientAuth を呼び出すときにアカウントに割り当てられる SIP アドレスを含める必要があります。

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

詳細については、「 [CsClientAuth のテスト](http://technet.microsoft.com/en-us/library/gg398712\(v=ocs.14\).aspx)コマンドレット」のヘルプドキュメントを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

指定したユーザーがクライアント証明書を使って Lync サーバーにログオンできる場合は、次のような出力が返されます。これには、Result プロパティが Success とマークされてい**ます。**

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待ち時間:00:00: 06.8630376

誤差

診断

指定したユーザーがログオンできない場合、結果は失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待ち時間:00:00: 03.3645259

エラー: 指定されたユーザーの CS 証明書をダウンロードできませんでした。 かどうかを確認

指定された uri と資格情報が正しい。

診断

たとえば、前回の出力には、指定したユーザーに対して有効なクライアント証明書が見つからなかったため、テストが失敗したことが示されます。 次のようにコマンドを実行することで、ユーザーに発行されたクライアント証明書の一覧を返すことができます。

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

テスト用のクライアント認証が失敗した場合は、Verbose パラメーターなどのテストを再実行することをお勧めします。

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

Verbose パラメーターが含まれている場合は、指定されたユーザーが Lync Server にログオンする機能をオンにしたときに実行される各操作のステップバイステップのアカウントが返されます。 次に例を示します。

次のユーザーの CS 証明書をダウンロードしようとしています: kenmyer@litwareinc.com endpoint: STEpid

Web サービスの url:https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc

Web サービスから CS 証明書をダウンロードできませんでした。

調べ

\-Web サービスの url が有効であり、web サービスが機能している

\-認証に PhoneNo\\\\Pin を使用している場合は、ユーザーの uri と一致することを確認します。

\-NTLM\\Kerberos 認証を使用している場合は、有効な資格情報を指定していることを確認します。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に、テスト用の CsClientAuth が失敗する一般的な理由をいくつか示します。

  - 無効なユーザーアカウントが指定されました。 次のようなコマンドを実行すると、ユーザーアカウントが存在するかどうかを確認できます。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。 Lync Server でユーザーアカウントが有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server を有効にしていないことを意味します。

  - テストユーザーは、有効なクライアント証明書を持っていない可能性があります。 次のようなコマンドを使用して、ユーザーに割り当てられているクライアント証明書に関する情報を返すことができます。
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

