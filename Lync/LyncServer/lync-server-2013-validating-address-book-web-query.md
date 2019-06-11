---
title: 'Lync Server 2013: アドレス帳の web クエリの検証'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44c43b4332be67bb164f21a2bb07459d61b23e85
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a>Lync Server 2013 でのアドレス帳 web クエリの検証

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
<p>Windows PowerShell のリモートインスタンスを使って実行する場合、ユーザーには、テスト-CsAddressBookWebQuery コマンドレットを実行するアクセス許可が与えられた RBAC の役割を割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

ユーザーがアドレス帳 Web クエリサービスを使用して特定の連絡先を検索できることを、管理者が確認できるようにします。 コマンドレットを実行すると、まず、テスト用の Web チケットサービスに接続して認証されます。 認証が成功すると、コマンドレットはアドレス帳 Web クエリサービスに接続し、指定された連絡先を検索します。 その連絡先が見つかった場合、コマンドレットはローカルコンピューターにその情報を返します。 テストは、すべての手順が完了した場合にのみ成功としてマークされます。

詳細については、「[テスト-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

テスト-CsAddressBookWebQuery コマンドレットは、事前に定義されたテストアカウント (「Lync Server テストを実行するためにテストアカウントをセットアップする」を参照)、または Lync Server を有効にしているユーザーのアカウントを使用して実行できます。 テストアカウントを使用してこのチェックを実行するには、Lync Server プールの FQDN と、検索のターゲットとして機能しているユーザーの SIP アドレスを指定する必要があります。 次に例を示します。

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

実際のユーザーアカウントを使用してこのチェックを実行するには、有効なユーザー名とパスワードを含む Windows PowerShell 資格情報オブジェクトを作成する必要があります。 次に、コードが Test-CsAddressBookWebQuery を呼び出したときに、アカウントに割り当てられている資格情報オブジェクトと SIP アドレスを含める必要があります。

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

詳細については、「[テスト-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

指定したユーザーがアドレス帳サービスに接続し、ターゲットユーザーアドレスを取得できる場合は、次のような出力が返されます。これは、Success とマークされた Result プロパティによって返されます。

TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待ち時間:00:00: 06.2611356

誤差

診断

指定したユーザーが接続できない場合、またはターゲットのユーザーアドレスを取得できない場合は、結果がエラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。

TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待ち時間: 00:00:00

エラー: アドレス帳 Web サービスの要求は応答コードで失敗しました

NoEntryFound。

診断

前の出力では、ターゲットユーザーが見つからなかったため、テストが失敗したことが示されます。 次のようなコマンドを実行することで、有効な SIP アドレスが CsAddressBookWebQuery に渡されたかどうかを確認できます。

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

テスト-CsAddressBookWebQuery が失敗した場合は、Verbose パラメーターも含めて、テストを再実行することをお勧めします。

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

Verbose パラメーターが含まれている場合は、指定したユーザーが Lync Server にログオンする機能を確認している間に、テスト-CsAddressBookWebQuery によって実行された各操作のステップバイステップのアカウントが返されます。 たとえば、次の出力は、テスト-CsAddressBookWebQuery がアドレス帳サービスに接続できましたが、ターゲット SIP アドレスが見つかりませんでした。

' QueryAddressBookWebService ' アクティビティが開始されました。

アドレス帳 Web クエリサービスを呼び出します。 ABWS URL =

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

アドレス帳のクエリ例外: アドレス帳 Web サービスの要求は、応答コード NoEntryFound で失敗しました。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に、テストまたは CsAddressBookWebQuery が失敗する可能性がある一般的な理由を示します。

  - 無効なユーザアカウントを指定しました。 次のようなコマンドを実行すると、ユーザーアカウントが存在するかどうかを確認できます。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server では有効になっていません。 Lync Server のユーザーアカウントが有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server に対して有効になっていないことを意味します。

  - ターゲットユーザーがアドレス帳に登録されていない可能性があります。

  - アドレス帳が完全に更新されて複製されていない可能性があります。 次のコマンドを実行して、組織内のすべてのアドレス帳サーバーを強制的に更新することができます。
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

