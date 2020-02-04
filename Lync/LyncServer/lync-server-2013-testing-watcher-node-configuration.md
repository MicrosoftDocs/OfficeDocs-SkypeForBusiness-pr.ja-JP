---
title: 'Lync Server 2013: ウォッチャーノード構成のテスト'
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
ms.openlocfilehash: 920fc39d3800f83a2d40a613c391b2f0c93e4dac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745267"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a>Lync Server 2013 でのウォッチャーノード構成のテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-11-03_


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
<p>Windows PowerShell のリモートインスタンスを使って実行する場合は、 <strong>CsWatcherNodeConfiguration</strong>コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Microsoft System Center Operations Manager を使って Lync Server 2013 を監視している場合は、"ウォッチャーノード" を設定することができます。定期的に自動的に実行されるコンピューターで、次のようにして Lync Server が動作していることを確認します。れる. ウォッチャーノードはプールに割り当てられ、 **CsWatcherNodeConfiguration**コマンドレットを使用して管理されます。 System Center Operations Manager を使用している場合は、監視ノードをインストールする必要はないことに注意してください。 ウォッチャーノードを使用しなくてもシステムを監視することができます。 唯一の違いは、実行しようとしている代理トランザクションは、Operations Manager によって自動的に呼び出されるのではなく手動で呼び出す必要がある点です。

**CsWatcherNodeConfiguration**コマンドレットを使用すると、ウォッチャーノードが正しく構成されていることを確認し、有効な Lync Server 2013 プールに割り当てられていることを確認できます。 **CsWatcherNodeConfiguration**コマンドレットは、ウォッチャーノード自体で実行されている必要があることに注意してください。 リモートコンピューターに対してコマンドレットを実行することはできません。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

次のコマンドは、組織で使用されている各ウォッチャーノードの構成設定を確認します。

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

次の正常なサンプル出力は、4台のエッジサーバーを備えたシステムを示しています。

トポロジに対するターゲットプールの atl-cs-001.litwareinc.com を検証しています。

成功: ターゲットプール atl-cs-001.litwareinc.com はトポロジ内に存在します。

成功: ターゲットプールの atl-cs-001.litwareinc.com には、レジストラーの役割がインストールされています。

成功: ターゲットプール atl-cs-001.litwareinc.com はサポートされているバージョンです。

成功: 5061 ターゲットプール atl-cs-001.litwareinc.com のポート番号が正しい。

ウォッチャーノード構成で見つからないプールの確認が開始されました。 エラーが検出された場合は、印刷されます。

ウォッチャーノード構成で見つからないプールの確認が完了しました。

ウォッチャーノードのインストールによって作成されたウォッチャーノードレジストリキーの確認が開始されました。 エラーが検出された場合は、印刷されます。

ウォッチャーノードのインストールによって作成されたウォッチャーノードレジストリキーの確認は完了しています。 検出された認証の種類は Negotiate です。

テストユーザーの資格情報 sip の存在が正常に検証されました: user1@ atl-cs-001.litwareinc.com (credential management store)。

テストユーザーの資格情報 sip の存在が正常に検証されました: user2@ atl-cs-001.litwareinc.com (credential management store)。

ウォッチャーノード構成で見つからないプールの確認が開始されました。 エラーが検出された場合は、印刷されます。

警告: Pool atl-cs-001.litwareinc.com にレジストラーが含まれています

ロールはインストールされていますが、テストユーザーが構成されていません。

ウォッチャーノード構成で見つからないプールの確認が完了しました。

ウォッチャーノードのインストールによって作成されたウォッチャーノードレジストリキーの確認は、

さ. エラーが検出された場合は、印刷されます。

CsWatcherNodeConfiguration: で正常性レジストリキーが見つかりません

Microsoft\\\\リアルタイム通信ソフトウェア。 Watcher ノードの .msi が

正しくインストールされている。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に **、テスト-CsWatcherNodeConfiguration**が失敗する可能性がある一般的な理由を示します。

  - ウォッチャーノードが正しくインストールされていません。

  - テストユーザーが構成されていません。

</div>

<div>

## <a name="see-also"></a>関連項目


[Get-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[New-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[Remove-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[Set-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

