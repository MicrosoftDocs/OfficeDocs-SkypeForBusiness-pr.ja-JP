---
title: 'Lync Server 2013: 場所のポリシーをテストする'
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
ms.openlocfilehash: 2a954405cb8dbba842250e0545ac8661d4f3795c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a>Lync Server 2013 での場所のポリシーのテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-06-05_


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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、CsLocationPolicy コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

テスト用の Locationpolicy コマンドレットは、位置情報ポリシーがユーザーに割り当てられていることを確認します。 場所ポリシーは、E9 の機能とクライアントの場所に関連する設定を適用するために使用されます。 位置情報ポリシーは、ユーザーが E9 に対して有効になっているかどうかを決定します。回答が "yes" の場合は、緊急通話の動作は何ですか。 たとえば、位置情報ポリシーを使って、緊急通話 (米国内の 911) を構成する番号、企業のセキュリティを自動的に通知するかどうか、通話のルーティング方法を定義できます。

ユーザーまたはネットワークサブネット上の位置情報ポリシーをテストすることができます。 サブネットに対してテストを実行する場合 (サブネットパラメーターの値を指定)、コマンドレットはそのサブネットの位置情報ポリシーを解決しようとします。 場所のポリシーがサブネットに割り当てられていない場合、構成されたユーザーの位置情報ポリシーが取得されます。 サブネットポリシーが正常に取得された場合、出力には subnet-tagid で始まる LocationPolicyTagID 値が含まれます。 サブネットの場所ポリシーが見つからなかった場合は、LocationPolicyTagID は tagid を使用して開始されます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

テスト用の Locationpolicy コマンドレットを実行するには、事前に定義されたテストアカウント (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照) または Lync Server を有効にしているユーザーのアカウントのいずれかを使用します。 テストアカウントを使用してこのチェックを実行するには、テスト対象の Lync Server プールの FQDN を指定する必要があります。 次に例を示します。

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

実際のユーザーアカウントを使用してこのチェックを実行するには、最初に、アカウント名とパスワードを含む Windows PowerShell 資格情報オブジェクトを作成する必要があります。 次に、資格情報オブジェクトと、テスト用の (CsLocationPolicy) を呼び出すとアカウントに割り当てられた SIP アドレスを含める必要があります。

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

詳細については、「[テスト-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) 」コマンドレットのヘルプドキュメントを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

指定したユーザーが有効な場所のポリシーを持っている場合は、次のような結果が返され、Result プロパティは Success とマークされ**ます。**

EnhancedEmergencyServicesEnabled: true

LocationPolicyTagID: tagid

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待ち時間:00:00: 06.8630376

誤差

診断

指定したユーザーに対して有効な場所のポリシーが見つからない場合は、結果がエラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待ち時間: 00:00:00

エラー: 404、見つかりません

診断: ErrorCode = 4005、Source = atl-cs-001.litwareinc.com、

理由 = ターゲット URI が SIP で有効になっていないか、

残っ.

DiagnosticHeader の場合

指定したユーザーが有効でないため、テストが失敗したことを示します。アカウントが存在しないか、ユーザーが Lync Server を有効にしていないことが原因です。 アカウントの有効性を確認し、次のようなコマンドを実行することにより、そのアカウントが nm-14-14-3 番目に有効になっているかどうかを確認できます。

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

テスト用の場所のポリシーが失敗した場合は、Verbose パラメーターなどのテストを再実行することをお勧めします。

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose パラメーターが含まれている場合、テスト-CsLocationPolicy は、位置情報ポリシーを確認したときに試行された各操作のステップバイステップのアカウントを返します。 たとえば、次の出力は、無効なパスワードが提供されたため、Lync Server がテストユーザーにログオンできなかったことを示します。

登録リクエストの送信:

ターゲット Fqdn = atl-cs-011.litwareinc.com

ユーザー Sip アドレス = sip:kenmyer@litwareinc.com

レジストラーポート = 5061

認証の種類 ' IWA ' が選択されています。

Sip/atl に対する登録ヒット-.cs-litwareinc

"Register" アクティビティは "0.0601795" 秒で完了しました。

例外 ' ログオンは拒否されました。 正しい資格情報が使用されていて、アカウントがアクティブであることを確認します。 ワークフロー中に発生しました。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に、テスト用の場所のポリシーが失敗する可能性がある一般的な理由をいくつか示します。

  - 無効なユーザーアカウントが指定されました。 次のようなコマンドを実行すると、ユーザーアカウントが存在するかどうかを確認できます。
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。 Lync Server でユーザーアカウントが有効になっていることを確認するには、次のようなコマンドを実行します。
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server を有効にしていないことを意味します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

