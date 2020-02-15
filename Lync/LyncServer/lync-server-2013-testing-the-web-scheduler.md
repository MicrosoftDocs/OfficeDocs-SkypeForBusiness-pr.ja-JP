---
title: 'Lync Server 2013: Web スケジューラのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bc3d93e1e4a08575119031471863dad817f3e80
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-web-scheduler-in-lync-server-2013"></a>Lync Server 2013 での Web スケジューラのテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-11-03_


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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、 <strong>Test-CsWebScheduler</strong>コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

**Test-CsWebScheduler**コマンドレットを使用すると、特定のユーザーが Web スケジューラを使用して会議をスケジュールできるかどうかを判断できます。 Web スケジューラは、Outlook を実行していないユーザーがオンライン会議をスケジュール設定できるようにします。 その他の機能として、この新しい機能 (Microsoft Lync Server 2010 リソースキットに付属していた Web スケジューラツールの機能を組み込む) により、ユーザーは次のことができます。

  - 新しいオンライン会議をスケジュール設定します。

  - ユーザーがスケジュール設定したすべての会議の一覧を示します。

  - 既存の会議を表示/変更します。

  - 既存の会議を削除します。

  - 事前設定された SMTP メール サーバーを使用して会議の参加者に電子メール招待を送信します。

  - 既存の会議に参加します。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

次の例では、プール atl-cs-001.litwareinc.com の Web スケジューラを検証します。 このコマンドは、プール atl-cs-001.litwareinc.com に対してテストユーザーが定義されている場合にのみ機能します。 その場合は、コマンドによって、最初のテストユーザーが Web スケジューラを使用してオンライン会議をスケジュールできるかどうかが判断されます。

テストユーザーが定義されていない場合は、どのユーザーがどのユーザーとしてログオンするかがわからないため、コマンドは失敗します。 プールに対してテストユーザーが定義されていない場合は、UserSipAddress パラメーターと、コマンドがログオンを試行するときに使用するユーザーの資格情報を含める必要があります。

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

次の例に示すコマンドは、特定のユーザー (litwareinc\\kenmeyer) が Web スケジューラを使用してオンライン会議をスケジュールする機能をテストします。 これを行うには、例の最初のコマンドは、**資格情報**コマンドレットを使用して、ユーザー Ken Meyer の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成します。 (ログオン名 litwareinc\\kenmeyer がパラメーターとして含まれているため、Windows PowerShell の [資格情報の要求] ダイアログボックスでは、管理者のみが Ken Meyer アカウントのパスワードを入力する必要があります。)その後、結果として得られる資格情報オブジェクトは $cred 1 という名前の変数に格納されます。

2番目のコマンドは、このユーザーがプール atl-cs-001.litwareinc.com にログオンし、オンライン会議をスケジュールすることができるかどうかをチェックします。 このタスクを実行するには、次の3つのパラメーターと共に、 **Test-CsWebScheduler**コマンドレットを呼び出します。 Targetfqdn (レジストラープールの FQDN)。UserCredential (Pilar Ackerman のユーザー資格情報を含む Windows PowerShell オブジェクト)。UserSipAddress (指定されたユーザー資格情報に対応する SIP アドレス)。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

Web スケジューラが正しく構成されている場合は、次のような出力が得られ、Result プロパティは**Success**とマークされます。

ターゲット Fqdn: atl-cs-001.litwareinc.com

ターゲット Uri: https://atl-cs-001.litwareinc.com。

litwareinc.com:443/Scheduler

結果: 成功

待機時間: 00:00:00

エラーメッセージ:

分析

Web スケジューラが正しく構成されていない場合は、結果が**エラーとして**表示され、追加情報が Error および診断プロパティに記録されます。

警告: 指定された完全修飾のレジストラーポート番号を読み取ることができませんでした

ドメイン名 (FQDN)。 既定のレジストラーポート番号を使用します。 例外

System.invalidoperationexception: トポロジ内に一致するクラスターが見つかりませんでした。

下部

TryRetri を SipSyntheticTransaction していることを示します。

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

ターゲット Fqdn: atl-cs-001.litwareinc.com

ターゲット Uri:

結果: エラー

待機時間: 00:00:00

エラーメッセージ: トポロジ内に一致するクラスターが見つかりませんでした。

分析

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

次に **、Test-CsWebScheduler**が失敗する可能性のある一般的な理由を示します。

  - 指定されたパラメーター値が正しくありません。 省略可能なパラメーターが使用されている場合、オプションのパラメーターが正しく構成されている必要があります。テストは失敗します。 オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。

  - Web スケジューラが正しく構成されていないか、まだ展開されていない場合、このコマンドは失敗します。

</div>

<div>

## <a name="see-also"></a>関連項目


[設定-CsWebServer](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

