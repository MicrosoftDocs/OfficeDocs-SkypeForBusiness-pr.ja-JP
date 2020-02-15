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
ms.openlocfilehash: efc07ff877d5692c2871a8b0481233d3bd8c58b6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-client-authentication-in-lync-server-2013"></a>Lync Server 2013 での Lync クライアント認証のテスト

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テスト用の CsClientAuth コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Test-CsClientAuth コマンドレットを使用すると、ユーザーがクライアント証明書を使用して Lync Server にログオンできるかどうかを判断できます。また、Test-CsClientAuth コマンドレットを実行することもできます。 Test-CsClientAuth を呼び出した後、コマンドレットは証明書プロビジョニングサービスに接続し、指定されたユーザーのクライアント証明書のコピーをダウンロードします。 クライアント証明書を検出してダウンロードできる場合は、その証明書を使用してログオンを試行します。 ログオンに成功すると、テスト-CsClientAuth はログオフし、テストが成功したことを報告します。 証明書が見つからないかダウンロードできない場合、またはダウンロードした証明書を使用してログオンできない場合、Test-CsClientAuth はテストが失敗したことを報告します。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Lync Server が有効になっているすべてのユーザーのアカウントを使用して、CsClientAuth コマンドレットを実行します。 実際のユーザーアカウントを使用してこのチェックを実行するには、まず、アカウント名とパスワードを含む Windows PowerShell credentials オブジェクトを作成する必要があります。 次に、システムが Test-CsClientAuth を呼び出すときに、その資格情報オブジェクトと、そのアカウントに割り当てられた SIP アドレスを含める必要があります。

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

詳細については、「 [Test-CsClientAuth](http://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

指定したユーザーがクライアント証明書を使用して Lync Server にログオンできる場合は、次のような出力が返されます。 Result プロパティは Success とマークされてい**ます。**

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間:00:00: 06.8630376

エラー

分析

指定したユーザーがログオンできない場合、結果は失敗として表示され、追加情報が Error および診断プロパティに記録されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間:00:00: 03.3645259

エラー: 指定されたユーザーの CS 証明書をダウンロードできませんでした。 かどうかを確認

指定された uri と資格情報が正しいこと。

分析

たとえば、指定されたユーザーの有効なクライアント証明書が見つからないため、テストが失敗したことが上記の出力に示されます。 次のようにコマンドを実行することによって、ユーザーに対して発行されたクライアント証明書の一覧を返すことができます。

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

Test-CsClientAuth に障害が発生した場合は、次のように詳細パラメーターを含めて、テストを再実行することをお勧めします。

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

Verbose パラメーターが指定されている場合、テスト-CsClientAuth は、指定されたユーザーが Lync Server にログオンできるかどうかを確認したときに試行された各アクションのステップバイステップのアカウントを返します。 例:

ユーザーの CS 証明書をダウンロードしようとしています: kenmyer@litwareinc.com endpoint: STEpid

Web サービス url:https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc

Web サービスから CS 証明書をダウンロードできませんでした。

確かめ

\-Web サービスの url が有効で、web サービスが機能している

\-PhoneNo\\\\Pin を使用して認証する場合は、ユーザーの uri と一致していることを確認してください。

\-NTLM\\Kerberos 認証を使用している場合は、有効な資格情報を入力してください。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

次に、Test-CsClientAuth が失敗する主な理由を示します。

  - 無効なユーザーアカウントが指定されました。 ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。 ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server に対して有効になっていないことを意味します。

  - テストユーザーが有効なクライアント証明書を持っていない可能性があります。 次のようなコマンドを使用して、ユーザーに割り当てられているクライアント証明書に関する情報を戻すことができます。
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

