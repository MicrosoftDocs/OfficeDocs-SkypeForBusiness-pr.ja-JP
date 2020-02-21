---
title: 'Lync Server 2013: Lync Server にログオンするユーザーの機能をテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 541870c2dc9bf5fde0ce2a339b07b894feb83082
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a>Lync Server 2013 にユーザーがログオンできるかどうかをテストする

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テスト用の登録コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Test-CsRegistration コマンドレットを使用すると、組織内のユーザーが Lync Server にログオンできることを確認できます。 テスト用の登録を実行すると、コマンドレットは、Lync Server へのテストユーザーのサインインを試み、成功した場合は、そのテストユーザーをシステムから切断します。 ユーザーによる操作なしに、また実際のユーザーに影響を及ぼすことなく、これらすべてが行われます。 たとえば、テストアカウント sip:kenmyer@litwareinc.com が実際の Lync Server アカウントを持つ実際のユーザーに対応しているとします。 この場合、テストは、実際の Ken Myer の業務を中断することなく実行されます。 Ken Myer test アカウントがシステムからログオフされると、そのユーザーは引き続きログオンしたままになります。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Test-CsRegistration コマンドレットを実行するには、事前に構成されたテストアカウント (Lync Server テストを実行するためのテストアカウントの設定を参照)、または Lync Server が有効になっているユーザーのアカウントのいずれかを使用します。 テストアカウントを使用してこのチェックを実行するには、テストする Lync Server レジストラープールの FQDN を指定するだけで済みます。 次に例を示します。

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

実際のユーザーアカウントを使用してこのチェックを実行するには、まず、アカウント名とパスワードを含む Windows PowerShell credentials オブジェクトを作成する必要があります。 その資格情報オブジェクトと、Test-CsRegistration を呼び出すときにアカウントに割り当てられた SIP アドレスを含める必要があります。

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

詳細については、「 [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

指定したユーザーが Lync Server にログオンしてからログオフすると、Result プロパティに成功のマークが付いた次のような出力が表示され**ます。**

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間:00:00: 06.8630376

エラー

分析

指定したユーザーがログインまたはログアウトできない場合は、結果がエラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間: 00:00:00

エラー: 404、見つかりません

診断: ErrorCode = 1003, source = litwareinc, Reason = ユーザーが実行しています

存在しない

DiagnosticHeader ()

たとえば、指定されたユーザーが見つからないため、テストが失敗したことが前の出力に示されます。 次のコマンドを実行することにより、SIP アドレスが有効かどうか (およびその SIP アドレスを割り当てられているユーザーが Lync Server に対して有効になっているかどうか) を確認できます。

    Get-CsUser "sip:kenmyer@litwareinc.com"

テスト用の登録が失敗した場合は、次のように詳細なパラメーターを含めて、テストを再実行することをお勧めします。

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose パラメーターが含まれている場合、指定されたユーザーが Lync Server にログオンできるかどうかを確認したときに、試行された各操作のステップバイステップのアカウントが返されます。 次に例を示します。

VERBOSE: ' Register ' アクティビティが開始されました。

登録要求の送信:

ターゲット Fqdn = atl-cs-011.litwareinc.com

ユーザー Sip アドレス = sip:kenmyer@litwareinc.com

レジストラーポート = 5061。

認証の種類 ' Trusted ' が選択されています。

例外 ' エンドポイントを登録できません。 ワークフロー STRegistrerWorkflow の実行中に発生した特定の理由については、「エラーコード」を参照してください。

例外の呼び出し履歴: SipAsyncResult'1 () (ThrowIfFailed)

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

以下に、テスト用の登録が失敗する主な理由を示します。

  - 正しくないユーザーアカウントが指定されています。 ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。 ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server に対して有効になっていないことを意味します。

  - 誤ったレジストラープールを指定しました。 次のコマンドを使用して、レジストラープールの Fqdn を返すことができます。
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - レジストラープールは現在使用できません。 プールに ping を実行し、応答があるかどうかを確認します。
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

