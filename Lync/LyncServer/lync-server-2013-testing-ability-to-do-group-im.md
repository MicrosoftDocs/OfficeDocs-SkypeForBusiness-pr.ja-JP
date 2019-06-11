---
title: 'Lync Server 2013: グループ IM の実行機能をテストしています'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c371db385b29f68aa8cc9280a901d095c43f2ac2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a>Lync Server 2013 でグループ IM を実行するためのテスト機能

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
<p>Windows PowerShell のリモートインスタンスを使って実行する場合、ユーザーには、テスト/CsGroupIM コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

テスト用の CsGroupIM コマンドレットは、組織内のユーザーがグループのインスタントメッセージングセッションを実施できることを確認します。 テスト用の CsGroupIM を実行すると、コマンドレットによって、テストユーザーのペアを Lync Server にサインインしようとします。 成功した場合、テスト-CsGroupIM は、最初のテストユーザーを使用して新しい会議を作成し、その会議に参加するために2人目のユーザーを招待します。 メッセージの交換後、両方のユーザーがシステムから切断されます。 これは、ユーザーの操作なしで、実際のユーザーには影響を与えずに行われることに注意してください。 たとえば、テストアカウント sip:kenmyer@litwareinc.com は、実際の Lync Server アカウントを持っている実際のユーザーに対応しているものとします。 その場合は、実際の Ken Myer を中断することなく、テストが行われます。 たとえば、Ken Myer のテストアカウントがシステムからログオフした場合でも、Ken Myer はログイン状態を維持します。 同様に、本物の Ken Myer は電話会議に参加するための招待状を受け取りません。 この招待状は、テストアカウントに送信され、承認されます。

詳細については、「[テスト-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

テスト-CsGroupIM コマンドレットを実行するには、定義済みのテストアカウントのペア (「Lync Server テストを実行するためのテストアカウントのセットアップ」を参照) を使用するか、Lync Server を有効にしている2人のユーザーのアカウントを使用します。 テストアカウントを使用してこの確認を実行するには、テストする Lync Server プールの FQDN を指定する必要があります。 次に例を示します。

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

実際のユーザーアカウントを使用してこのチェックを実行するには、Lync Server 管理シェルの資格情報オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。 次に、テストまたは CsGroupIM を呼び出すときに、これらの資格情報オブジェクトと、2つのアカウントの SIP アドレスを含める必要があります。

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

詳細については、「[テスト-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

2人のユーザーがグループのインスタントメッセージングセッションを完了できる場合は、次のような結果として、Success とマークされた Result プロパティが表示され**ます。**

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待ち時間:00:00: 06.3812203

誤差

診断

2人のユーザーがインスタントメッセージングセッションを完了できなかった場合、結果はエラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待ち時間: 00:00:00

エラー: 404、見つかりません

診断: ErrorCode = 4005、Source = atl-cs-001.litwareinc.com、

理由 = ターゲット URI が SIP で有効になっていないか、

残っ.

DiagnosticHeader の場合

前回の出力では、アカウントが存在しないか、ユーザーが Lync Server を有効にしていないために、少なくとも1つのテストアカウントが無効であったため、テストが失敗したことが示されます。 アカウントが存在するかどうかを確認することができます。また、次のようなコマンドを実行することにより、そのアカウントが海里で有効になっているかどうかを確認できます。

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

テスト用の CsGroupIM が失敗した場合は、Verbose パラメーターも含めて、テストを再実行することをお勧めします。

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose パラメーターが含まれている場合は、指定したユーザーがグループのインスタントメッセージングセッションに参加できるかどうかを確認したときに、テスト用の CsGroupIM からステップバイステップのアカウントが返されます。 たとえば、テストが失敗し、1つ以上のユーザーアカウントが有効でないという通知が表示された場合は、Verbose パラメーターを使用してテストを再実行して、無効なユーザーアカウントを特定することができます。

登録リクエストの送信:

 ターゲット Fqdn = atl-cs-001.litwareinc.com

 ユーザー SIP アドレス = sip:kenmyer@litwareinc.com

 登録ポート = 5061

認証の種類 ' IWA ' が選択されています。

例外 ' ログオンは拒否されました。 正しい資格情報が使用されていて、アカウントがアクティブであることを確認します。

この例では、SIP アドレス sip:kenmyer@litwareinc.com を持っているユーザーがログオンできなかったことを示しています。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に、テスト用の CsGroupIM が失敗する一般的な理由をいくつか示します。

  - 指定したユーザーアカウントが間違っています。 次のようなコマンドを実行すると、ユーザーアカウントが存在するかどうかを確認できます。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。 ユーザーアカウントが Lync Server 用に有効になっていることを確認するには、次のようなコマンドを実行します。
    
    "Sip:kenmyer@litwareinc.com" というユーザーを取得する |選択-オブジェクトを有効にする
    
    Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server を有効にしていないことを意味します。

  - インスタントメッセージングサービスを利用できない可能性があります。 Lync Server では、アーカイブデータベースにアクセスできない場合にインスタントメッセージングが利用できないようにシステムを構成できます。 これを確認するには、次のようなコマンドを実行します。
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    Blockonアーカイブエラーが True に設定されている場合は、アーカイブデータベースを使用できるかどうかを判断する必要があります。 次のコマンドを使用して、アーカイブデータベースの場所を返すことができます。
    
        Get-CsService -ArchivingDatabase

  - アーカイブサーバーを利用できない可能性があります。 次のコマンドを使用して、アーカイブサーバーの FQDN を取得できます。
    
        Get-CsService -ArchivingServer
    
    次に、適切なサーバーに対して ping を実行し、そのサーバーが利用可能であることを確認できます。 例:
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

