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
ms.openlocfilehash: 145a2849d8b87f0f19559583e94edb5e895f89db
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500494"
---
# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a>Lync Server 2013 で2人のユーザー間の IM のテスト機能

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsIM コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Test-CsIM コマンドレットは、テストユーザーのペアがインスタントメッセージを交換できるかどうかを確認します。 呼び出された場合、Test-CsIM コマンドレットは、一連のテストユーザーを Lync Server にログオンすることで開始します。 2回のログオンが成功すると、コマンドレットは2つのテストユーザー間で IM セッションを開始します。 (ユーザー1がユーザー2を IM セッションに招待し、ユーザー2が招待を受け入れます)。2人のユーザーの間でメッセージを交換できることを確認した後 Test-CsIM、IM セッションを終了し、両方のユーザーをシステムからログオフします。

詳細については、「 [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Test-CsIM コマンドレットを実行するには、事前に構成された一連のテストアカウントを使用します (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照してください)。または、Lync Server が有効になっている2人のユーザーのアカウント。 このチェックをテストアカウントを使用して実行するには、テストする Lync Server プールの FQDN を指定するだけで済みます。 以下に例を示します。

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

実際のユーザーアカウントを使用してこのチェックを実行するには、2つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。 次に、テスト-CsIM を呼び出すときに、これらの資格情報オブジェクトと2つのアカウントの SIP アドレスを含める必要があります。

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

詳細については、「 [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

2人のユーザーがインスタントメッセージングセッションを完了できる場合は、次のような出力が得られます。 Result プロパティは Success としてマークされてい **ます。**

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間:00:00: 06.6630911

エラー

分析

テストユーザーがセッションを完了できない場合は、結果がエラーとして表示され、追加情報が Error および診断プロパティに記録されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間: 00:00:00

エラー: 504、サーバーのタイムアウト

診断: ErrorCode = 2, Source = litwareinc, Reason = 「」を参照

応答コードと理由の語句。

DiagnosticHeader ()

たとえば、指定されたユーザーが見つからないため、テストが失敗したことが前の出力に示されます。 次のコマンドを実行することにより、SIP アドレスが有効かどうか (およびその SIP アドレスを割り当てられたユーザーが Lync Server を使用したかどうか) を判断できます。

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

Test-CsIM が失敗した場合は、次のようにして、Verbose パラメーターを含むテストを再実行することをお勧めします。

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose パラメーターが指定されている場合、Test-CsIM は、2つのテストユーザーが IM セッションに参加できるかどうかを確認したときに実行された各アクションのステップバイステップのアカウントを返します。 たとえば、次のサンプル出力は、誤ったユーザー資格情報のセット (この場合は間違ったパスワード) がテスト用に提供されたときに発生します。

登録要求の送信:

ターゲット Fqdn = atl-cs-011.litwareinc.com

ユーザー Sip アドレス = sip:kenmyer@litwareinc.com

レジストラーポート = 5061

認証の種類 ' IWA ' が選択されています。

Sip/atl-ws-01 に対する登録ヒット。 litwareinc

' Register ' アクティビティは、' 0.0601795 ' 秒で完了しました。

例外 ' ログオンが拒否されました。 正しい資格情報が使用されており、アカウントがアクティブであることを確認してください。 ワークフローの実行中に発生した。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

Test-CsIM が失敗する可能性のある一般的な理由を次に示します。

  - 無効なユーザーアカウントが指定されました。 ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。 ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが Lync Server に対して有効になっていないことを意味します。

  - インスタントメッセージングサービスを利用できない可能性があります。 Lync Server を使用すると、アーカイブデータベースにアクセスできない場合に IM を使用できないようにシステムを構成できます。 これを確認するには、次のようなコマンドを実行します。
    
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

