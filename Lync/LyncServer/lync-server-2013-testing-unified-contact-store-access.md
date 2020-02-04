---
title: 'Lync Server 2013: ユニファイド連絡先ストアへのアクセスのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47d5d216a1d7a389f20bf2c59f94baf54636d409
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a>Lync Server 2013 での統合連絡先ストアへのアクセスのテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-05-15_


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
<p>Windows PowerShell のリモートインスタンスを使って実行する場合は、 <strong>CsUnifiedContactStore</strong>コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Lync Server 2013 で導入された統合連絡先ストアでは、管理者はユーザーの連絡先を Lync Server ではなく Microsoft Exchange Server 2013 に保存するオプションが提供されます。 これにより、ユーザーは Lync 2013 だけでなく、Outlook Web Access でも同じ連絡先のセットにアクセスできるようになります。 (または、引き続き Lync Server に連絡先を保存することができます。 この場合、ユーザーは、Outlook と Outlook Web Access で使用するためと Lync 2013 で使用するために、2つの別々の連絡先を管理する必要があります。

**CsUnifiedContactStore**コマンドレットを実行することで、ユーザーの連絡先がユニファイド連絡先ストアに移動されたかどうかを確認できます。 **CsUnifiedContactStore**コマンドレットは、指定されたユーザーアカウントを受け取り、ユニファイド連絡先ストアに接続して、ユーザーの連絡先を取得しようとします。 連絡先を取得できない場合、コマンドは "ユーザーの連絡先は受信されませんでした" というメッセージと共に失敗します。 ユーザーに対して連絡先が存在することを確認します。 "

ユーザーが統合された連絡先ストアに正常に移行したが、連絡先リストに連絡先がない場合は、 **CsUnifiedContactStore**コマンドレットが失敗します。 指定したユーザーは、 **CsUnifiedContactStore**コマンドレットを正常に完了するために、少なくとも1つの連絡先を持っている必要があります。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

次の例に示すコマンドは、ユーザー litwareinc\\kenmyer の連絡先がユニファイド連絡先ストアで見つかるかどうかを決定します。 これを行うには、この例の最初のコマンドでは、 **Credential**コマンドレットを使って、user litwareinc\\kenmyer の Windows PowerShell コマンドラインインターフェイスの credentials オブジェクトを作成します。 有効な資格情報オブジェクトを作成し、 **CsUnifiedContactStore**コマンドレットでチェックを実行できるようにするには、このアカウントのパスワードを指定する必要があることに注意してください。

この例の2番目のコマンドでは、指定された資格情報オブジェクト ($x) と\\ユーザーの litwareinc KENMYER の SIP アドレスを使って、自分の連絡先がユニファイド連絡先ストアで見つかるかどうかを確認します。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

連絡先ストアへのアクセスが適切に構成されている場合は、次のような結果が返され、Result プロパティは Success とマークされ**ます。**

ターゲット Fqdn: atl-cs-001.litwareinc.com

結果: 成功

待ち時間:00:00: 14.9862716

エラーメッセージ:

診断

連絡先ストアへのアクセスが正しく構成されていない場合は、結果が**失敗**として表示され、エラーと診断のプロパティに追加の情報が記録されます。

警告: 指定した完全修飾のレジストラーポート番号の読み取りに失敗しました

ドメイン名 (FQDN)。 既定のレジストラーポート番号を使用します。 エラー

InvalidOperationException: トポロジで一致するクラスターが見つかりませんでした。

自宅

SipSyntheticTransaction-TryRetri の同期を行います。

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

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

次に **、テスト-CsUnifiedContactStore**が失敗する可能性がある一般的な理由を示します。

  - 指定されたパラメーター値が正しくありません。 使用する場合は、オプションのパラメーターが正しく構成されている必要があります。または、テストが失敗します。 省略可能なパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。

  - ユニファイド連絡先ストアに接続できませんでした。ユーザーの連絡先を取得しようとしましたが、できませんでした。 ネットワーク接続に問題がある可能性があります。

</div>

<div>

## <a name="see-also"></a>関連項目


[New-CsUserServicesPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[Set-CsUserServicesPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

