---
title: 'Lync Server 2013: ダイヤルイン会議セッションのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11a5126d0555e39c5e0c4637a70939227c787299
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a>Lync Server 2013 でのダイヤルイン会議セッションのテスト

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、Test-CsDialInConferencing コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Test-Csdial Inコンファレンスコマンドレットは、ユーザーがダイヤルイン会議に参加できるかどうかを確認します。 テスト用のダイヤルイン会議は、テストユーザーをシステムにログオンすることによって動作します。 ログオンに成功すると、コマンドレットはユーザーの資格情報とアクセス許可を使用して、使用可能なすべてのダイヤルイン会議アクセス番号を試します。 各ダイヤルイン試行の成功または失敗が表示されます。その後、テストユーザーは Lync Server からログオフされます。テスト-Csdial In会議では、適切な接続が可能であることのみが確認されます。 このコマンドレットでは、他のユーザーが参加できる電話会議は、実際には作成されません。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Test-CsDialInConferencing コマンドレットは、事前構成されたテストアカウント (「Lync Server テストを実行するためのテストアカウントの設定」を参照)、または Lync Server が有効になっているユーザーのアカウントのいずれかを使用して実行できます。 テストアカウントを使用してこのチェックを実行するには、テストする Lync Server プールの FQDN を指定するだけで済みます。 次に例を示します。

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

実際のユーザーアカウントを使用してこのチェックを実行するには、アカウント名とパスワードを含む Windows PowerShell 資格情報オブジェクトを作成する必要があります。 次に、その資格情報オブジェクトとアカウント SIP アドレスを呼び出し元のテスト-Csダイヤルイン会議に含める必要があります。

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

詳細については、「 [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

指定したユーザーが Lync Server にログオンして、使用可能なダイヤルイン会議アクセス番号のいずれかを使用して接続すると、次のような出力が得られます。 Result プロパティは Success としてマークされてい**ます。**

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間:00:00: 06.8630376

エラー

分析

指定したユーザーがこの接続を確立できない場合は、結果がエラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間: 00:00:00

エラー: ログオンが拒否されました。 適切な資格情報があることを確認する

使用されており、アカウントがアクティブである。

内部例外: NegotiateSecurityAssociation が失敗しました。エラー:-

2146893044

分析

上記の出力は、テストユーザーが Lync Server 自体へのアクセスを拒否されたことを示しています。 これは、通常、Test-CsDialInConferencing に渡されたユーザー資格情報が無効であったことを意味します。 その後で、Windows PowerShell 資格情報オブジェクトを再作成する必要があります。 ユーザーアカウントのパスワードを取得することもできますが、次のようなコマンドを使用して SIP アドレスを確認できます。

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

次に、テスト用のダイヤルイン会議が失敗する主な理由を示します。

  - 無効なユーザーアカウントが指定されました。 ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。 ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server に対して有効になっていないことを意味します。

  - ダイヤルイン会議アクセス番号が正しくない可能性があります。 次のコマンドを使用して、現在構成されているダイヤルイン会議アクセス番号の一覧を返すことができます。
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

