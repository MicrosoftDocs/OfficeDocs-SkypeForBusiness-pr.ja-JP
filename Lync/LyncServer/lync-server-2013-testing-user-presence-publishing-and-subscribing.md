---
title: 'Lync Server 2013: ユーザープレゼンスの発行とサブスクライブのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user presence publishing and subscribing
ms:assetid: 27694c71-8e63-4aa4-b49f-fa06ccb81949
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743832(v=OCS.15)
ms:contentKeyID: 63969587
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b76cd47ccfe35cecf7b7e9182aeadccc37436bc5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a>Lync Server 2013 でユーザープレゼンスの発行とサブスクライブをテストする

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テスト-CsPresence コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

テスト-CsPresence は、テストユーザーのペアが Lync Server にログオンし、プレゼンス情報を交換できるかどうかを判断するために使用されます。 これを行うために、コマンドレットを実行して、この 2 人のユーザーをシステムにログオンさせます。 両方のログオンが正常に行われたら、1 番目のテスト ユーザーが、2 番目のテスト ユーザーからプレゼンス情報を受信するよう依頼します。 2 番目のユーザーがこの情報を公開したら、Test-CsPresence を実行して、情報が 1 番目のユーザーに正常に転送されたことを確認します。 プレゼンス情報の交換後、2つのテストユーザーが Lync Server からログオフされます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Test-CsPresence コマンドレットを実行するには、事前に構成されたテストアカウントのペア (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照) を使用するか、Lync Server が有効になっている2人のユーザーのアカウントを使用します。 このチェックをテストアカウントを使用して実行するには、テストする Lync Server プールの FQDN を指定するだけで済みます。 次に例を示します。

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

実際のユーザーアカウントを使用してこのチェックを実行するには、2つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。 次に、これらの資格情報オブジェクトと、テストを呼び出すときに2つのアカウントの SIP アドレスを含める必要があります。

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

詳細については、「 [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence)コマンドレット」のヘルプドキュメントを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

指定したユーザーがプレゼンス情報を交換できる場合は、次のような出力が得られます。 Result プロパティは Success としてマークされてい**ます。**

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間:00:00: 06.3280315

エラー

分析

2人のユーザーがプレゼンス情報を交換できない場合、結果は失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間: 00:00:00

エラー: 404、見つかりません

診断: ErrorCode = 4005, Source = 001.litwareinc.com,

Reason = 宛先 URI が SIP に対して有効になっていないか、または使用されていません

ない.

DiagnosticHeader ()

たとえば、次の2つのユーザーアカウントのうち少なくとも1つが無効であるためにテストが失敗したことが、上記の出力に示されています。アカウントが存在しないか、Lync Server に対して有効になっていません。 アカウントが存在するかどうかを確認し、次のようなコマンドを実行することによって、そのアカウントが Lync Server に対して有効になっているかどうかを確認できます。

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

テストのために失敗した場合は、次のように詳細なパラメーターを含めて、テストを再実行することをお勧めします。

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose パラメーターが指定されている場合は、指定したユーザーが Lync Server にログオンできるかどうかを確認したときに実行された各操作のステップごとのアカウントが返されます。 次に例を示します。

不明に対する登録要求ヒット

' Register ' アクティビティは、' 0.0345791 ' 秒で完了しました。

' SelfSubscribeActivity ' アクティビティが開始されました。

' SelfSubscribeActivity ' アクティビティは、' 0.0041174 ' 秒で完了しました。

' SubscribePresence ' アクティビティが開始されました。

' SubscribePresence ' アクティビティは、' 0.0038764 ' 秒で完了しました。

' PublishPresence ' アクティビティが開始されました。

例外 ' プレゼンス通知が25秒以内に受信されません。 ' ワークフローのワークフローの実行についてのワークフローが発生しました。

25秒以内にプレゼンス通知が受信されなかった場合、ネットワークの問題が原因で情報を交換できないことを示している可能性があります。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

次に、テスト、CsPresence 失敗する主な理由を示します。

  - 正しくないユーザーアカウントが指定されています。 ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。 ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが Lync Server に対して有効になっていないことを意味します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

