---
title: 'Lync Server 2013: サービスのアクティブ化とグループのアクセス許可をテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6616e1f2835ab55f9e3e8f98e5a8693ef3d2fb4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a>Lync Server 2013 でのサービスのアクティブ化とグループのアクセス許可のテスト

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
<p>Windows PowerShell のリモートインスタンスを使って実行する場合、ユーザーには、テスト-CsTopology コマンドレットを実行するアクセス許可が与えられた RBAC の役割を割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

テスト用の CsTopology コマンドレットを使用すると、Lync Server 2013 がグローバルスコープで正常に機能していることを確認できます。 既定では、コマンドレットは Lync Server インフラストラクチャ全体をチェックし、必要なサービスが実行されていること、およびこれらのサービスに適切な権限が設定されていること、および Lync Server をインストールするときに作成されるユニバーサルセキュリティグループについて確認します。.

Lync Server のインストールの有効性を確認するだけでなく、テスト用に特定のサービスの有効性を確認することもできます。 たとえば、次のコマンドは、プール atl-cs-001.litwareinc.com で A/V 会議サーバーの状態を確認します。

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a>テストの実行

既定では、テスト用の CsTopology 内容は画面上に非常に小さな出力が表示されます。 代わりに、コマンドレットによって返される情報は、HTML ファイルに書き込まれます。 Report パラメーターを使用すると、テスト用に生成された HTML ファイルのファイルパスとファイル名を指定できます。 レポートパラメーターが含まれていない場合、HTML ファイルは [ユーザー] フォルダーに自動的に保存され、次のような名前が付けられます。 ce84964a-c4da-4622 2-ad34-361f、.html

次の例のコマンドは、テスト用の CsTopology ツールを実行して、出力を C\\:\\Logs computertest .html という名前のファイルに保存します。

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

詳細については、「[テスト-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology)ツールレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

テスト用コマンドレットのほとんどは、テスト用のコマンドレットによって、成功または失敗を報告します。 一部では、コマンドレットが実行されるたびに実行する必要がある多数の確認チェックが行われるためです。 代わりに、Internet Explorer を使用して表示できる HTML レポートにデータが保存されます。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に、テスト用の CsTopology が失敗する一般的な理由をいくつか示します。

  - テストコンピューターのレプリケーションは最新ではない可能性があります。 CsManagementStoreReplicationStatus コマンドレットを実行して、コンピューターの現在のレプリケーションの状態を確認できます。
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    レプリケーションの状態が最新でない場合は、次のようなコマンドを使用して、手動でレプリケーションを強制的に実行できます。
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - トポロジを有効にする必要がある場合があります。 Lync Server のトポロジ (ローカルコンピューターに影響を与える可能性のある変更) を変更する場合は、新しいトポロジを有効にする必要があります。 このコマンドを実行すると、いつでもトポロジーを有効にすることができます。
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

