---
title: 'Lync Server 2013: 会議での共有のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0094c0b58281027f24d4cd902a4e0813c7e45f96
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a>Lync Server 2013 での会議での共有のテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-11-01_


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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合は、 <strong>test-csdataconference</strong>コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Lync Server 2013 のデータ会議とは、ホワイトボードや注釈などのコラボレーションアクティビティを使用する会議のことです。 **Test-csdataconference**コマンドレットを使用すると、ユーザーのペアがデータ会議に参加できることを確認できます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

例 1 に示すコマンドは、atl-cs-001.litwareinc.com というプールでデータ電話会議を実施できるかどうかを確認します。ここでは、指定するプールに対して 1 組のテスト ユーザーが構成済みであることを前提としています。テスト ユーザーが構成されていない場合、コマンドの実行は失敗します。

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

例2のコマンドは、ユーザーのペア (litwareinc\\pilar と litwareinc\\Kenmyer) が Lync Server 2013 にログオンし、データ会議を行うことができるかどうかをテストします。 これを行うために、この例の最初のコマンドは、**資格情報**コマンドレットを使用して、User Pilar Ackerman の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成します。 (ログオン名 litwareinc\\pilar がパラメーターとして含まれているため、[Windows PowerShell 資格情報の要求] ダイアログボックスでは、管理者のみが Pilar Ackerman アカウントのパスワードを入力する必要があります)。その後、結果として得られる資格情報オブジェクトは $cred 1 という名前の変数に格納されます。 2番目のコマンドは同じことを行いますが、今度は Ken Myer アカウントの credential オブジェクトを返します。

資格情報オブジェクトが手元にある場合、3番目のコマンドは、これら2人のユーザーが Lync Server 2013 にログオンしてデータ会議を実行できるかどうかを判断します。 このタスクを実行するために、 **test-csdataconference**コマンドレットを次のパラメーターと共に呼び出します。 targetfqdn (レジストラープールの FQDN)。SenderSipAddress (最初のテストユーザーの SIP アドレス)。SenderCredential (この同じユーザーの資格情報を含む Windows PowerShell オブジェクト)。ReceiverSipAddress (他のテストユーザーの SIP アドレス)。と ReceiverCredential (他のテストユーザーの資格情報を格納している Windows PowerShell オブジェクト)。

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

データ会議が正しく構成されている場合は、次のような出力が得られ、Result プロパティは Success とマークされ**ます。**

ターゲット Fqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間: 00:00:00

エラーメッセージ:

分析

指定したユーザーがデータ共有を使用できない場合は、結果**がエラーとして**表示され、エラーと診断のプロパティに追加情報が記録されます。

ターゲット Fqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間: 00:00:00

エラーメッセージ: 10060。接続しているパーティが原因で接続に失敗しました。

一定期間後に正しく応答しなかったか、または

接続されたホストの接続に失敗しました。

2001年に\[応答できませんでした: 4898: e8: f39e: 5c9a: ad83:\]81b3: 9944: 5061

内部例外: 接続の試行が失敗しました。

接続されたパーティは、一定期間の後に正しく応答しませんでした

接続されているホストが原因で、接続に失敗しました。

応答に失敗した

\[2001年: 4898: e8: f39e: 5c9a: ad83: 81b3:\]9944: 5061

分析

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

**Test-csdataconference**が失敗する可能性のある一般的な原因を次に示します。

  - 指定されたパラメーター値が正しくありません。 省略可能なパラメーターが使用されている場合、オプションのパラメーターが正しく構成されている必要があります。テストは失敗します。 オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。

  - データ会議を開催できるかどうかは、会議を開催したユーザー ( **test-csdataconference**コマンドレットの場合は "sender") に割り当てられている会議ポリシーによって決まります。 開催者が会議に共同作業のアクティビティを含めることが許可されていない場合 (たとえば、その会議ポリシーで EnableDataCollaboration プロパティが False に設定されている場合)、 **test-csdataconference**コマンドレットは失敗します。

  - エッジサーバーの構成が正しくないか、まだ展開されていない場合、このコマンドは失敗します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

