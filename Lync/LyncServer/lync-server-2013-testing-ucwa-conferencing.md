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
ms.openlocfilehash: 8c5daad2d43cf5a7e61dd0e87fac79eb98b9c82e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a>Lync Server 2013 での UCWA 会議のテスト

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合は、 <strong>test-csucwaconference</strong>コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

**Test-csucwaconference**コマンドレットは、テストユーザーのペアが、統合コミュニケーション Web API (ucwa) を使用してオンライン会議をスケジュール、参加、および実行できることを確認します。 これを行うために、コマンドレットは Lync Server web チケットサービスを使用して2つのテストユーザーを認証し、それらを Lync Server に登録します。 コマンドレットは、開催者の資格情報を使用して会議を開始し、参加者に会議への参加を依頼します。 会議が参加した後、 **test-csucwaconference**コマンドレットは、ユーザーが exchange インスタントメッセージやプールの実行などの操作を行うことができることを確認した後、会議を切断し、2つのテストユーザーの登録を解除します。 スケジュールされた会議は、テストが完了したときにも削除されます。

匿名ユーザーがオンライン会議に参加できるかどうかを判断するには、 **test-csucwaconference**コマンドレットを使用することもできます。

**Test-csucwaconference**コマンドレットは、ucwa がそのプールにインストールされていない限り、Microsoft Lync Server 2010 プールに対して実行しないように注意してください。 UCWA がインストールされていない場合は、 **test-csucwaconference**コマンドレットの呼び出しは失敗します。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

例1に示すコマンドを実行すると、テストユーザーのペアが、プール atl-cs-001.litwareinc.com で UCWA 会議に参加できることが確認されます。 Atl-cs-001.litwareinc.com の正常性の監視構成テストユーザーのペアが事前に定義されていない場合、このコマンドは失敗することに注意してください。

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

例2のコマンドは、ユーザーのペア (litwareinc\\pilar と litwareinc\\kenmyer) が ucwa 会議に参加できるかどうかをテストします。 これを行うには、例の最初のコマンドは、資格情報コマンドレットを使用して、user Pilar Ackerman の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成します。 (ログオン名 litwareinc\\pilar がパラメーターとして含まれているため、[Windows PowerShell 資格情報の要求] ダイアログボックスでは、管理者のみが Pilar Ackerman アカウントのパスワードを入力する必要があります)。その後、結果の資格情報オブジェクトは $cred 1 という名前の変数に格納されます。 2番目のコマンドは同じことを行いますが、今度は Ken Myer アカウントの credential オブジェクトを返します。

2つの資格情報オブジェクトがある場合、この例の3番目のコマンドでは、2人のユーザーが UCWA 会議に参加できるかどうかを判断します。 このタスクを実行するには、 **test-csucwaconference**コマンドレットを次のパラメーターと共に呼び出します。 targetfqdn (レジストラープールの FQDN)。OrganizerSipAddress (会議の開催者の SIP アドレス)。Groupname Ercredential (この同じユーザーの資格情報を含む Windows PowerShell オブジェクト)。ParticipantSipAddress (他のテストユーザーの SIP アドレス)。ParticipantCredential (他のユーザーの資格情報を含む Windows PowerShell コマンドラインインターフェイスオブジェクト)。

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

会議が正しく構成されている場合は、次のような出力が得られ、Result プロパティは Success としてマークされ**ます。**

ターゲット Fqdn: atl-cs-001.litwareinc.com

ターゲット Uri: https://LyncTest-Corp. LyncTest.

Microsoft.com:443/CertProv/CertProvisiongService.svc

結果: 成功

待機時間:00:00: 14.9862716

エラーメッセージ:

分析

指定したユーザーが会議を使用できない場合、結果は**失敗**として表示され、エラーと診断のプロパティに追加情報が記録されます。

警告: 指定された完全修飾のレジストラーポート番号を読み取ることができませんでした

ドメイン名 (FQDN)。 既定のレジストラーポート番号を使用します。 例外

System.invalidoperationexception: トポロジ内に一致するクラスターが見つかりませんでした。

下部

TryRetri を SipSyntheticTransaction していることを示します。

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Test-csucwaconference: に対してテストユーザーが割り当てられていません

\[LyncTest.SelfHost.Corp.Microsoft.com\]。 テストユーザーの構成を確認します。

行: 1 char: 1

\+Test-csucwaconference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+カテゴリ情報: ResourceUnavailable 不可: (:)\[Test-csucwaconference\]

、System.invalidoperationexception

\+FullyQualifiedErrorId: Notていない Testusers、Microsoft Rtc.

TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

**Test-csucwaconference**が失敗する可能性のある一般的な原因を次に示します。

  - 指定されたパラメーター値が正しくありません。 省略可能なパラメーターが使用されている場合、オプションのパラメーターが正しく構成されている必要があります。テストは失敗します。 オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。

  - 会議を開催できるかどうかは、会議を開催したユーザー ( **test-csucwaconference**コマンドレットの場合は "sender") に割り当てられている会議ポリシーによって決まります。 開催者が会議に共同作業のアクティビティを含めることが許可されていない場合 (たとえば、その会議ポリシーで EnableDataCollaboration プロパティが False に設定されている場合)、 **test-csucwaconference**コマンドレットは失敗します。

  - エッジサーバーの構成が正しくないか、まだ展開されていない場合、このコマンドは失敗します。

</div>

<div>

## <a name="see-also"></a>関連項目


[テスト-CsASConference](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[Test-csdataconference](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[テスト-CsAVConference 会議](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

