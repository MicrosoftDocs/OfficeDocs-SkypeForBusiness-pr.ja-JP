---
title: 'Lync Server 2013: 場所のポリシーのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a46eecb63ed35075cb44ff840e733f781357ea6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a>Lync Server 2013 での場所のポリシーのテスト

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、Test-CsLocationPolicy コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Test-CsLocationPolicy コマンドレットは、場所のポリシーがユーザーに割り当てられていることを確認します。 場所のポリシーを使用して、E9-1-1 の機能およびクライアントの場所に関連する設定を適用します。 場所のポリシーによって、ユーザーが E9-1-1 に対して有効になっているかどうかが判断されます。また、応答が "yes" の場合は、緊急電話の動作がどのようなものですか。 たとえば、場所のポリシーを使用して、会社のセキュリティを自動的に通知するかどうか、および通話をルーティングする方法を定義することができます (米国では 911)。

ユーザーまたはネットワーク サブネットに対して場所のポリシーをテストできます。 サブネットに対してテストを実行する場合 (Subnet パラメーターに値を指定します)、コマンドレットはそのサブネット用の場所のポリシーの解決を試みます。 サブネットに場所のポリシーが割り当てられていない場合、構成されているユーザーの場所のポリシーが取得されます。 サブネットポリシーが正常に取得された場合、出力には、サブネット-tagid で始まる LocationPolicyTagID 値が含まれます。 サブネットの場所のポリシーが見つからなかった場合は、LocationPolicyTagID は user-tagid で始まります。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Test-CsLocationPolicy コマンドレットは、事前構成されたテストアカウント (「Lync Server テストを実行するためのテストアカウントの設定」を参照)、または Lync Server が有効になっているユーザーのアカウントのいずれかを使用して実行できます。 テストアカウントを使用してこのチェックを実行するには、テストする Lync Server プールの FQDN を指定するだけで済みます。 例:

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

実際のユーザーアカウントを使用してこのチェックを実行するには、まず、アカウント名とパスワードを含む Windows PowerShell credentials オブジェクトを作成する必要があります。 次に、その資格情報オブジェクトと、Test-CsLocationPolicy を呼び出すときにアカウントに割り当てられた SIP アドレスを含める必要があります。

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

詳細については、 [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy)コマンドレットのヘルプドキュメントを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

指定したユーザーに有効な場所ポリシーがある場合は、次のような出力が得られ、Result プロパティは Success としてマークされ**ます。**

EnhancedEmergencyServicesEnabled: true

LocationPolicyTagID: user-tagid

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間:00:00: 06.8630376

エラー

分析

指定したユーザーの有効な場所のポリシーが見つからない場合は、結果がエラーとして表示され、次の情報が Error および診断プロパティに記録されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間: 00:00:00

エラー: 404、見つかりません

診断: ErrorCode = 4005, Source = 001.litwareinc.com,

Reason = 宛先 URI が SIP に対して有効になっていないか、または使用されていません

ない.

DiagnosticHeader ()

指定されたユーザーが有効でないため、テストが失敗したことが示されます。アカウントが存在しないか、ユーザーが Lync Server に対して有効になっていません。 アカウントの有効性を確認し、次のようなコマンドを実行することによって、アカウントが、そのアカウントが有効になっているかどうかを確認できます。

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

Test-CsLocationPolicy が失敗した場合は、次のように詳細なパラメーターを含めて、テストを再実行することもできます。

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose パラメーターが指定されている場合、テスト-CsLocationPolicy は、場所ポリシーの確認時に試行された各操作のステップバイステップのアカウントを返します。 たとえば、次の出力は、無効なパスワードが指定されたために、Lync Server がテストユーザーにログオンできなかったことを示しています。

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

次に、Test-CsLocationPolicy が失敗する主な理由を示します。

  - 無効なユーザーアカウントが指定されました。 ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。 ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server に対して有効になっていないことを意味します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

