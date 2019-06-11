---
title: 'Lync Server 2013: Web scheduler のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: beb4030a87302c8abaaba9418eaba06b831ed8d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-web-scheduler-in-lync-server-2013"></a>Lync Server 2013 で Web scheduler をテストする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-11-03_


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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、 <strong>CsWebScheduler</strong>コマンドレットを実行するアクセス許可が与えられた RBAC の役割を割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

**テスト用の webscheduler**コマンドレットを使用すると、特定のユーザーが Web Scheduler を使って会議をスケジュールできるかどうかを判断できます。 Web Scheduler は、Outlook を実行していないユーザーがオンライン会議をスケジュールすることを可能にします。 この新機能 (Microsoft Lync Server 2010 リソースキットに含まれていた Web Scheduler ツールに含まれていた機能が組み込まれています) では、ユーザーは次のことを行うことができます。

  - 新しいオンライン会議をスケジュールします。

  - 自分がスケジュールしたすべての会議を一覧表示します。

  - 既存の会議を表示または変更する。

  - 既存の会議を削除します。

  - 事前に構成された SMTP メールサーバーを使用して、会議の出席者にメール招待状を送信します。

  - 既存の会議に参加します。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

次の例では、プール atl-cs-001.litwareinc.com の Web Scheduler を確認します。 このコマンドは、プール atl-cs-001.litwareinc.com に対してテストユーザーが定義されている場合にのみ機能します。 その場合、コマンドは、最初のテストユーザーが Web Scheduler を使ってオンライン会議をスケジュールできるかどうかを決定します。

テストユーザーが定義されていない場合は、どのユーザーとしてログオンするかがわからないため、コマンドは失敗します。 プールのテストユーザーを定義していない場合は、UserSipAddress パラメーターと、ログオンしようとしたときにコマンドによって使用されるユーザーの資格情報を含める必要があります。

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

次の例に示すコマンドは、Web scheduler を使ってオンライン会議を\\スケジュールするために、特定のユーザー (litwareinc kenmeyer) の機能をテストします。 これを行うには、この例の最初のコマンドでは、 **Credential**コマンドレットを使用して、ユーザー Ken Meyer の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイスの資格情報オブジェクトを作成します。 (Logon name litwareinc\\kenmeyer はパラメーターとして含まれているため、Windows PowerShell 資格情報の要求ダイアログボックスでは、管理者が Ken Meyer account のパスワードを入力するだけであることになります。)結果として得られた資格情報オブジェクトは、$cred 1 という名前の変数に格納されます。

2番目のコマンドは、このユーザーがプール atl-cs-001.litwareinc.com にログオンしてオンライン会議をスケジュールできるかどうかを確認します。 このタスクを実行するために、**テスト用の Webscheduler**コマンドレットが呼び出され、次の3つのパラメーター (レジストラープールの FQDN) が使用されます。UserCredential (Pilar Ackerman のユーザー資格情報を格納する Windows PowerShell オブジェクト)UserSipAddress (提供されているユーザー資格情報に対応する SIP アドレス) を選びます。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

Web scheduler が適切に構成されている場合は、次のような結果が返され、Result プロパティは**Success**とマークされます。

ターゲット Fqdn: atl-cs-001.litwareinc.com

ターゲット Uri: https://atl-cs-001.litwareinc.com。

litwareinc.com:443/Scheduler

結果: 成功

待ち時間: 00:00:00

エラーメッセージ:

診断

Web scheduler が正しく構成されていない場合は、結果が**失敗**として表示され、エラーと診断のプロパティに追加情報が記録されます。

警告: 指定した完全修飾のレジストラーポート番号の読み取りに失敗しました

ドメイン名 (FQDN)。 既定のレジストラーポート番号を使用します。 エラー

InvalidOperationException: トポロジで一致するクラスターが見つかりませんでした。

自宅

SipSyntheticTransaction-TryRetri の同期を行います。

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

ターゲット Fqdn: atl-cs-001.litwareinc.com

ターゲット Uri:

結果: エラー

待ち時間: 00:00:00

エラーメッセージ: 一致するクラスターがトポロジに見つかりませんでした。

診断

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に **、テスト用の Webscheduler スケジューラ**が機能しない場合の一般的な理由を示します。

  - 指定されたパラメーター値が正しくありません。 使用する場合は、オプションのパラメーターが正しく構成されている必要があります。または、テストが失敗します。 省略可能なパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。

  - Web Scheduler が正しく構成されていない場合、またはまだ展開されていない場合、このコマンドは失敗します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Set-CsWebServer](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

