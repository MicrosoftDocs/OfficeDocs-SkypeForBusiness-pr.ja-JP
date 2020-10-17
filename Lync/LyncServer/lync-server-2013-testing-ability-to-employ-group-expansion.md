---
title: 'Lync Server 2013: グループ拡張を使用するためのテスト能力'
description: 'Lync Server 2013: グループ拡張を使用するためのテスト機能。'
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
ms.openlocfilehash: 6267bc2099fc420c5c57e1ef80f4bf4491334938
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560793"
---
# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a>Lync Server 2013 でグループ拡張を採用するためのテスト能力

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsGroupExpansion コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Test-CsGroupExpansion コマンドレットを使用すると、グループ拡張が組織内で動作しているかどうかを判断できます。 グループ拡張が有効になっている場合、ユーザーは配布グループを連絡先として構成します。 つまり、それらのユーザーは、そのグループの個々のメンバーではなく、グループにメッセージをアドレス指定することによって、すべてのグループメンバーに同じインスタントメッセージを送信できます。 グループ拡張を使用すると、すべてのグループメンバーとその現在の状態をすばやく簡単に表示できます。

Test-CsGroupExpansion コマンドレットを使用して、グループの電子メールアドレスを使用して Active Directory 配布グループを指定します。 次に Test-CsGroupExpansion グループ拡張を使用してグループメンバーシップを取得し、取得したリストを、指定したグループ電子メールアドレスのメンバーシップと比較します。 2つのリストが一致する場合は、グループ拡張が正しく機能しています。 グループ拡張のテストは、サービス自体をテストする方法と、関連付けられた web サービスをテストする方法の2つで確認できます。

詳細については、「 [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Test-CsGroupExpansion コマンドレットを実行するには、事前に構成されたテストアカウントを使用するか (「Lync Server テストを実行するためのテストアカウントの設定」を参照してください)、Lync Server が有効になっているユーザーのアカウントを使用します。 このチェックをテストアカウントを使用して実行するには、テスト対象の Lync Server プールの FQDN と、有効な配布グループの電子メールアドレスを指定する必要があります。 以下に例を示します。

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

実際のユーザーアカウントを使用してこのチェックを実行するには、まず、アカウント名とパスワードを含む Lync Server credentials オブジェクトを作成する必要があります。 次に、システムが Test-CsGroupExpansion を呼び出すときに、その資格情報オブジェクトと、そのアカウントに割り当てられた SIP アドレスを含める必要があります。

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

詳細については、「 [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

指定したユーザーがグループ拡張を使用できる場合は、次のような出力が得られ、Result プロパティは Success としてマークされ **ます。**

TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間:00:00: 01.1234976

エラー

分析

指定したユーザーがグループ拡張を使用できない場合、結果は失敗として表示され、追加情報が Error および診断プロパティに記録されます。

TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間: 00:00:00

エラー

分析

Test-CsGroupExpansion: エンドポイントを登録できませんでした。 具体的な理由については、「ErrorCode」を参照してください。

前の出力には、指定したユーザーが Lync Server に登録できなかったためにテストが失敗したことが示されます。 これは通常、テストアカウントが存在しないか、Lync Server に対して有効になっていない場合に発生します。 アカウントが存在するかどうかを確認し、次のようなコマンドを実行することによって、そのアカウントが有効になっているかどうかを確認できます。

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

Test-CsGroupExpansion が失敗した場合は、次のようにして、Verbose パラメーターを含むテストを再実行することをお勧めします。

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

Verbose パラメーターが含まれている場合 Test-CsGroupExpansion は、指定されたユーザーが Lync Server にログオンできるかどうかを確認したときに実行された各アクションのステップバイステップのアカウントを返します。 たとえば、次の出力は、指定された配布グループが見つからなかったことを示しています。

Web チケットを取得しようとしています。

Web サービス url: https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc

NTLM/Kerb 認証を使用します。

GetWebTicketActivity が完了しました。

' VerifyDistributionList ' アクティビティが開始されました。

DLX Web サービス応答ステータスは: NotFound です。

' VerifyDistributionList ' アクティビティは、' 0.2597923 ' 秒で完了しました。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

Test-CsGroupExpansion が失敗する可能性のある一般的な理由を次に示します。

  - 無効なユーザーアカウントが指定されています。 ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。 ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server に対して有効になっていないことを意味します。

  - グループの拡張が無効になっている可能性があります。 グループ拡張を無効にすることができます。 グループ拡張が無効になっている場合、Test-CsGroupExpansion コマンドレットは失敗します。 グループ拡張が有効になっているかどうかを判断するには、次のようなコマンドを使用します。
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

