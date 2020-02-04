---
title: 'Lync Server 2013: グループ展開を使用するためのテスト機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d79c5432bc2efca0d3a958d3837793eaf227b251
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a>Lync Server 2013 でグループ展開を使用するためのテスト機能

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、CsGroupExpansion コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

テスト用の CsGroupExpansion コマンドレットを使用すると、グループの展開が組織内で機能しているかどうかを確認できます。 グループの拡張が有効になっている場合、ユーザーは配布グループを連絡先として構成します。 つまり、これらのユーザーは、グループの個々のメンバーではなく、グループにメッセージをアドレス指定して、すべてのグループメンバーに同じインスタントメッセージを送信することができます。 グループ展開では、すべてのグループメンバーとその現在の状態をすばやく簡単に表示できます。

テスト用の CsGroupExpansion コマンドレットを使用して、グループのメールアドレスを使って Active Directory 配布グループを指定します。 テスト-CsGroupExpansion では、グループの展開を使用してグループメンバーシップを取得し、取得したリストと、指定したグループメールアドレスのメンバーシップを比較します。 2つのリストが一致する場合、グループの展開は正常に機能しています。 グループの展開をテストするには、サービス自体をテストするか、関連付けられた web サービスをテストするという2つの方法があります。

詳細については、「 [CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

テスト用の CsGroupExpansion コマンドレットを実行するには、事前に定義されたテストアカウント (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照) または Lync Server を有効にしたユーザーのアカウントを使用します。 テストアカウントを使用してこのチェックを実行するには、テスト対象の Lync Server プールの FQDN と、有効な配布グループのメールアドレスを指定する必要があります。 次に例を示します。

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

実際のユーザーアカウントを使用してこのチェックを実行するには、まず、アカウント名とパスワードを含む Lync Server 資格情報オブジェクトを作成する必要があります。 次に、資格情報オブジェクトと、システムによってテスト CsGroupExpansion が呼び出されたときにアカウントに割り当てられる SIP アドレスを含める必要があります。

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

詳細については、「 [CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

指定したユーザーがグループ拡張を使用できる場合は、次のような結果として、Success とマークされた Result プロパティが表示され**ます。**

TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待ち時間:00:00: 01.1234976

誤差

診断

指定したユーザーがグループの展開を使用できない場合は、結果がエラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。

TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待ち時間: 00:00:00

誤差

診断

テスト-CsGroupExpansion: エンドポイントは登録できませんでした。 具体的な理由については、「エラーコード」をご覧ください。

以前の出力では、指定されたユーザーが Lync Server に登録できなかったため、テストが失敗したことが示されます。 これは通常、テストアカウントが存在しないか、Lync Server に対して有効になっていない場合に発生します。 アカウントが存在するかどうかを確認し、次のようなコマンドを実行して、nm-ocs-14-3 のアカウントが有効になっているかどうかを確認できます。

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

テスト用の CsGroupExpansion 展開に失敗した場合は、Verbose パラメーターも含めて、テストを再実行することをお勧めします。

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

Verbose パラメーターが含まれている場合は、指定したユーザーが Lync Server にログオンする機能を確認したときに実行される各操作のステップバイステップのアカウントが返されます。 たとえば、次の出力は、指定された配布グループが見つからなかったことを示します。

Web チケットを取得しようとしています。

Web サービスの url:https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc

NTLM/Kerb auth を使用しています。

GetWebTicketActivity が完了しました。

' VerifyDistributionList ' アクティビティが開始されました。

DLX Web サービスの応答状態: NotFound。

' VerifyDistributionList ' アクティビティは "0.2597923" 秒で完了しました。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に、テスト用の CsGroupExpansion 展開が失敗する可能性がある一般的な理由を示します。

  - 無効なユーザアカウントを指定しました。 次のようなコマンドを実行すると、ユーザーアカウントが存在するかどうかを確認できます。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。 ユーザーアカウントが Lync Server 用に有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server を有効にしていないことを意味します。

  - グループの拡張が無効になっている可能性があります。 グループの拡張機能をオフにすることができます。 グループの拡張が無効になっている場合、テスト用の CsGroupExpansion コマンドレットは失敗します。 グループの展開が有効であるかどうかを判断するには、次のようなコマンドを使用します。
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

