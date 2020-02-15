---
title: 'Lync Server 2013: サードパーティの電話会議のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2897e085ea35e17d65719874ecf103ed7f1475d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a>Lync Server 2013 でのサードパーティの電話会議のテスト

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合は、Test-csaudioconferencingprovider コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

電話会議プロバイダーとは、電話会議サービスを組織に提供するサード パーティの企業です。電話会議プロバイダーの主な機能は、社外にいて企業ネットワークまたはインターネットに接続されていないユーザーが、電話会議または会議のオーディオ部分に参加できるようにすることです。電話会議プロバイダーは多くの場合、リアルタイム通訳、トランスクリプション、オペレーターによる各電話会議のリアルタイム サポートなど、高度なサービスを提供します。

**Test-csaudioconferencingprovider**コマンドレットは、ユーザーが自分の電話会議プロバイダーに接続できることを確認するために使用されます。 このコマンドレットは、次の2つの方法のどちらかで実行できることに注意してください。 多くの管理者は、CsHealthMonitoringConfiguration コマンドレットを使用して、テスト ユーザーを各レジストラー プールに設定します。 これらのテストユーザーは、代理トランザクションで使用するために事前に構成されたユーザーアカウントのペアを表します。 (通常、これらはテストアカウントであり、実際のユーザーに属するアカウントではありません)。テストユーザーがプールに対して構成されている場合、管理者は、テストに関係するユーザーアカウント (および資格情報) を指定せずに、そのプールに対して**test-csaudioconferencingprovider**コマンドレットを実行できます。

または、管理者は実際のユーザーアカウントを使用して**test-csaudioconferencingprovider**コマンドレットを実行できます。 実際のユーザー アカウントを使用してテストを実行する場合は、そのアカウントのログオン名とパスワードを入力する必要があります。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

例1では、プール atl-cs-001.litwareinc.com に対して定義されたテストユーザーが自分の電話会議プロバイダーに接続できるかどうかを確認します。 このコマンドでは、プールに対して少なくとも1つのテストユーザーを定義する必要があります。 Atl-cs-001.litwareinc.com に対してテストユーザーが定義されていない場合、コマンドは失敗します。これは、 **test-csaudioconferencingprovider**コマンドレットはテストに使用するユーザーを認識しないためです。 プールに対してテストユーザーが定義されていない場合は、電話会議プロバイダーとの接続を確認するときに、コマンドが使用する必要があるユーザーアカウントの UserSipAddress パラメーターと資格情報を含める必要があります。

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

例2に示すコマンドは、特定のユーザー (litwareinc\\kenmyer) が自分の電話会議プロバイダーに接続できるかどうかをテストします。 これを行うには、例の最初のコマンドは、資格情報コマンドレットを使用して、ユーザー Ken Myer の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成します。 (ログオン名 litwareinc\\kenmyer がパラメーターとして含まれているため、Windows PowerShell の [資格情報の要求] ダイアログボックスでは、管理者のみが Ken Myer アカウントのパスワードを入力する必要があります)。結果の資格情報オブジェクトは、$credential という名前の変数に格納されます。

次に、2 番目のコマンドでは、このユーザーが電話会議プロバイダーに接続できるかを確認します。 このタスクを実行するために、Test-csaudioconferencingprovider コマンドレットがとともに、TargetFqdn (レジストラープールの FQDN) という3つのパラメーターと共に呼び出されます。UserCredential (Ken Myer のユーザー資格情報を含む Windows PowerShell オブジェクト)。UserSipAddress (指定されたユーザー資格情報に対応する SIP アドレス)。

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

電話会議プロバイダーが正しく構成されている場合は、次のような出力が得られ、Result プロパティは Success としてマークされ**ます。**

ターゲット Fqdn: atl-sql-001.litwareinc.com

結果: 成功

待機時間: 00:00:00

エラーメッセージ:

分析

指定したユーザーがログオンまたはログオフできない場合は、結果**がエラーと**して表示され、エラーと診断のプロパティに追加情報が記録されます。

ターゲット Fqdn: atl-sql-001.litwareinc.com

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

たとえば、前述の出力には、通常、エッジサーバーに問題があることを示す「接続されたパーティは正しく応答しませんでした」というメモが含まれています。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

**Test-csaudioconferencingprovider**が失敗する可能性のある一般的な原因を次に示します。

  - 指定されたパラメーター値が正しくありません。 前の例で示されているように、オプションのパラメーターが正しく構成されている必要があります。または、テストが失敗します。 オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。

  - **Test-csaudioconferencingprovider**コマンドレットによって使用されているユーザーに電話会議プロバイダーが割り当てられていない場合は、テストが失敗することに注意してください。

  - エッジサーバーの構成が正しくないか、まだ展開されていない場合、このコマンドは失敗します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

