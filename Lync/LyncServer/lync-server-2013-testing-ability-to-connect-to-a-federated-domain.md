---
title: 'Lync Server 2013: フェデレーションドメインに接続するためのテスト機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82c44cf7cff78fc93054679ae1bc4c66bc6b4c40
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42016238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a>Lync Server 2013 からフェデレーションドメインに接続するためのテスト機能

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合は、Test-csfederatedpartner コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Test-CsFederatedPartner を実行して、フェデレーション パートナーのドメインに接続できることを確認します。 ドメインへの接続を確認するには、そのドメインが許可された (フェデレーション) ドメインのコレクションに記載されている必要があります。 次のコマンドを使用して、許可されたドメインの一覧にあるドメインの一覧を取得できます。

    Get-CsAllowedDomain

詳細については、 [test-csfederatedpartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)コマンドレットのヘルプドキュメントを参照してください。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

FederatedPartner コマンドレットでは、エッジサーバーの FQDN とフェデレーションパートナーの FQDN という2つの情報が必要です。 たとえば、次のコマンドは、ドメイン contoso.com に接続できるかどうかをテストします。

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

次のコマンドを実行すると、許可されたドメインの一覧に現在あるすべてのドメインへの接続をテストできます。

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

詳細については、 [test-csfederatedpartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)コマンドレットのヘルプドキュメントを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

指定したドメインに接続できる場合は、次のような出力が得られ、Result プロパティは Success としてマークされ**ます。**

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間: 00:00:00

エラー

分析

指定したドメインに接続できない場合は、結果がエラーとして表示され、追加情報が Error および診断プロパティに記録されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間: 00:00:00

エラー: 504、サーバーのタイムアウト

診断: ErrorCode = 2, Source = litwareinc, Reason = 「」を参照

応答コードと理由の語句。

DiagnosticHeader ()

たとえば、前回の出力では、サーバータイムアウトエラーによってテストが失敗したことが示されます。 これは、通常、ネットワーク接続の問題またはエッジサーバーへの接続の問題を示します。

Test-csfederatedpartner が失敗した場合は、次のように詳細なパラメーターを含めて、テストを再実行することをお勧めします。

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

Test-csfederatedpartner が失敗する可能性のある一般的な原因を次に示します。

  - エッジサーバーを使用できない可能性があります。 次のコマンドを使用して、エッジサーバーの Fqdn を使用できます。
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    その後、各エッジサーバーに ping して、ネットワーク経由でアクセスできることを確認できます。 例:
    
        ping atl-edge-001.litwareinc.com

  - 指定したドメインが、許可されたドメインリストに表示されていない可能性があります。 許可されたドメインリストに追加されたドメインを確認するには、次のコマンドを使用します。
    
        Get-CsAllowedDomain
    
    ユーザーが通信をブロックされたドメインの一覧を表示するには、次のコマンドを使用します。
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

