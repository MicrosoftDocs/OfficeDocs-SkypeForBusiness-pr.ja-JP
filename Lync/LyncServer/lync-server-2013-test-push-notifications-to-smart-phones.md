---
title: 'Lync Server 2013: スマートフォンへのプッシュ通知のテスト'
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
ms.openlocfilehash: 858c1ad3ad5776453a4a48505672c69083de1cc2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42021218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a>Lync Server 2013 でのスマートフォンへのプッシュ通知のテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2017-03-15_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>検証スケジュール</p></td>
<td><p>毎月</p></td>
</tr>
<tr class="even">
<td><p>テストツール</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要なアクセス許可</p></td>
<td><p>Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</p>
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テスト-CsMcxPushNotification コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

プッシュ通知サービス (Apple Push Notification Service および Microsoft プッシュ通知サービス) では、Lync クライアントの場合でも、新しいインスタントメッセージや新しいボイスメールなどのイベントに関する通知を、iPhones や Windows Phone などのモバイルデバイスに送信できます。これらのデバイスでは、現在バックグラウンドで中断または実行されています。 プッシュ通知サービスは、Microsoft サーバー上で実行されているクラウドベースのサービスです。 プッシュ通知を利用するには、プッシュ通知クリアリングハウスに接続して認証される必要があります。 テスト-CsMcxPushNotification コマンドレットを使用すると、管理者はプッシュ通知要求がエッジサーバーを経由してプッシュ通知クリアリングハウスにルーティングされることを確認できます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

プッシュ通知サービスをテストするには、テスト-CsMcxPushNotification コマンドレットを呼び出します。 エッジサーバーの完全修飾ドメイン名を指定していることを確認してください。

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

詳細については、 [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

テスト-CsMcxPushNotification が成功した場合、コマンドレットはテスト結果成功を返します。

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間: 00:00:00

エラー

分析

テスト-CsMcxPushNotification がプッシュ通知クリアリングハウスに接続できない場合、通常、コマンドレットは失敗のテスト結果を返しません。 その代わりに、コマンドは完全に失敗します。 例:

テスト-CsMcxPushNotification: ネットワークから 504 (サーバータイムアウト) 応答が受信され、操作に失敗しました。 詳細については、例外の詳細を参照してください。

行: 1 文字:27

\+テスト-csmcxpushnotification \< \< \< \< -AccessEdgeFqdn lyncedge.mydomain.com

\+カテゴリ情報: OperationStopped: (:)\[テスト-CsMcxPushNotification\]、FailureResponseException

\+FullyQualifiedErrorId: WorkflowNotCompleted、TestMcxPushNotificationCmdlet (TestMcxPushNotificationCmdlet)

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

プッシュ通知サービスが失敗した場合は、通常、エッジサーバーとの通信に関する問題、またはプッシュ通知クリアリングハウスとの通信に問題があることを示します。 テスト-CsMcxPushNotification の実行時に問題が発生した場合は、まず、エッジサーバーが正しく動作していることを確認する必要があります。 これを行う方法の1つは、Test-csavedgeconnectivity コマンドレットを使用することです。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

このチェックは、指定されたユーザーがエッジサーバーに接続できることを確認します。

エッジサーバーが正常に動作しているように見える場合、プッシュ通知のクリアリングハウスに接続できないことがよくあります。 そのため、通常は、この URL をポイントする DNS SRV レコードが存在しないか、またはクリアリングハウス URI が正しく構成されていないことを意味します。 次のコマンドを実行することによって、URI が正しい値 (sip:push@push.lync.com) に設定されていることを確認できます。

    Get-CsMcxConfiguration

PushNotificationProxyUri プロパティが sip:push@push.lync.com 以外の値に設定されている場合は、この問題を修正するには、Set-McxConfiguration コマンドレットを使用します。 たとえば、次のコマンドを実行すると、組織全体に URI が正しく設定されます。

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

詳細については、「 [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration)コマンドレット」のヘルプトピックを参照してください。

URI が正しく構成されている場合は、次の手順として、SIP ドメインおよびエッジサーバーに解決する DNS SRV レコードがあることを確認する必要があります。 これらのレコードを構成する方法の詳細については、ヘルプトピック「Mobility の DNS 要件」を参照してください。 次のエラーメッセージは、通常、DNS レコードに問題があることを示しています。

ネットワークからの 504 (サーバータイムアウト) 応答を受信し、操作に失敗しました。 詳細については、例外の詳細を参照してください。

また、次のエラーメッセージが表示され、テスト-CsMcxConfiguration が失敗する可能性もあります。

テスト-CsMcxPushNotification: プッシュ通知要求が拒否されました。

行: 1 文字:27

\+テスト-CsMcxPushNotification\<\<\<\<

\+カテゴリ情報: OperationStopped: (:)\[テスト-CsMcxPushNotification\]、SyntheticTransactionException

\+FullyQualifiedErrorId: WorkflowNotCompleted、TestMcxPushNotificationCmdlet (TestMcxPushNotificationCmdlet)

通常、[プッシュ通知要求は拒否されました] メッセージは、URL フィルターを有効にしていて、http: および https: プレフィックスをブロックしている場合に発生します。 次のようなコマンドを使用して、どのプレフィックスがブロックされているかを判断できます。

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

[Http:] または [https:] が結果に表示されている場合は、プッシュ通知を機能させるために、ブロックされたプレフィックスリストから削除する必要があります。 これを行うには、次のようなコマンドを使用します。

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

詳細については、「 [Set-Cシム Filterconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)コマンドレット」のヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

