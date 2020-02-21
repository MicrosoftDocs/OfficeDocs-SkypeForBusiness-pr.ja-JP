---
title: 'Lync Server 2013: アドレス帳のアクセスの検証'
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
ms.openlocfilehash: 665ee384afd85c4be5c82182691953e1c78c9659
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a>Lync Server 2013 でのアドレス帳へのアクセスの検証

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、Test-CsAddressBookService コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Test-CsAddressBookService コマンドレットを使用すると、ユーザーがアドレス帳のダウンロード Web サービスに接続できることを確認することができます。 コマンドレットを実行すると、指定されたプールのアドレス帳のダウンロード Web サービスに接続し、アドレス帳ファイルの場所を要求します。 アドレス帳のダウンロード Web サービスによってその場所が提供された場合、テストは成功したと見なされます。 要求が拒否された場合は、テストが失敗とみなされます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Test-CsAddressBookService コマンドレットは、事前構成されたテストアカウント (「Lync Server テストを実行するためのテストアカウントの設定」を参照)、または Lync Server に対して有効になっているユーザーのアカウントのいずれかを使用して実行できます。 このチェックをテストアカウントを使用して実行するには、テストする Lync Server プールの完全修飾ドメイン名 (FQDN) を指定するだけです。 次に例を示します。

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

実際のユーザーアカウントを使用してこのチェックを実行するには、まず、アカウント名とパスワードを含む Windows PowerShell credentials オブジェクトを作成する必要があります。 次に、その資格情報オブジェクトと、Test-CsAddressBookService を呼び出すときにアカウントに割り当てられた SIP アドレスを含める必要があります。

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

詳細については、「 [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

指定したユーザーがアドレス帳サービスに接続できる場合は、次のような出力が返されます。 Result プロパティは**Success**としてマークされています。

TargetUrihttps://lync-se.fabrikam.com:443/abs/handler

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間:00:00: 06.2260399

エラー

分析

指定したユーザーがこの接続を確立できない場合、結果は失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。

TargetUri

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間: 00:00:00

診断: ErrorCode = 4005, Source = 001.litwareinc.com,

Reason = 宛先 URI が SIP に対して有効になっていないか、または使用されていません

ない.

DiagnosticHeader ()

たとえば、指定されたユーザー ("Destination URI") が存在しないか、Lync Server が有効になっていないため、テストが失敗したことが上記の出力に示されます。 ユーザーアカウントが有効かどうかを確認し、次のようなコマンドを実行することによって、正しい SIP アドレスを指定したことを確認できます。

取得-CsUser-Identity "sip:kenmyer@litwareinc.com" |Select-Object SipAddress、Enabled

Test-CsAddressBookService が失敗した場合は、次のように詳細なパラメーターを含めて、テストを再実行することをお勧めします。

Test-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose

Verbose パラメーターが指定されている場合、指定されたユーザーが Lync Server にログオンできるかどうかを確認するときに、実行しようとした各アクションのステップバイステップのアカウントが返されます。 たとえば、このサンプル出力は、少なくともこの例の Test-CsAddressBookService がアドレス帳ファイルをダウンロードできることを示しています。

Http GET 要求を送信しています。

ファイルパス =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

試行回数 = 1

タイムアウト (ミリ秒) = 6万

ABS ファイルが正常にダウンロードされましたhttps://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

次に、Test-CsAddressBookService が失敗する可能性のある一般的な理由を示します。

  - 無効なユーザーアカウントが指定されています。 ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server で有効になっていません。 ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが Lync Server で現在有効になっていないことを意味します。

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

