---
title: 'Lync Server 2013: 統合連絡先ストアのアクセスのテスト'
description: 'Lync Server 2013: 統合連絡先ストアへのアクセスをテストします。'
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
ms.openlocfilehash: 58238685133c51130c414e0d7a8cd761d0233f5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556083"
---
# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a>Lync Server 2013 での統合連絡先ストアアクセスのテスト

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-05-15_


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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合は、 <strong>test-csunifiedcontactstore</strong> コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Lync Server 2013 で導入された統合連絡先ストアによって、管理者は、ユーザーの連絡先を Lync Server ではなく Microsoft Exchange Server 2013 に保存するオプションを選択できます。 これにより、ユーザーは Lync 2013 に加えて、Outlook Web Access 内の同じ連絡先セットにアクセスできるようになります。 (または、引き続き Lync Server に連絡先を保存することができます。 その場合、ユーザーは2つの別々の連絡先セットを保持する必要があります。1つは Outlook と Outlook Web Access で使用し、もう1つは Lync 2013 で使用するためです。

**Test-csunifiedcontactstore**コマンドレットを実行して、ユーザーの連絡先が統合連絡先ストアに移動されたかどうかを判断できます。 **Test-csunifiedcontactstore**コマンドレットは、指定されたユーザーアカウントを取得し、統合連絡先ストアに接続して、ユーザーの連絡先を取得しようとします。 連絡先を取得できない場合、コマンドは "ユーザーの連絡先は受信されていません" というメッセージと共に失敗します。 ユーザーの連絡先が存在することを確認します。

ユーザーが統合連絡先ストアに正常に移行されたが、連絡先リストに連絡先が存在しない場合、 **test-csunifiedcontactstore** コマンドレットは失敗します。 **Test-csunifiedcontactstore**コマンドレットを正常に完了するには、指定されたユーザーが少なくとも1つの連絡先を持っている必要があります。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

次の例に示すコマンドは、ユーザー litwareinc kenmyer の連絡先が統合連絡先ストアにあるかどうかを判断し \\ ます。 これを行うには、この例の最初のコマンド **は、litwareinc コマンドレットを** 使用して、user Kenmyer の Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成し \\ ます。 有効な資格情報オブジェクトを作成し、 **test-csunifiedcontactstore** コマンドレットでチェックを実行できることを確認するには、このアカウントのパスワードを指定する必要があることに注意してください。

この例の2番目のコマンドでは、指定された credentials オブジェクト ($x) とユーザー litwareinc kenmyer の SIP アドレスを使用して、その \\ 連絡先が統合連絡先ストアに存在するかどうかを判断します。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

連絡先ストアへのアクセスが正しく構成されている場合は、次のような出力が得られ、Result プロパティは Success としてマークされ **ます。**

ターゲット Fqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間:00:00: 14.9862716

エラーメッセージ:

分析

連絡先ストアへのアクセスが正しく構成されていない場合、結果は **失敗**として表示され、追加情報が Error および診断プロパティに記録されます。

警告: 指定された完全修飾のレジストラーポート番号を読み取ることができませんでした

ドメイン名 (FQDN)。 既定のレジストラーポート番号を使用します。 例外

System.invalidoperationexception: トポロジ内に一致するクラスターが見つかりませんでした。

下部

TryRetri を SipSyntheticTransaction していることを示します。

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

ターゲット Fqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間: 00:00:00

エラーメッセージ: 10060。接続しているパーティが原因で接続に失敗しました。

一定期間後に正しく応答しなかったか、または

接続されたホストの接続に失敗しました。

10.188.116.96: 5061 に応答できませんでした

内部例外: 接続の試行が失敗しました。

接続されたパーティは、一定期間の後に正しく応答しませんでした

接続されているホストが原因で、接続に失敗しました。

10.188.116.96: 5061 に応答できませんでした

分析

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

**Test-csunifiedcontactstore**が失敗する可能性のある一般的な原因を次に示します。

  - 指定されたパラメーター値が正しくありません。 省略可能なパラメーターが使用されている場合、オプションのパラメーターが正しく構成されている必要があります。テストは失敗します。 オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。

  - 統合連絡先ストアに接続できませんでした。ユーザーの連絡先を取得しようとしましたができませんでした。 ネットワーク接続の問題が発生している可能性があります。

</div>

<div>

## <a name="see-also"></a>関連項目


[新しい-Csuserサービスポリシー](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[設定-Csuserサービスポリシー](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

