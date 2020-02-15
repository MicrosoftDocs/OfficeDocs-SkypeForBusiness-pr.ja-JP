---
title: 'Lync Server 2013: Lync Phone Edition ログインのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbacccabc98829c90e01dc49099b65b829274c82
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a>Lync Server 2013 での Lync Phone Edition ログインのテスト

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テスト-CsPhoneBootstrap コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Test-CsPhoneBootstrap コマンドレットを使用すると、管理者は、特定のユーザー (自分に割り当てられている電話番号と PIN を使用) が Lync 2013 Phone Edition 互換デバイスからシステムにログオンできるかどうかを確認できます。 (テストを実行するために実際に必要なデバイスはありません)。

Test-CsPhoneBootstrap でチェックを実行できるようにするには、テスト対象のユーザー アカウントをホストするレジストラー プールが DHCP を使用して検出できる必要があります。 この方法でレジストラーが検出可能かどうかを判断するには、コマンドレット Get-csregistrarconfiguration を使用して、EnableDHCPServer プロパティの値を確認します。 このプロパティが False に設定されている場合は、Get-csregistrarconfiguration を使用してプロパティ値を True に設定し、DHCP を使用してレジストラーを検出可能にする必要があります。 これは、エンタープライズ DHCP サーバーを使用して、Lync Server 固有のオプションを構成することによっても実行できます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Test-CsPhoneBootstrap コマンドレットを実行するには、少なくとも、有効な Lync Server ユーザーの電話番号とクライアント暗証番号 (PIN) を指定する必要があります。 たとえば、次のコマンドは、電話番号12065551219と PIN 0712 を持つユーザーのログオン機能をテストします。

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

より包括的なチェックを行うには、ユーザーの SIP アドレスを含めることもできます。 その場合、テストが成功するには、電話番号、クライアント PIN、および SIP アドレスをすべて有効にする必要があります。

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

詳細については、「 [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

指定されたユーザーが Lync Server に接続できた場合は、次のような出力が得られます。 Result プロパティは Success としてマークされてい**ます。**

TargetUrihttps://atl-cs-001.litwareinc.com:443/CertProv/

Certプロビジョニングサービス svc

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間:00:00: 06.3981276

エラー

分析

指定したユーザーが接続を確立できなかった場合、結果はエラーとして表示され、追加情報が Error および診断プロパティに記録されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: エラー

待機時間:00:00: 04.1993845

エラー: Web チケットサービスの応答が受信されませんでした。

分析

前回の出力では、Web チケットサービスが応答しなかったため、テストが失敗したことが示されます。 これは、サービス自体に問題があるか、または SIP アドレス、電話番号、またはテスト/CsPhoneBootstrap に渡されたクライアント PIN が原因である可能性があります。 次のようなコマンドを使用して、ユーザーの SIP アドレスと電話番号を確認できます。

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

また、次のコマンドを使用して、ユーザーが有効な PIN を持っていることを確認できます。

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

テスト-CsPhoneBootstrap が失敗した場合は、次のように詳細なパラメーターを含めて、テストを再実行することをお勧めします。

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

Verbose パラメーターを指定すると、指定されたユーザーが Lync Server にログオンできるかどうかを確認したときに実行された各操作のステップバイステップのアカウントが返されます。 たとえば、正しくない PIN が含まれているセッションで、ログオンが失敗した場合の出力の一部を次に示します。

\\内線番号での pin 認証の使用: 12065551219 ピン: 0712

Web チケットを取得できませんでした

確かめ

\-Web サービスの url が有効で、web サービスが機能している

\-PhoneNo\\PIN を使用して認証する場合は、ユーザーの uri と一致していることを確認してください。

\-NTLM\\Kerberos 認証を使用している場合は、有効な資格情報を入力してください。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

テスト、CsPhoneBootstrap が失敗する原因としては、次のようなものがあります。

  - 無効な SIP アドレスを指定した可能性があります。 次のようなコマンドを使用して、SIP アドレスが正しいことを確認できます。
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - 無効な PIN が指定されている可能性があります。 ユーザーの PIN 番号を取得することはできませんが、次のようなコマンドを使用して、少なくともユーザーが PIN 番号を持っていることを確認できます。
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - 無効な電話番号が指定されている可能性があります。 ユーザーの電話を確認するには、次のようなコマンドを使用します。
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - レジストラープールは DHCP 対応になっていません。 レジストラープールが DHCP に対して有効になっているかどうかを確認するには、Get-csregistrarconfiguration コマンドレットを実行し、EnableDHCPServer プロパティの値を確認します。 次に例を示します。
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

