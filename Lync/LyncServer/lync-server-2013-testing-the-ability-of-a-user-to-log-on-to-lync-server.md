---
title: 'Lync Server 2013: ユーザーが Lync Server にログオンする機能をテストする'
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
ms.openlocfilehash: 4fb1d0af8a5191c7e0af1ffe3319c426c116b586
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a>Lync Server 2013 へのユーザーのログオン機能のテスト

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、CsRegistration コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

テスト環境登録コマンドレットを使用すると、組織内のユーザーが Lync Server にログオンできることを確認できます。 テスト用の登録を実行するときに、コマンドレットはテストユーザーへのサインインを Lync Server に試み、成功した場合は、テストユーザーをシステムから切断します。 これは、ユーザーの操作なしで、実際のユーザーには影響を与えずに行われます。 たとえば、テストアカウント sip:kenmyer@litwareinc.com は、実際の Lync Server アカウントを持っている実際のユーザーに対応しているものとします。 その場合は、実際の Ken Myer を中断することなく、テストが行われます。 Ken Myer のテストアカウントがシステムからログオフすると、Ken Myer がログイン状態を維持します。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

指定したテストアカウント (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照) または Lync Server を有効にしているユーザーのアカウントを使用して、CsRegistration コマンドレットを実行します。 テストアカウントを使用してこのチェックを実行するには、テストする Lync Server レジストラープールの FQDN を指定する必要があります。 次に例を示します。

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

実際のユーザーアカウントを使用してこのチェックを実行するには、最初に、アカウント名とパスワードを含む Windows PowerShell 資格情報オブジェクトを作成する必要があります。 次に、資格情報オブジェクトと、テスト用のユーザーアカウントに割り当てられた SIP アドレスを指定する必要があります。

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

詳細については、「 [CsRegistration のテスト](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration)」コマンドレットのヘルプドキュメントを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

指定したユーザーが Lync Server にログオンして (その後、ログオフしてから)、Lync Server にログオンできる場合は、次のような結果として、Success とマークされた Result プロパティが出力され**ます。**

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待ち時間:00:00: 06.8630376

誤差

診断

指定したユーザーがログインまたはログアウトできない場合は、結果が失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待ち時間: 00:00:00

エラー: 404、見つかりません

診断: ErrorCode = 1003、source = atl-ws-01、litwareinc、Reason = User による

存在しない

DiagnosticHeader の場合

たとえば、前の出力には、指定したユーザーが見つからなかったためにテストが失敗したことが示されます。 次のコマンドを実行して、SIP アドレスが有効であるかどうか (およびその SIP アドレスを割り当てられたユーザーが Lync Server に対して有効になっているかどうか) を確認できます。

    Get-CsUser "sip:kenmyer@litwareinc.com"

テスト用の登録が失敗した場合は、Verbose パラメーターも含めて、テストを再実行することをお勧めします。

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose パラメーターが含まれている場合は、指定されたユーザーが Lync Server にログオンする機能を確認したときに、テスト/CsRegistration によって実行された各操作のステップバイステップのアカウントが返されます。 次に例を示します。

VERBOSE: ' Register ' アクティビティが開始されました。

登録リクエストの送信:

ターゲット Fqdn = atl-cs-011.litwareinc.com

ユーザー Sip アドレス = sip:kenmyer@litwareinc.com

レジストラーポート = 5061。

[Authentication Type ' Trusted '] が選択されています。

例外 ' エンドポイントを登録できません。 STRegistrerWorkflow の実行中に発生した特定の理由のエラーコードを参照してください。

例外コールスタック: SipAsyncResult'1 () を呼び出します。 ThrowIfFailed ()

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に、テスト用の登録が失敗する一般的な理由をいくつか示します。

  - 指定したユーザーアカウントが間違っています。 次のようなコマンドを実行すると、ユーザーアカウントが存在するかどうかを確認できます。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。 Lync Server でユーザーアカウントが有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server を有効にしていないことを意味します。

  - 指定したレジスタプールが正しくありません。 レジストラープールの Fqdn は、次のコマンドを使用して返すことができます。
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - レジストラープールは現在利用できません。 プールに対して ping を実行し、応答するかどうかを確認します。
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

