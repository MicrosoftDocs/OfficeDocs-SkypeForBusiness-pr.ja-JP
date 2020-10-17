---
title: 'Lync Server 2013: Lync Server サービスのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e74a24818094d7de0edc4627f987464df048315f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519014"
---
# <a name="testing-lync-server-services-in-lync-server-2013"></a>Lync server 2013 での Lync Server サービスのテスト

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsComputer コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Test-CsComputer は、ローカルコンピューター上で実行されているすべての Lync Server 2013 サービスの状態を確認します。 (Test-CsComputer はローカルでのみ実行できますが、Windows PowerShell のリモートインスタンスからは実行できません)。また、このコマンドレットは、コンピューター上で適切なファイアウォールポートが開かれているかどうかを確認し、Lync Server 2013 のインストール時に作成された Active Directory グループが対応するローカルグループに追加されたかどうかを判断します。 たとえば、Test-CsComputer は、Active Directory グループ RTCUniversalUserAdmins が Administrators グループに追加されたことを確認します。

詳細については、「 [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Test-CsComputer コマンドレットは、ローカルコンピューターでのみ実行できます。 Windows PowerShell のリモートインスタンスから Test-CsComputer を呼び出すことはできません。 既定では、画面に表示される出力はほとんどありませんが、コマンドレットによって返される情報は、HTML ファイルに書き込まれるので、Test-CsComputer になります。 そのため、Test CsComputer を実行するたびに、Verbose パラメーターと Report パラメーターを含めることをお勧めします。 Verbose パラメーターは、コマンドレットの実行中に画面により詳細な出力を提供します。 Report パラメーターを使用すると、Test CsComputer で生成された HTML ファイルのファイルパスとファイル名を指定できます。 Report パラメーターを指定しない場合、HTML ファイルは自動的にユーザーのフォルダーに保存され、次のような名前が付けられます。 ce84964a-c4da-4622-ad34-c54ff3ed361f.html。

次のサンプルコマンドは Test-CsComputer を実行し、出力を C: LogsComputerTest.html という名前のファイルに保存し \\ \\ ます。

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

詳細については、「 [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

テストが成功したかどうかについては、検証チェックの数が多いので、テストが **成功** したかどうかを Test-CsComputer は報告しません。テストは **失敗しました**。 代わりに、生成された HTML ファイルを表示するには、Internet Explorer を使用して、各テストの成功または失敗を確認する必要があります。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

Test-CsComputer が失敗する可能性のある一般的な理由を次に示します。

  - テストコンピューターが Lync Server で使用可能になっていない可能性があります。 これは、コンピューター上の Lync Server サービスまたはサーバーの役割が変更され、Enable-CsComputer コマンドレットが実行されなかった場合に発生する可能性があります。 この問題を解決するには、次のコマンドを実行します。
    
        Enable-CsComputer

  - テストコンピューターでレプリケーションが最新の状態になっていない可能性があります。 Get-CsManagementStoreReplicationStatus コマンドレットを実行して、コンピューターの現在のレプリケーションの状態を確認できます。
    
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

