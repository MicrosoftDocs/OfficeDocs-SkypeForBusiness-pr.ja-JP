---
title: 'Lync Server 2013: Lync 通知への Exchange のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Exchange to Lync notifications
ms:assetid: ed2d6325-3cf5-4450-9951-03092bcb0a7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727315(v=OCS.15)
ms:contentKeyID: 63969665
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37f163d5a43dce9672535ec3d78f360bcec8d926
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a>Lync Server 2013 での Lync からの通知への Exchange のテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-11-01_


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
<p>Windows PowerShell のリモートインスタンスを使って実行する場合は、 <strong>CsExStorageNotification</strong>コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

**CsExStorageNotification**コマンドレットを使用して、ユーザーの連絡先リストが更新されたときに、Microsoft Exchange Server 2013 notification Service が Lync Server 2013 に通知することを確認します。 このコマンドレットは、ユニファイド連絡先ストアを使用している場合にのみ有効です。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

例1に示すコマンドは、Lync Server ストレージサービスが、ユーザー sip:kenmyer@litwareinc.com の Microsoft Exchange Server メールボックス通知サービスに接続できるかどうかを確認するものです。 この例では、NetNamedPipe は WCF バインディングとして使用されます。

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

Exchange の統合が正しく構成されている場合は、次のような結果が返され、Result プロパティは**Success**とマークされます。

ターゲット Fqdn: atl-cs-001.litwareinc.com

結果: 成功

待ち時間: 00:00:00

エラーメッセージ:

診断

指定したユーザーが通知を受信できない場合、結果はエラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。

ターゲット Fqdn: atl-cs-001.litwareinc.com

結果: エラー

待ち時間: 00:00:00

エラーメッセージ: 10060、接続されているパーティのため、接続に失敗しました

一定の期間が経過した後に正しく応答しなかった場合、または

接続されているホストに、接続に失敗しました

10.188.116.96 に応答できませんでした: 5061

内部例外: 接続の試行が失敗したため、接続できませんでした。

しばらくしても、接続されているパーティが正しく応答しませんでした

接続されているホストが原因で、時刻、または接続に失敗しました

さんが10.188.116.96 に応答できませんでした: 5061

診断

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に **、テスト-CsExStorageNotification**が失敗する可能性がある一般的な理由を示します。

  - 指定されたパラメーター値が正しくありません。 使用する場合は、オプションのパラメーターが正しく構成されている必要があります。または、テストが失敗します。 省略可能なパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。

  - Microsoft Exchange Server が正しく構成されていないか、まだ展開されていない場合、このコマンドは失敗します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

