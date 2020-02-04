---
title: 'Lync Server 2013: ボイスルール、ルート、ポリシーをテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c3b2d98846e537a9a416eaabaf6b02627c7273f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a>Lync Server 2013 でのボイスルール、ルート、ポリシーのテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-05-20_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>確認のスケジュール</p></td>
<td><p>毎月</p></td>
</tr>
<tr class="even">
<td><p>テストツール</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要なアクセス許可</p></td>
<td><p>Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</p>
<p>Windows PowerShell のリモートインスタンスを使って実行する場合は、Get-csvoiceuser コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

ユーザーが電話をかけると、通話の発信先のルートは、そのユーザーに割り当てられているポリシーとダイヤルプランの両方によって異なります。 ユーザーの SIP アドレスと電話番号を指定すると、Get-csvoiceuser コマンドレットによって、問題のユーザーがその番号への呼び出しを完了できるかどうかが確認されます。 テストが成功した場合、Get-csvoiceuser は次の値を返します。

  - 番号が164形式に変換されます (ユーザーのダイヤルプランに基づく)

  - 翻訳を提供した正規化ルール

  - 使用されているボイスルート (ルートの優先順位に基づく)

  - ユーザーのボイスポリシーを音声ルートにリンクした電話の使用状況。

Get-csvoiceuser を使用すると、特定の電話番号が予期したとおりにルーティングおよび翻訳されるかどうかを判断でき、個々のユーザーが経験した通話関連の問題のトラブルシューティングに役立ちます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Get-csvoiceuser コマンドレットを実行するときには、ダイヤルされる番号とテストされるユーザーアカウントの Id の2つの情報を提供する必要があります。 たとえば、次のコマンドは、SIP アドレス sip:kenmyer@litwareinc.com を持っているユーザーが電話番号 + 1206555-1219 への通話を発信できるかどうかをテストします。

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

電話番号は、ダイヤルする場合と同じように書式設定する必要があります。 たとえば、通常、長距離通話を発信する前に1がダイヤルされない場合は、次の形式を使用する必要があります。

`-DialedNumber "2065551219"`

ただし、この場合、番号2065551219を正しく変換できる正規化ルールを持っていない場合、テストは失敗します。これは、Lync Server で使用されている電子電話形式の E.i になります。 詳細については、ヘルプトピック「CsVoiceNormalizationRule コマンドレット」を参照してください。

各ユーザーアカウントに対して同じテストを実行する場合は、次のようなコマンドを使用できます。

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

詳細については、「Get-csvoiceuser コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

テストが正常に完了した場合 (つまり、ユーザーが指定した番号に電話をかけることができる場合)、出力には、翻訳された電話番号や、一致する正規化ルールとボイスルートなどの情報が表示されます。

TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage

\----------------    ------------    ------------------    -------------

\+12065551219 Descripti   LocalRoute ローカル

Windows PowerShell 画面の制限により、少なくともいくつかの情報 (一致する正規化ルールの詳細な説明) が画面に表示されないことがあります。 テストの成功または失敗のみを目的としている場合は、これは問題ではない可能性があります。 返されるデータの完全な詳細情報を表示する場合は、テストを実行するときに、出力を形式指定コマンドレットにパイプします。

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

これにより、次のような出力がわかりやすい形式で表示されます。

TranslatedNumber: + 12065551219

MatchingRule: Description =;Pattern = ^ (\\d{11}) $;翻訳 = + $ 1;

Name = Prefix All; IsInternalExtension = False

FirsMatchingRoute: LocalRoute

MatchingUsage: Local

テストに失敗した場合、Get-csvoiceuser は、空のプロパティ値のセットを返します。

TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage

\---------------- ------------ ------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

Get-csvoiceuser コマンドレットが失敗する可能性がある理由はいくつかあります。指定した電話番号を変換できる正規化ルールがない可能性があります。 ボイスルーティングで問題が発生する可能性があります。 問題のユーザーに割り当てられているダイヤルプランの構成で問題が発生している可能性があります。 このため、Get-csvoiceuser コマンドレットを実行する場合は、Verbose パラメーターを含めることができます。

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

Verbose コマンドレットが含まれている場合、Get-csvoiceuser は、チェックを実行するときに実行されるすべての手順の詳細なアカウントを発行します。 たとえば、次のような手順が表示される場合があります。 

VERBOSE: id が "sip:kenmyer@litwareinc.com" のユーザーを検索しています

詳細: ダイヤルプランを読み込み中: "RedmondDialPlan"

この追加情報は、エラーの原因を特定するために実行できる手順についてのヒントを提供します。 たとえば、ここに表示される verbose の出力では、テスト対象のユーザーにダイヤルプランの RedmondDialPlan が割り当てられたことがわかります。 テストが失敗した場合は、RedmondDialPlan が指定した電話番号を翻訳できるかどうかを確認するための論理的な次の手順があります。

</div>

<div>

## <a name="see-also"></a>関連項目


[テスト-Get-csvoiceuser](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

