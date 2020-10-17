---
title: 'Lync Server 2013: 監視ノード構成のテスト'
description: 'Lync Server 2013: 監視ノードの構成をテストしています。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1eeb141eee011d7e06f5dd49e483e026484d733
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546843"
---
# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a>Lync Server 2013 での監視ノード構成のテスト

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-11-03_


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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合は、 <strong>set-cswatchernodeconfiguration</strong> コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Microsoft System Center Operations Manager を使用して Lync Server 2013 を監視している場合は、「監視ノード」を設定することもできます。定期的に、自動的に実行されるコンピューターは、Lync Server が期待どおりに動作していることを確認するために、代理トランザクションを実行します。 監視ノードはプールに割り当てられ、 **set-cswatchernodeconfiguration** コマンドレットを使用して管理されます。 System Center Operations Manager を使用している場合は、監視ノードをインストールする必要はないことに注意してください。 監視ノードを使用せずにシステムを監視することもできます。 唯一の違いは、実行する代理トランザクションは、Operations Manager によって自動的に呼び出されるのではなく、手動で起動する必要があることです。

**Set-cswatchernodeconfiguration**コマンドレットを使用すると、監視ノードが正しく構成されており、有効な Lync Server 2013 プールに割り当てられていることを確認できます。 **Set-cswatchernodeconfiguration**コマンドレットは監視ノード自体で実行する必要があることに注意してください。 リモートコンピューターに対してコマンドレットを実行することはできません。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

次のコマンドは、組織で使用されている各監視ノードの構成設定を確認します。

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

次の正常なサンプル出力は、エッジサーバーが4台あるシステムを示しています。

トポロジに対してターゲットプール atl-cs-001.litwareinc.com を検証します。

成功: トポロジにターゲットプール atl-cs-001.litwareinc.com が存在します。

成功: ターゲットプール atl-cs-001.litwareinc.com には、レジストラーの役割がインストールされています。

成功: ターゲットプール atl-cs-001.litwareinc.com がサポートされているバージョンです。

成功: 5061 ターゲットプール atl-cs-001.litwareinc.com のポート番号が正しい。

監視ノード構成で不足しているプールの確認が開始されます。 エラーが検出された場合は、出力されます。

監視ノード構成で不足しているプールの確認が完了しました。

監視ノードのインストールによって作成された監視ノードレジストリキーの確認が開始されます。 エラーが検出された場合は、出力されます。

監視ノードのインストールによって作成された監視ノードレジストリキーの確認が完了しました。 検出された認証の種類は Negotiate です。

テストユーザーの資格情報 sip が存在することが正常に検証されました。資格情報管理ストアで user1@ atl-cs-001.litwareinc.com。

テストユーザーの資格情報 sip が存在することが正常に検証されました。資格情報管理ストアで user2@ atl-cs-001.litwareinc.com。

監視ノード構成で不足しているプールの確認が開始されます。 エラーが検出された場合は、出力されます。

警告: プール atl-cs-001.litwareinc.com にレジストラーがあります

役割がインストールされましたが、それに対して構成されたテストユーザーがありません。

監視ノード構成で不足しているプールの確認が完了しました。

監視ノードのインストールによって作成された監視ノードレジストリキーの確認は、

なかっ. エラーが検出された場合は、出力されます。

Test-CsWatcherNodeConfiguration: で正常性レジストリキーが見つかりません

ソフトウェア \\ Microsoft \\ のリアルタイムコミュニケーション。 監視ノード .msi がであることを確認してください。

正しくインストールされている。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

**Set-cswatchernodeconfiguration**が失敗する可能性のある一般的な原因を次に示します。

  - 監視ノードが正しくインストールされていません。

  - テストユーザーが構成されていません。

</div>

<div>

## <a name="see-also"></a>関連項目


[Set-cswatchernodeconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[Set-cswatchernodeconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[Set-cswatchernodeconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[Set-cswatchernodeconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

