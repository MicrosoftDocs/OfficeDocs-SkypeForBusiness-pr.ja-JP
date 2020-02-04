---
title: 'Lync Server 2013: 2 人のユーザー間の IM のテスト機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 201aceceadeba3c6c97530925273097fe039bc08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a>Lync Server 2013 での2人のユーザー間の IM のテスト機能

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
<p>Windows PowerShell のリモートインスタンスを使って実行する場合は、テスト用の Cgi コマンドレットを実行する権限を持つ RBAC の役割をユーザーに割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

テスト用の Cgi コマンドレットは、1組のテストユーザーがインスタントメッセージを交換できることを確認します。 呼び出された場合、テストユーザーのペアに対して Lync Server にログオンしようとすることで、テスト用の CsIM コマンドレットが開始されます。 2つのログオンが成功すると、コマンドレットによって2つのテストユーザーの間で IM セッションが開始されます。 (ユーザー1がユーザー2を IM セッションに招待し、ユーザー2が招待を承諾します)。2人のユーザー間でメッセージを交換できることを確認した後、テスト-CsIM によって IM セッションが終了し、両方のユーザーがシステムからログオフします。

詳細については、「[テスト-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

テスト用の Cgi コマンドレットを実行するには、定義済みのテストアカウントのペア (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照) を使用するか、Lync Server を有効にしている2人のユーザーのアカウントを使用します。 テストアカウントを使用してこの確認を実行するには、テストする Lync Server プールの FQDN を指定する必要があります。 次に例を示します。

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

実際のユーザーアカウントを使用してこのチェックを実行するには、2つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。 次に、テスト-CsIM を呼び出すときに、資格情報オブジェクトと2つのアカウントの SIP アドレスを含める必要があります。

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

詳細については、「[テスト-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

2人のユーザーがインスタントメッセージングセッションを終了すると、次のような出力が表示され、Result プロパティは Success とマークされ**ます。**

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待ち時間:00:00: 06.6630911

誤差

診断

テストユーザーがセッションを完了できなかった場合、結果はエラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待ち時間: 00:00:00

エラー: 504、サーバーのタイムアウト

診断: ErrorCode = 2、Source = litwareinc、Reason = を参照してください。

応答コードと理由の語句。

DiagnosticHeader の場合

たとえば、前の出力には、指定したユーザーが見つからなかったためにテストが失敗したことが示されます。 次のコマンドを実行して、SIP アドレスが有効であるかどうか (およびその SIP アドレスを割り当てられたユーザーが Lync Server に対して有効にしていたかどうか) を確認できます。

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

テスト用の Cgi が失敗した場合は、Verbose パラメーターも含めて、テストを再実行することをお勧めします。

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose パラメーターが含まれている場合は、2つのテストユーザーが IM セッションに参加しているかどうかを確認したときに、テスト用の CsIM によって、実行しようとした各操作のステップバイステップのアカウントが返されます。 たとえば、次のサンプル出力は、不適切なユーザー資格情報のセット (この場合は、不正なパスワード) がテスト用の CsIM に提供された場合に発生します。

登録リクエストの送信:

ターゲット Fqdn = atl-cs-011.litwareinc.com

ユーザー Sip アドレス = sip:kenmyer@litwareinc.com

レジストラーポート = 5061

認証の種類 ' IWA ' が選択されています。

Sip/atl に対する登録ヒット-.cs-litwareinc

"Register" アクティビティは "0.0601795" 秒で完了しました。

例外 ' ログオンは拒否されました。 正しい資格情報が使用されていて、アカウントがアクティブであることを確認します。 ワークフロー中に発生しました。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に、テスト用の Cgi が失敗する一般的な理由をいくつか示します。

  - 無効なユーザーアカウントが指定されました。 次のようなコマンドを実行すると、ユーザーアカウントが存在するかどうかを確認できます。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。 Lync Server でユーザーアカウントが有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server を有効にしていないことを意味します。

  - インスタントメッセージングサービスを利用できない可能性があります。 Lync Server では、アーカイブデータベースにアクセスできない場合に IM を使用できないように、システムを構成することができます。 これを確認するには、次のようなコマンドを実行します。
    
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

