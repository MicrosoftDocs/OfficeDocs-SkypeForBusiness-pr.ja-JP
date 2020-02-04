---
title: 'Lync Server 2013: UCWA 会議のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9496b2a860f0a8272d6eb98df6a2c897aa245ec9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a>Lync Server 2013 での UCWA 会議のテスト

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
<p>Windows PowerShell のリモートインスタンスを使って実行する場合は、 <strong>CsUcwaConference</strong>コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

**CsUcwaConference**コマンドレットは、1組のテストユーザーがユニファイドコミュニケーション Web API (ucwa) を使用してオンライン会議をスケジュール、参加、実施できることを確認します。 これを行うには、コマンドレットは Lync Server web ticket サービスを使って2つのテストユーザーを認証し、Lync Server に登録します。 次に、このコマンドレットは開催者の資格情報を使用して会議を開始し、参加者を会議に参加するように招待します。 会議が参加した後、 **CsUcwaConference**コマンドレットは、ユーザーが exchange インスタントメッセージやプールの実施などの操作を実行できることを確認した後、会議を切断し、2つのテストユーザーの登録を解除します。 スケジュールされた会議も、テストが完了したときに削除されます。

**CsUcwaConference**コマンドレットを使用して、匿名ユーザーがオンライン会議に参加できるかどうかを判断することもできます。

UCWA がそのプールにインストールされていない場合は、 **CsUcwaConference**コマンドレットを Microsoft Lync Server 2010 プールに対して実行しないように注意してください。 UCWA がインストールされていない場合は、 **CsUcwaConference**コマンドレットの呼び出しが失敗します。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

例1に示すコマンドは、テストユーザーのペアが、プール atl-cs-001.litwareinc.com の UCWA 会議に参加できることを確認します。 Atl-cs-001.litwareinc.com の正常性監視構成テストユーザーのペアを定義していない場合、このコマンドは失敗します。

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

例2に示すコマンドは、UCWA 会議に参加するユーザーのペア\\(litwareinc pilar\\と litwareinc kenmyer) の機能をテストします。 これを行うには、この例の最初のコマンドでは、Credential コマンドレットを使用して、user Pilar Ackerman の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成します。 (Logon name、litwareinc\\pilar はパラメーターとして指定されているため、Windows PowerShell 資格情報の要求ダイアログボックスでは、管理者は Pilar Ackerman アカウントのパスワードを入力する必要があります)。結果として得られた資格情報オブジェクトは、$cred 1 という名前の変数に格納されます。 2番目のコマンドでも同じことが実行されますが、今回は Ken Myer アカウントの credential オブジェクトを返します。

2つの資格情報オブジェクトを使うと、この例の3番目のコマンドは、2人のユーザーが UCWA 会議に参加できるかどうかを決定します。 このタスクを実行するために、 **CsUcwaConference**コマンドレットが呼び出され、次のパラメーターが使用されます。 targetfqdn (レジストラープールの FQDN)OrganizerSipAddress (会議の開催者の SIP アドレス)組織の資格情報 (同じユーザーの資格情報を格納する Windows PowerShell オブジェクト)ParticipantSipAddress (他のテストユーザーの SIP アドレス)ParticipantCredential (他のユーザーの資格情報が含まれている Windows PowerShell コマンドラインインターフェイスオブジェクト) を選びます。

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

会議が適切に構成されている場合は、次のような結果が返され**ます。** これには、Result プロパティが Success とマークされています。

ターゲット Fqdn: atl-cs-001.litwareinc.com

ターゲット Uri: https://LyncTest-SE. LyncTest.

Microsoft.com:443/CertProv/CertProvisiongService.svc

結果: 成功

待ち時間:00:00: 14.9862716

エラーメッセージ:

診断

指定されたユーザーが会議を使用できない場合は、結果**がエラーとして**表示され、エラーと診断のプロパティに追加情報が記録されます。

警告: 指定した完全修飾のレジストラーポート番号の読み取りに失敗しました

ドメイン名 (FQDN)。 既定のレジストラーポート番号を使用します。 エラー

InvalidOperationException: トポロジで一致するクラスターが見つかりませんでした。

自宅

SipSyntheticTransaction-TryRetri の同期を行います。

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

CsUcwaConference: のテストユーザーが割り当てられていません。

\[LyncTest.SelfHost.Corp.Microsoft.com\]。 テストユーザー構成を確認します。

行: 1 char: 1

\+CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+カテゴリ情報: ResourceUnavailable 使用できません: (:)\[テスト-CsUcwaConference\]

、InvalidOperationException

\+FullyQualifiedErrorId: Notん Testusers、Microsoft Rtc。

TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に **、テスト-CsUcwaConference**が失敗する可能性がある一般的な理由を示します。

  - 指定されたパラメーター値が正しくありません。 使用する場合は、オプションのパラメーターが正しく構成されている必要があります。または、テストが失敗します。 省略可能なパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。

  - 会議を開催する機能は、会議を開催したユーザーに割り当てられている会議ポリシー ( **CsUcwaConference**コマンドレットの場合は "送信者") によって異なります。 開催者が、会議に共同作業のアクティビティを含めることを許可していない場合 (たとえば、自分の会議ポリシーの EnableDataCollaboration プロパティが False に設定されている場合など)、 **CsUcwaConference**コマンドレットは失敗します。

  - エッジサーバーが正しく構成されていないか、まだ展開されていない場合、このコマンドは失敗します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

