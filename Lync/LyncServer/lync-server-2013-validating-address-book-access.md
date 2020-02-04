---
title: 'Lync Server 2013: アドレス帳へのアクセスを検証する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96fe45f1491ca518a6985b0c15f8bcc229bd7f8c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a>Lync Server 2013 でのアドレス帳へのアクセスを検証する

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
<p>Windows PowerShell のリモートインスタンスを使って実行する場合、ユーザーには、テスト/CsAddressBookService コマンドレットを実行するアクセス許可が与えられた RBAC の役割を割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

テスト-CsAddressBookService コマンドレットを使うと、ユーザーがアドレス帳のダウンロード Web サービスに接続できることを確認することができます。 コマンドレットを実行すると、指定されたプールのアドレス帳ダウンロード Web サービスに接続し、アドレス帳ファイルの場所を要求します。 アドレス帳のダウンロード Web サービスがこの場所を提供した場合、テストは成功したと見なされます。 要求が拒否された場合、テストは失敗したと見なされます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

テスト-CsAddressBookService コマンドレットは、事前に定義されたテストアカウント (「Lync Server テストを実行するためにテストアカウントをセットアップする」を参照)、または Lync Server が有効になっているユーザーのアカウントを使用して実行できます。 テストアカウントを使用してこのチェックを実行するには、テスト対象の Lync サーバープールの完全修飾ドメイン名 (FQDN) を指定する必要があります。 次に例を示します。

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

実際のユーザーアカウントを使用してこのチェックを実行するには、最初に、アカウント名とパスワードを含む Windows PowerShell 資格情報オブジェクトを作成する必要があります。 次に、ユーザーの資格情報オブジェクトと、CsAddressBookService を呼び出すときにアカウントに割り当てられた SIP アドレスを含める必要があります。

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

詳細については、「[テスト-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

指定したユーザーがアドレス帳サービスに接続できる場合は、次のような結果が返されます。これには、Result プロパティが**Success**とマークされています。

TargetUri :https://lync-se.fabrikam.com:443/abs/handler

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待ち時間:00:00: 06.2260399

誤差

診断

指定したユーザーがこの接続を確立できない場合、結果は失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。

TargetUri :

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待ち時間: 00:00:00

診断: ErrorCode = 4005、Source = atl-cs-001.litwareinc.com、

理由 = ターゲット URI が SIP で有効になっていないか、

残っ.

DiagnosticHeader の場合

たとえば、上記の出力では、指定されたユーザー ("送信先 URI") が存在しないか、Lync Server が有効になっていないため、テストが失敗したことが示されます。 次のようなコマンドを実行して、ユーザーアカウントが有効であるかどうかを確認し、正しい SIP アドレスを入力したことを確認できます。

"Sip:kenmyer@litwareinc.com" というユーザー Id を取得するSelect-Object SipAddress、Enabled

テスト用の Addressaddressbookservice が失敗した場合は、Verbose パラメーターなどのテストを再実行することをお勧めします。

テスト-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose

Verbose パラメーターが含まれている場合は、指定したユーザーが Lync Server にログオンする機能を確認したときに実行される各操作のステップバイステップのアカウントが返されます。 たとえば、次の例の出力では、少なくともこの例で使用されている [テスト-CsAddressBookService] がアドレス帳ファイルをダウンロードできることを示しています。

Http GET 要求を送信しています。

ファイルパス =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

試行回数 = 1

タイムアウト (ミリ秒) = 6万

ABS ファイルが正常にダウンロードされましたhttps://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に、テスト-CsAddressBookService が失敗する可能性がある一般的な理由を示します。

  - 無効なユーザアカウントを指定しました。 次のようなコマンドを実行すると、ユーザーアカウントが存在するかどうかを確認できます。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server では有効になっていません。 Lync Server のユーザーアカウントが有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server に対して有効になっていないことを意味します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

