---
title: 'Lync Server 2013: サービスのアクティブ化とグループのアクセス許可のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38bc988ec1fdfeb0c4fd5714f31342902fe45821
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a>Lync Server 2013 でのサービスのアクティブ化とグループのアクセス許可のテスト

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テストコマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Test-CsTopology コマンドレットを使用すると、Lync Server 2013 がグローバルスコープで正常に機能していることを確認できます。 既定では、このコマンドレットは Lync Server インフラストラクチャ全体をチェックし、必要なサービスが実行されていること、およびこれらのサービスに対して適切なアクセス許可が設定されていることと、Lync Server のインストール時に作成されたユニバーサルセキュリティグループに対して適切なアクセス許可が設定されている.

Lync Server のインストールの有効性を検証するだけでなく、特定のサービスの有効性を確認することもできます。 たとえば、次のコマンドは、プール atl-cs-001.litwareinc.com 上の音声ビデオ会議サーバーの状態をチェックします。

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a>テストの実行

既定では、テスト用の出力画面に表示される出力はほとんどありません。 代わりに、コマンドレットによって返される情報は、HTML ファイルに書き込まれます。 Report パラメーターを使用すると、テスト用の HTML ファイルのファイルパスとファイル名を指定できます。 Report パラメーターを指定しない場合は、HTML ファイルは自動的にユーザーのフォルダーに保存され、次のような名前が付けられます。 ce84964a-c4da-c4da-4622 2-ad34-c54ff3ed361f .html。

次のサンプルコマンドは、テスト-CsTopology 使い方を実行し、出力を C:\\Logs\\computertest .html という名前のファイルに保存します。

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

詳細については、[テスト](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology)用のヘルプドキュメントを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

Test コマンドレットは、ほとんどのテストコマンドレットとは異なり、成功または失敗の報告を返します。 これは、コマンドレットが実行されるたびに実行する必要のある多くの検証チェックが行われるためです。 代わりに、Internet Explorer を使用して表示できる HTML レポートにデータが保存されます。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

テスト-Cstopostoが失敗する主な理由を次に示します。

  - テストコンピューターでレプリケーションが最新の状態ではない可能性があります。 Get-csmanagementstorereplicationstatus コマンドレットを実行して、コンピューターの現在のレプリケーションの状態を確認できます。
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    レプリケーションの状態が最新ではない場合は、次のようなコマンドを使用して、レプリケーションを手動で強制的に実行できます。
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - トポロジを有効にする必要がある場合があります。 Lync Server トポロジ (ローカルコンピューターに影響する可能性がある変更) を変更する場合は、新しいトポロジを有効にする必要があります。 次のコマンドを実行することによって、いつでもトポロジを有効にすることができます。
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

