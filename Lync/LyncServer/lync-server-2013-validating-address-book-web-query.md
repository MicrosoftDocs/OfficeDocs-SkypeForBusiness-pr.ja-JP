---
title: 'Lync Server 2013: アドレス帳 web クエリの検証'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7306b56fca8feada05ee895eea64dc2aecfafb0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42115110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a>Lync Server 2013 でのアドレス帳 web クエリの検証

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テスト-CsAddressBookWebQuery コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Test-CsAddressBookWebQuery コマンドレットを使用すると、管理者は、ユーザーがアドレス帳 Web クエリサービスを使用して特定の連絡先を検索できることを確認できます。 コマンドレットを実行すると、最初に認証を行うために Web チケットサービスに接続されます。 認証が成功した場合、コマンドレットはアドレス帳 Web クエリサービスに接続し、指定された連絡先を検索します。 その連絡先が見つかった場合、コマンドレットはその情報をローカルコンピューターに返します。 このテストは、これらの手順をすべて完了できる場合にのみ、成功としてマークされます。

詳細については、「 [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Test-CsAddressBookWebQuery コマンドレットは、事前に構成されたテストアカウント (「Lync Server テストを実行するためのテストアカウントの設定」を参照)、または Lync Server が有効になっているユーザーのアカウントのいずれかを使用して実行できます。 このチェックをテストアカウントを使用して実行するには、Lync Server プールの FQDN と、検索の対象として機能するユーザーの SIP アドレスを指定する必要があります。 次に例を示します。

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

実際のユーザーアカウントを使用してこのチェックを実行するには、有効なユーザー名とパスワードを含む Windows PowerShell 資格情報オブジェクトを作成する必要があります。 次に、この資格情報オブジェクトと、コードで Test-CsAddressBookWebQuery を呼び出したときにアカウントに割り当てられた SIP アドレスを含める必要があります。

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

詳細については、「 [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

指定したユーザーがアドレス帳サービスに接続して、対象のユーザーアドレスを取得できる場合は、次のような出力が返されます。 Result プロパティには、Success というマークが付けられています。

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間:00:00: 06.2611356

エラー

分析

指定したユーザーが接続できない場合、またはターゲットユーザーのアドレスを取得できない場合、結果は失敗として表示され、追加情報が Error および診断プロパティに記録されます。

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間: 00:00:00

エラー: アドレス帳 Web サービスの要求が応答コードを使用して失敗しました

NoEntryFound。

分析

前の出力には、ターゲットユーザーが見つからないためにテストが失敗したことが示されます。 次のようなコマンドを実行することにより、有効な SIP アドレスが Test-CsAddressBookWebQuery に渡されたかどうかを判断できます。

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

Test-CsAddressBookWebQuery が失敗した場合は、次のように詳細なパラメーターを含めて、テストを再実行することをお勧めします。

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

Verbose パラメーターを指定すると、指定されたユーザーが Lync Server にログオンできるかどうかを確認している間に実行しようとした各操作のステップごとのアカウントが返されます。 たとえば、次の出力は、Test-CsAddressBookWebQuery がアドレス帳サービスに接続できたが、対象の SIP アドレスを見つけられなかったことを示しています。

' QueryAddressBookWebService ' アクティビティを開始しました。

アドレス帳 Web クエリサービスを呼び出す。 ABWS URL =

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

アドレス帳のクエリ例外: アドレス帳 Web サービスの要求が失敗しました。応答コードの NoEntryFound が見つかりませんでした。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

次に、Test-CsAddressBookWebQuery が失敗する主な理由を示します。

  - 無効なユーザーアカウントが指定されています。 ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server で有効になっていません。 ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが Lync Server で現在有効になっていないことを意味します。

  - ターゲットユーザーがアドレス帳に登録されていない可能性があります。

  - アドレス帳が完全に更新され、レプリケートされていない可能性があります。 次のコマンドを実行して、組織内のすべてのアドレス帳サーバーを強制的に更新することができます。
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

