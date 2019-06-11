---
title: サイトに割り当てられている Kerberos アカウントの構成をテストする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e12a780c4c900423b23eff6cdaae15ba15786b6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a>Lync Server 2013 でサイトに割り当てられている Kerberos アカウントの構成をテストする

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
<p>Windows PowerShell のリモートインスタンスを使って実行する場合は、CsKerberosAccountAssignment コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

CsKerberosAccountAssignment コマンドレットを使用すると、指定したサイトに Kerberos アカウントが関連付けられていること、アカウントが正しく構成されていること、アカウントが予期したとおりに動作していることを確認できます。 Kerberos アカウントは、インターネットインフォメーションサーバー (IIS) を実行しているサイト内のすべてのコンピューターの認証プリンシパルとして機能するコンピューターアカウントです。 これらのアカウントは Kerberos 認証プロトコルを使用しているため、アカウントは Kerberos アカウントと呼ばれ、新しい認証プロセスは Kerberos web 認証と呼ばれます。 これにより、1つのアカウントを使用してすべての IIS サーバーを管理することができます。

詳細については、「 [CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

既定では、CsKerberosAccountAssignment には、画面上に非常に小さな出力が表示されます。 代わりに、コマンドレットによって返される情報は、HTML ファイルに書き込まれます。 このため、CsKerberosAccountAssignment を実行するたびに Verbose パラメーターと Report パラメーターを含めることをお勧めします。 Verbose パラメーターは、コマンドレットが実行されている間、画面上により詳細な出力を提供します。 レポートパラメーターを使用すると、CsKerberosAccountAssignment によって生成された HTML ファイルのファイルパスとファイル名を指定できます。 レポートパラメーターが含まれていない場合、HTML ファイルは [ユーザー] フォルダーに自動的に保存され、次のような名前が付けられます。 ce84964a-c4da-4622 2-ad34-361f、.html

また、CsKerberosAccountAssignment を実行するときに、サイト Id を指定する必要があります。 Kerberos アカウントは、サイトの範囲で割り当てられます。

次のコマンドは、CsKerberosAccountAssignment を実行し、出力を C:\\Logs\\KerberosTest という名前のファイルに保存します。

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

詳細については、「 [CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

CsKerberosAccountAssignment コマンドレットでは、成功または失敗を示す単純な通知は返されません。 代わりに、Internet Explorer を使用して生成された HTML ファイルを表示する必要があります。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に、テスト-CsKerberosAccountAssignment が失敗する可能性がある一般的な理由を示します。

  - 指定したサイト Id が間違っている可能性があります。 有効なサイト Id のリストを返すには、次のコマンドを使用します。
    
        Get-CsSite | Select-Identity Identity
    
    サイト Id は、通常、次のようになります。
    
    サイト: レドモンド

  - 指定したサイトには、Kerberos アカウントが割り当てられていない可能性があります。 次のようなコマンドを実行することで、サイトに Kerberos アカウントが割り当てられているかどうかを確認できます。
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - Kerberos アカウントのパスワードが有効でない可能性があります。 レポートで次のエラーメッセージが表示された場合は、おそらく Kerberos アカウントのパスワードを再設定する必要があります。
    
    InvalidKerberosConfiguration: Kerberos 構成が無効です。
    
    InvalidKerberosConfiguration: atl-cs001.litwareinc.com の Kerberos 構成が無効です。 期待される割り当て済みアカウント\\は litwareinc kerberostest です。 アカウントの有効期限が切れていないこと、およびコンピューター上の構成されたパスワードが、アカウントの Active Directory パスワードと一致していることを確認します。
    
    パスワードを設定するには、 [set-Csker"@ Accountpassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15)) " コマンドレットを使用します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

