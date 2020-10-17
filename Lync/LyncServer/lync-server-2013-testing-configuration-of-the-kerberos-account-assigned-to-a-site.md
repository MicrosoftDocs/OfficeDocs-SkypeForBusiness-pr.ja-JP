---
title: サイトに割り当てられた Kerberos アカウントの構成をテストする
description: サイトに割り当てられた Kerberos アカウントの構成をテストします。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0eab1618474a19753a4c6064d59aa4f8a856fceb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560693"
---
# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a>Lync Server 2013 のサイトに割り当てられた Kerberos アカウントの構成をテストする

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsKerberosAccountAssignment コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Test-CsKerberosAccountAssignment コマンドレットを使用すると、Kerberos アカウントが特定のサイトに関連付けられていること、このアカウントが正しく構成されていること、およびアカウントが期待どおりに動作していることを確認できます。 Kerberos アカウントは、インターネットインフォメーションサービス (IIS) を実行しているサイト内のすべてのコンピューターの認証プリンシパルとして機能するコンピューターアカウントです。 これらのアカウントは kerberos 認証プロトコルを使用するため、アカウントは Kerberos アカウントと呼ばれ、新しい認証プロセスは Kerberos web 認証と呼ばれます。 これにより、1つのアカウントを使用してすべての IIS サーバーを管理できるようになります。

詳細については、 [get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) コマンドレットのヘルプドキュメントを参照してください。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

既定では、Test-CsKerberosAccountAssignment 画面に表示される出力はほとんどありません。 代わりに、コマンドレットによって返される情報は、HTML ファイルに書き込まれます。 そのため、Get-cskerberosaccountassignment を実行するたびに Verbose パラメーターと Report パラメーターを含めることをお勧めします。 Verbose パラメーターは、コマンドレットの実行中に画面により詳細な出力を提供します。 Report パラメーターを使用すると、Get-cskerberosaccountassignment によって生成された HTML ファイルのファイルパスとファイル名を指定できます。 Report パラメーターを指定しない場合、HTML ファイルは自動的にユーザーのフォルダーに保存され、次のような名前が付けられます。 ce84964a-c4da-4622-ad34-c54ff3ed361f.html。

Get-cskerberosaccountassignment を実行するときに、サイト Id も指定する必要があります。 Kerberos アカウントは、サイトスコープで割り当てられます。

次のコマンドは Test-CsKerberosAccountAssignment を実行し、出力を C: LogsKerberosTest.html という名前のファイルに保存し \\ \\ ます。

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

詳細については、 [get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) コマンドレットのヘルプドキュメントを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

Test-CsKerberosAccountAssignment コマンドレットは、成功または失敗の簡単な指示を返しません。 代わりに、生成された HTML ファイルを Internet Explorer を使用して表示する必要があります。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

Test-CsKerberosAccountAssignment が失敗する可能性のある一般的な理由を次に示します。

  - 正しくないサイト Id が指定されている可能性があります。 有効なサイト Id の一覧を返すには、次のコマンドを使用します。
    
        Get-CsSite | Select-Identity Identity
    
    サイト Id は通常、次のようになります。
    
    サイト: Redmond

  - 指定したサイトに Kerberos アカウントが割り当てられていない可能性があります。 次のようなコマンドを実行することによって、サイトに Kerberos アカウントが割り当てられているかどうかを判断できます。
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - Kerberos アカウントに有効ではないパスワードが設定されている可能性があります。 次のエラーメッセージがレポートに表示された場合は、Kerberos アカウントのパスワードをリセットする必要があります。
    
    InvalidKerberosConfiguration: Kerberos 構成が無効です。
    
    InvalidKerberosConfiguration: atl-cs001.litwareinc.com 上の Kerberos 構成が無効です。 必要な割り当て済みアカウントが litwareinc kerberostest である \\ 。 アカウントの有効期限が切れていないこと、およびコンピューター上の構成されたパスワードがアカウントの Active Directory パスワードと一致することを確認します。
    
    パスワードを設定するには、 [set-Cskerの Osaccountpassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) コマンドレットを使用します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

