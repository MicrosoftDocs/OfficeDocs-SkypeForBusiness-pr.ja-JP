---
title: 'Lync Server 2013: スマートフォンへのプッシュ通知をテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94daa288757e2a0af446b455b951af9a990147b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a>Lync Server 2013 でのスマートフォンへのプッシュ通知をテストする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2017-03-15_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>確認のスケジュール</p></td>
<td><p>毎月</p></td>
</tr>
<tr class="even">
<td><p>テストツール</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要なアクセス許可</p></td>
<td><p>Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</p>
<p>Windows PowerShell のリモートインスタンスを使って実行する場合は、テスト-CsMcxPushNotification コマンドレットを実行するためのアクセス許可を持つ RBAC の役割をユーザーに割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

プッシュ通知サービス (Apple Push Notification Service および Microsoft プッシュ通知サービス) では、Lync クライアントを使用している場合でも、新しいインスタントメッセージや新しいボイスメールなどのイベントに関する通知を、iPhones、Windows Phone などのモバイルデバイスに送信できます。これらのデバイスでは、現在、バックグラウンドで一時停止または実行されています。 プッシュ通知サービスは、Microsoft サーバー上で実行されているクラウドベースのサービスです。 プッシュ通知を利用するには、プッシュ通知の受信者に接続し、認証する必要があります。 テスト-CsMcxPushNotification コマンドレットを使用すると、管理者は、プッシュ通知要求をエッジサーバー経由でプッシュ通知のクリアリングハウスにルーティングできることを確認できます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

プッシュ通知サービスをテストするには、CsMcxPushNotification コマンドレットを呼び出します。 エッジサーバーの完全修飾ドメイン名を指定していることを確認します。

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

詳細については、「[テスト-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)コマンドレット」のヘルプトピックを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

テスト-CsMcxPushNotification が成功すると、コマンドレットはテスト結果の成功を返します。

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待ち時間: 00:00:00

誤差

診断

テスト用の CsMcxPushNotification がプッシュ通知のクリアリングハウスに接続できない場合、通常、コマンドレットは失敗のテスト結果を返しません。 通常、コマンドは完全に失敗します。 次に例を示します。

テスト-CsMcxPushNotification: ネットワークから 504 (サーバータイムアウト) 応答を受信しましたが、操作に失敗しました。 詳細については、例外の詳細を参照してください。

行: 1 char:27

\+テスト-csmcxpushnotification \< \< \< \< -AccessEdgeFqdn lyncedge.mydomain.com

\+カテゴリ情報: OperationStopped: (:)\[テスト-CsMcxPushNotification\]、FailureResponseException

\+FullyQualifiedErrorId: WorkflowNotCompleted、Synmcxpushnotificationコマンドレットを実行します。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

プッシュ通知サービスが失敗した場合、通常、エッジサーバーとの通信に問題があるか、プッシュ通知のクリアリングハウスとの通信で問題があることを示します。 テスト-CsMcxPushNotification の実行時に問題が発生した場合は、まず、エッジサーバーが正常に動作していることを確認する必要があります。 1つの方法として、CsAVEdgeConnectivity コマンドレットを使用します。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

このチェックでは、指定したユーザーがエッジサーバーに接続できることを確認します。

エッジサーバーが正常に動作しているようであれば、プッシュ通知のクリアリングハウスに接続できないことがよくあります。 つまり、通常は、クリアリングの URI を正しく構成していないか、この URL を参照する DNS SRV レコードがないことを意味します。 次のコマンドを実行して、URI が正しい値 (sip:push@push.lync.com) に設定されていることを確認できます。

    Get-CsMcxConfiguration

PushNotificationProxyUri プロパティが sip:push@push.lync.com 以外の値に設定されている場合は、Set-McxConfiguration コマンドレットを使用してその問題を修正できます。 たとえば、次のコマンドは組織全体で URI を正しく設定します。

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

詳細については、「 [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration)コマンドレット」のヘルプトピックを参照してください。

URI が正しく構成されている場合は、次の手順を実行して、SIP ドメインとエッジサーバーに解決される DNS SRV レコードがあることを確認する必要があります。 これらのレコードを構成する方法の詳細については、「モビリティのための DNS の要件」を参照してください。 次のエラーメッセージは、通常、DNS レコードに問題があることを示します。

ネットワークから 504 (サーバータイムアウト) 応答を受信しましたが、操作に失敗しました。 詳細については、例外の詳細を参照してください。

このエラーメッセージが表示されると、テスト用の CsMcxConfiguration が失敗する可能性もあります。

テスト-CsMcxPushNotification: プッシュ通知要求は拒否されました。

行: 1 char:27

\+テスト-CsMcxPushNotification\<\<\<\<

\+カテゴリ情報: OperationStopped: (:)\[テスト-CsMcxPushNotification\]、SyntheticTransactionException

\+FullyQualifiedErrorId: WorkflowNotCompleted、Synmcxpushnotificationコマンドレットを実行します。

"プッシュ通知要求は拒否されました" というメッセージは通常、URL フィルタリングを有効にし、http: と https: プレフィックスをブロックしている場合に発生します。 次のようなコマンドを使用して、どのプレフィックスがブロックされるかを判断できます。

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

結果に http: または https: が表示される場合は、プッシュ通知が機能するように、ブロックされたプレフィックスリストから削除する必要があります。 この操作を実行するには、次のようなコマンドを使用します。

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

詳細については、「 [Set-Cシム Filterconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)コマンドレット」のヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

