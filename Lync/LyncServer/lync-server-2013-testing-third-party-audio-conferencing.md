---
title: 'Lync Server 2013: サードパーティの電話会議のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1c23f65015dd34f5efbaafa8472466394caa52c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a>Lync Server 2013 でのサードパーティの電話会議のテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-11-01_


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
<p>Windows PowerShell のリモートインスタンスを使って実行する場合は、CsAudioConferencingProvider コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

電話会議プロバイダーとは、電話会議サービスを組織に提供するサード パーティの企業です。 電話会議プロバイダーの主な機能は、社外にいて企業ネットワークまたはインターネットに接続されていないユーザーが、電話会議または会議のオーディオ部分に参加できるようにすることです。 電話会議プロバイダーは、リアルタイムの翻訳、議事録、電話会議などの機能のようなハイエンドサービスを提供します。

**CsAudioConferencingProvider**コマンドレットを使用して、ユーザーが電話会議プロバイダーへの接続を確立できることを確認します。 このコマンドレットは、次の2つの方法のいずれかで実行できます。 多くの管理者は、CsHealthMonitoringConfiguration コマンドレットを使用して、各レジストラープールのテストユーザーをセットアップします。 これらのテストユーザーは、代理トランザクションで使用するために事前に構成されているユーザーアカウントのペアを表します。 (通常、テストアカウントであり、実際のユーザーに属するアカウントではありません)。プールに対してテストユーザーが構成されている場合、管理者は、テストに関係しているユーザーアカウントの id を指定せずに、そのプールに対して**CsAudioConferencingProvider**コマンドレットを実行することができます。

または、管理者は実際のユーザーアカウントを使用して**CsAudioConferencingProvider**コマンドレットを実行することができます。 実際のユーザーアカウントを使用してテストを実施する場合は、そのアカウントのログオン名とパスワードを指定する必要があります。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

例1プール atl-cs-001.litwareinc.com に対して定義されたテストユーザーが、自分の電話会議プロバイダーに接続できるかどうかを確認します。 このコマンドでは、プールに対して少なくとも1つのテストユーザーを定義する必要があります。 Atl-cs-001.litwareinc.com にテストユーザーが定義されていない場合、コマンドは失敗します。これは、 **CsAudioConferencingProvider**コマンドレットでは、どのユーザーがテストで採用するかわからないためです。 プールのテストユーザーを定義していない場合は、電話会議プロバイダーとの接続を確認するときに、コマンドで使用する必要があるユーザーアカウントの UserSipAddress パラメーターと資格情報を含める必要があります。

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

例2に示すコマンドは、特定のユーザー (litwareinc\\kenmyer) が電話会議プロバイダーに接続できるかどうかをテストします。 これを行うには、この例の最初のコマンドでは、credentials コマンドレットを使用して、ユーザー Ken Myer の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイスの credentials オブジェクトを作成します。 (ログオン名 litwareinc\\kenmyer はパラメーターとして含まれているため、Windows PowerShell 資格情報の要求ダイアログボックスでは、管理者が Ken Myer アカウントのパスワードを入力するだけで済みます)。この結果、資格情報オブジェクトは $credential という名前の変数に格納されます。

2番目のコマンドは、このユーザーが自分の電話会議プロバイダーに接続できるかどうかを確認します。 この処理を実行するために、CsAudioConferencingProvider コマンドレットが呼び出され、次の3つのパラメーター (レジストラープールの FQDN) が使用されます。UserCredential (Ken Myer のユーザー資格情報を含む Windows PowerShell オブジェクト)UserSipAddress (提供されているユーザー資格情報に対応する SIP アドレス) を選びます。

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

電話会議プロバイダーが正しく構成されている場合は、次のような出力が表示され、Result プロパティは Success とマークされ**ます。**

ターゲット Fqdn: atl-sql-001.litwareinc.com

結果: 成功

待ち時間: 00:00:00

エラーメッセージ:

診断

指定したユーザーがログオンまたはログオフできない場合は、結果がエラーと**** して表示され、エラーと診断のプロパティに追加情報が記録されます。

ターゲット Fqdn: atl-sql-001.litwareinc.com

結果: エラー

待ち時間: 00:00:00

エラーメッセージ: 10060、接続されているパーティのため、接続に失敗しました

一定の期間が経過した後に正しく応答しなかった場合、または

接続されているホストに、接続に失敗しました

2001: 4898 \[: f39e: 5c9a: ad83: 81b3: 9944\]: 5061 を応答できませんでした。

内部例外: 接続の試行が失敗したため、接続できませんでした。

しばらくしても、接続されているパーティが正しく応答しませんでした

接続されているホストが原因で、時刻、または接続に失敗しました

が応答しませんでした

\[2001: 4898: f39e: 5c9a: ad83: 81b3: 9944\]: 5061

診断

たとえば、前回の出力には、"接続されているパーティは正しく応答しませんでした" というメモが含まれています。通常、エッジサーバーに問題があることを示します。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に **、テスト-CsAudioConferencingProvider**が失敗する可能性がある一般的な理由を示します。

  - 指定されたパラメーター値が正しくありません。 上の例で示したように、オプションのパラメーターは正しく構成されている必要があります。また、テストは失敗します。 省略可能なパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。

  - **CsAudioConferencingProvider**コマンドレットによって採用されたユーザーに電話会議プロバイダーが割り当てられていない場合、テストは失敗します。

  - エッジサーバーが正しく構成されていないか、まだ展開されていない場合、このコマンドは失敗します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

