---
title: 'Lync Server 2013: Lync Server サービスのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b193473ad5941c647c572fae1b7cb5e7ece7f95d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-server-services-in-lync-server-2013"></a>Lync server 2013 での Lync Server サービスのテスト

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、CsComputer コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

テスト-CsComputer は、ローカルコンピューターで実行されているすべての Lync Server 2013 サービスの状態を確認します。 (Test-CsComputer はローカルでのみ実行できます。 Windows PowerShell のリモートインスタンスから実行することはできません)。このコマンドレットは、コンピューター上で適切なファイアウォールポートが開かれているかどうかを確認し、Lync Server 2013 のインストール時に作成された Active Directory グループが、対応するローカルグループに追加されたかどうかを確認します。 たとえば、[テスト] コンピューターは、[Active Directory グループ RTCUniversalUserAdmins が管理者グループに追加されたことを確認します。

詳細については、「 [CsComputer のテスト](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer)」コマンドレットのヘルプドキュメントを参照してください。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

テスト用のコンピューターのコマンドレットは、ローカルコンピューターでのみ実行できます。 Windows PowerShell のリモートインスタンスからテスト用コンピューターを呼び出すことはできません。 既定では、テスト用のコンピューターは画面上に非常に小さな出力を表示します。代わりに、コマンドレットによって返される情報は HTML ファイルに書き込まれます。 このため、テスト用のコンピューターを実行するときは、必ず Verbose パラメーターと Report パラメーターを含めることをお勧めします。 Verbose パラメーターは、コマンドレットが実行されている間、画面上により詳細な出力を提供します。 レポートパラメーターを使用すると、CsComputer によって生成された HTML ファイルのファイルパスとファイル名を指定できます。 レポートパラメーターが含まれていない場合、HTML ファイルは [ユーザー] フォルダーに自動的に保存され、次のような名前が付けられます。 ce84964a-c4da-4622 2-ad34-361f、.html

次の例のコマンドは、テスト用のコンピューターを実行して、出力を C:\\Logs\\computertest .html という名前のファイルに保存します。

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

詳細については、「 [CsComputer のテスト](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer)」コマンドレットのヘルプドキュメントを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

テストによって実行される確認チェックの数が原因で、テストに不合格になった、テストが**成功**した、またはいいえというテストが**失敗**します。 代わりに、生成された HTML ファイルを Internet Explorer を使って表示し、各テストの成功または失敗を確認する必要があります。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に、テスト用のコンピューターで障害が発生する一般的な理由をいくつか示します。

  - テストコンピューターが Lync Server で使用できるようになっていない可能性があります。 この問題は、コンピューター上の Lync Server サービスまたはサーバーの役割が変更され、かつ、CsComputer コマンドレットが実行されていない場合に発生する可能性があります。 この問題を解決するには、次のコマンドを実行します。
    
        Enable-CsComputer

  - テストコンピューターのレプリケーションが最新ではない可能性があります。 CsManagementStoreReplicationStatus コマンドレットを実行して、コンピューターの現在のレプリケーションの状態を確認できます。
    
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

