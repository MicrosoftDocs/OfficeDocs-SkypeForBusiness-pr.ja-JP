---
title: 'Lync Server 2013: アプリケーション共有のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11130c1882fd6d12784cf6c25559a4249453f5d3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530534"
---
# <a name="testing-application-sharing-in-lync-server-2013"></a>Lync Server 2013 でのアプリケーション共有のテスト

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsASConference コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

**Test-CsASConference**コマンドレットは、テストユーザーのペアがアプリケーション共有を含むオンライン会議に参加できることを確認します。 これを行うために、コマンドレットは2人のユーザーを Lync Server 2013 に登録し、ユーザーアカウントの1人を使用して、アプリケーション共有を含む新しい会議を作成します。 その後、もう 1 人のユーザーが電話会議に参加できるかどうかを確認します。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

例 1 に示すコマンドは、atl-cs-001.litwareinc.com というプールでアプリケーション共有電話会議を実施できるかどうかを確認します。ここでは、指定するプールに対して 1 組のテスト ユーザーが構成済みであることを前提としています。テスト ユーザーが構成されていない場合、コマンドの実行は失敗します。

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

例 2 では、atl-cs-001.litwareinc.com というプールでのアプリケーション共有電話会議に Join Launcher サービスが参加できるかどうかをテストします。このコマンドはサービスのみをテストします。このコマンドを実行するためにモバイル デバイスは必要ありません。

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

例2のコマンドは、ユーザーのペア (litwareinc \\ pilar と litwareinc \\ kenmyer) が Lync Server 2013 にログオンして、アプリケーション共有会議を開始できるかどうかをテストします。 これを行うには、この例の最初のコマンドは Get-Credential コマンドレットを使用して、user Pilar Ackerman の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成します。 (ログオン名 litwareinc \\ pilar がパラメーターとして含まれているため、[Windows PowerShell 資格情報の要求] ダイアログボックスでは、管理者のみが Pilar Ackerman アカウントのパスワードを入力する必要があります)。その後、結果として得られる資格情報オブジェクトは $cred 1 という名前の変数に格納されます。 2番目のコマンドは同じことを行いますが、今度は Ken Myer アカウントの credential オブジェクトを返します。

資格情報オブジェクトが手元にある場合、3番目のコマンドは、これら2人のユーザーが Lync Server 2013 にログオンして、アプリケーション共有会議を実行できるかどうかを判断します。 このタスクを実行するために、次のパラメーターと共に、 **Test-CsASConference** コマンドレットが呼び出されます。 targetfqdn (レジストラープールの FQDN)。SenderSipAddress (最初のテストユーザーの SIP アドレス)。SenderCredential (この同じユーザーの資格情報を含む Windows PowerShell オブジェクト)。ReceiverSipAddress (他のテストユーザーの SIP アドレス)。と ReceiverCredential (他のテストユーザーの資格情報を格納している Windows PowerShell オブジェクト)。

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

アプリケーション共有が正しく構成されている場合は、次のような出力が得られ、Result プロパティは Success としてマークされ **ます。**

ターゲット Fqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間: 00:00:01

エラーメッセージ:

分析

指定したユーザーがアプリケーションを共有できない場合、結果は失敗として表示され、追加情報が Error および診断プロパティに記録されます。

ターゲット Fqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間: 00:00:00

エラーメッセージ: 10060。接続しているパーティが原因で接続に失敗しました。

一定期間後に正しく応答しなかったか、または

接続されたホストの接続に失敗しました。

10.188.116.96: 5061 に応答できませんでした

内部例外: 接続の試行が失敗しました。

接続されたパーティは、一定期間の後に正しく応答しませんでした

接続されているホストが原因で、接続に失敗しました。

10.188.116.96: 5061 に応答できませんでした

分析

たとえば、前述の出力には、通常、エッジサーバーに問題があることを示す「接続されたパーティは正しく応答しませんでした」というメモが含まれています。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

次に **、Test-CsASConference** が失敗する主な理由を示します。

  - 指定されたパラメーター値が正しくありません。 省略可能なパラメーターが使用されている場合、オプションのパラメーターが正しく構成されている必要があります。テストは失敗します。 オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。

  - テストユーザーにアプリケーション共有の使用を禁止する電話会議ポリシーが割り当てられている場合、このコマンドは失敗します。

  - エッジサーバーの構成が正しくないか、まだ展開されていない場合、このコマンドは失敗します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[Test-csdataconference](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

