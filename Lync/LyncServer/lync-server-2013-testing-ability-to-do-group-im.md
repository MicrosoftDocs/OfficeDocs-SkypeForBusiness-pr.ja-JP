---
title: 'Lync Server 2013: グループ IM を実行するためのテスト機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97562d82f751280ec4d1a8f154af2b85ed2be128
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a>Lync Server 2013 でグループ IM を実行するためのテスト機能

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、Test-CsGroupIM コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Test-CsGroupIM コマンドレットは、組織内のユーザーがグループのインスタントメッセージングセッションを実行できるかどうかを確認します。 Test-CsGroupIM を実行すると、コマンドレットはテストユーザーのペアを Lync Server にサインインしようとします。 成功すると、Test-CsGroupIM は、最初のテスト ユーザーを使用して新しい会議を作成し、2 番目のユーザーを会議に招待します。 メッセージの交換後、両方のユーザーはシステムから切断されます。 すべてのユーザーが操作を行わなくても、実際のユーザーに影響を与えることなく、すべてが行われることに注意してください。 たとえば、テストアカウント sip:kenmyer@litwareinc.com が実際の Lync Server アカウントを持つ実際のユーザーに対応しているとします。 この場合、テストは、実際の Ken Myer の業務を中断することなく実行されます。 たとえば、Ken Myer のテスト アカウントがシステムからログオフした場合でも、Ken Myer 本人はログオン状態が保持されます。 同様に、実際の Ken Myer は会議に参加するための招待を受信しません。 その招待は、テスト アカウントに対して送信されて、テスト アカウントによって承諾されます。

詳細については、「 [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Test-CsGroupIM コマンドレットは、事前に構成されたテストアカウントのペア (「Lync Server テストを実行するためのテストアカウントの設定」を参照)、または Lync Server が有効になっている2人のユーザーのアカウントのいずれかを使用して実行できます。 このチェックをテストアカウントを使用して実行するには、テストする Lync Server プールの FQDN を指定するだけで済みます。 例:

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

実際のユーザーアカウントを使用してこのチェックを実行するには、Lync Server 管理シェルの資格情報オブジェクト (アカウント名とパスワードを含むオブジェクト) を、各アカウントに2つ作成する必要があります。 その後、Test-CsGroupIM を呼び出すときに、これらの資格情報オブジェクトと2つのアカウントの SIP アドレスを含める必要があります。

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

詳細については、「 [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

2人のユーザーがグループのインスタントメッセージングセッションを完了できた場合は、次のような出力が得られ、Result プロパティは Success としてマークされ**ます。**

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間:00:00: 06.3812203

エラー

分析

2人のユーザーがインスタントメッセージングセッションを完了できない場合、結果は失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間: 00:00:00

エラー: 404、見つかりません

診断: ErrorCode = 4005, Source = 001.litwareinc.com,

Reason = 宛先 URI が SIP に対して有効になっていないか、または使用されていません

ない.

DiagnosticHeader ()

以前の出力には、少なくとも1つのテストアカウントが有効でないためにテストが失敗したことが示されます。これは、アカウントが存在しないか、ユーザーが Lync Server に対して有効になっていないためです。 アカウントが存在することと、次のようなコマンドを実行することによって、アカウントが次のように有効になっているかどうかを確認できます。

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

Test-CsGroupIM に障害が発生した場合は、次のように詳細パラメーターを含めて、テストを再実行することをお勧めします。

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose パラメーターが指定されている場合、テスト-CsGroupIM は、指定されたユーザーがグループのインスタントメッセージングセッションに参加できるかどうかを確認したときに実行された各操作のステップバイステップのアカウントを返します。 たとえば、テストが失敗し、1つ以上のユーザーアカウントが有効でないと通知された場合は、Verbose パラメーターを使用してテストを再実行し、無効なユーザーアカウントを特定します。

登録要求の送信:

 ターゲット Fqdn = atl-cs-001.litwareinc.com

 ユーザー SIP アドレス = sip:kenmyer@litwareinc.com

 Register Port = 5061

認証の種類 ' IWA ' が選択されています。

例外 ' ログオンが拒否されました。 正しい資格情報が使用されていて、アカウントがアクティブであることを確認してください。

この例では、SIP アドレス sip:kenmyer@litwareinc.com を持つユーザーがログオンできなかったことを示しています。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

次に、Test-CsGroupIM が失敗する可能性がある一般的な理由を示します。

  - 正しくないユーザーアカウントが指定されています。 ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。 ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。
    
    取得-CsUser "sip:kenmyer@litwareinc.com" |Select-オブジェクトが有効
    
    Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server に対して有効になっていないことを意味します。

  - インスタントメッセージングサービスを利用できない可能性があります。 Lync Server を使用すると、アーカイブデータベースにアクセスできない場合に、インスタントメッセージングを使用できないようにシステムを構成できます。 これを確認するには、次のようなコマンドを実行します。
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    Blockonアーカイブエラーが True に設定されている場合は、アーカイブデータベースが使用可能かどうかを判断する必要があります。 次のコマンドを使用して、アーカイブデータベースの場所を返すことができます。
    
        Get-CsService -ArchivingDatabase

  - アーカイブサーバーが使用できない可能性があります。 次のコマンドを使用して、アーカイブサーバーの FQDN を取得できます。
    
        Get-CsService -ArchivingServer
    
    その後、適切なサーバーに ping を実行して、そのサーバーが使用可能であることを確認できます。 次に例を示します。
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

