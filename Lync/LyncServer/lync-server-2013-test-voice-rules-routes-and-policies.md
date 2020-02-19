---
title: 'Lync Server 2013: 音声ルール、ルート、およびポリシーのテスト'
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
ms.openlocfilehash: 8da7334e00c0361a5c8ad840dbf57ee7d5024763
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a>Lync Server 2013 での音声ルール、ルート、ポリシーのテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-05-20_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>検証スケジュール</p></td>
<td><p>毎月</p></td>
</tr>
<tr class="even">
<td><p>テストツール</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要なアクセス許可</p></td>
<td><p>Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</p>
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合は、CsVoiceUser コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

ユーザーが電話をかけた場合、通話が宛先に到達するのにかかるルートは、そのユーザーに割り当てられているポリシーとダイヤルプランの両方によって決まります。 ユーザーの SIP アドレスと電話番号を指定すると、CsVoiceUser コマンドレットは、その番号への呼び出しをユーザーが完了できるかどうかを確認します。 テストが成功した場合、CsVoiceUser は次の値を返します。

  - 番号は、(ユーザーのダイヤルプランに基づいて) e.164 形式に変換されます。

  - その翻訳を指定した正規化ルール

  - 使用された音声ルート (ルートの優先度に基づいて)。

  - ユーザーの音声ポリシーを音声ルートにリンクした電話の使用法。

CsVoiceUser を使用すると、特定の電話番号が予想どおりにルーティングおよび翻訳されるかどうかを判断し、個々のユーザーが経験する通話関連の問題のトラブルシューティングに役立てることができます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

CsVoiceUser コマンドレットを実行するときは、ダイヤルされる番号 (ダイヤル番号) とテストするユーザーアカウントの Id の2つの情報を提供する必要があります。 たとえば、次のコマンドは、SIP アドレス sip:kenmyer@litwareinc.com を持つユーザーが電話番号 + 1206555-1219 を呼び出すことができるかどうかをテストします。

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

電話番号は、ダイヤルするのと同じ方法で書式設定する必要があります。 たとえば、ユーザーが長距離電話をかける前に1をダイヤルしない場合は、次の形式を使用する必要があります。

`-DialedNumber "2065551219"`

当然のことですが、この場合、数字2065551219を Lync Server で使用されている e.164 電話形式に正しく変換できる正規化ルールがないと、テストは失敗します。 詳細については、ヘルプトピック「Get-csvoicenormalizationrule コマンドレット」を参照してください。

各ユーザーアカウントに対してこの同じテストを実行する場合は、次のようなコマンドを使用できます。

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

詳細については、CsVoiceUser コマンドレットのヘルプドキュメントを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

テストが正常に完了した場合 (つまり、ユーザーが指定された番号に電話をかけることができる場合)、出力には、翻訳された電話番号と一致する正規化ルールおよび音声ルートなどの情報が表示されます。

TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage

\----------------    ------------    ------------------    -------------

\+12065551219 Descripti   LocalRoute ローカル

Windows PowerShell 画面には制限があるため、返される情報 (特に一致する正規化ルールの詳細な説明) が画面に表示されない場合があります。 テストの成功または失敗のみを目的としている場合は、これは問題ではない可能性があります。 返されるデータの完全な詳細を表示する場合は、テストの実行時に出力を Format List コマンドレットにパイプ処理します。

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

これにより、出力がよりわかりやすい形式で表示されます。

TranslatedNumber: + 12065551219

MatchingRule: Description =;Pattern = ^ (\\d{11}) $;直線移動 = + $ 1;

Name = Prefix All、IsInternalExtension = False

FirsMatchingRoute: LocalRoute

MatchingUsage: ローカル

テストが失敗した場合、CsVoiceUser は空のプロパティ値のセットを返します。

TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage

\---------------- ------------ ------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

CsVoiceUser コマンドレットが失敗する原因としては、次のようないくつかの理由が考えられます。指定された電話番号を変換できる正規化ルールがない場合があります。 音声ルートに問題がある可能性があります。 対象のユーザーに割り当てられているダイヤルプランの構成に問題がある可能性があります。 そのため、CsVoiceUser コマンドレットを実行しているときに、Verbose パラメーターを含めることをお勧めします。

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

Verbose コマンドレットが含まれている場合、CsVoiceUser は、チェックを実行するときに実行されるすべての手順の詳細なアカウントを発行します。 たとえば、次のような手順が表示されることがあります。 

VERBOSE: id が "sip:kenmyer@litwareinc.com" のユーザーを検索しています

VERBOSE: ダイヤルプランの読み込み: "RedmondDialPlan"

この追加情報は、障害の原因を特定するために実行できる手順についてのヒントを提供することができます。 たとえば、次に示す詳細出力は、テスト対象のユーザーにダイヤルプラン RedmondDialPlan が割り当てられたことを示しています。 テストが失敗した場合は、RedmondDialPlan が指定された電話番号を翻訳できるかどうかを確認する論理的な次の手順があります。

</div>

<div>

## <a name="see-also"></a>関連項目


[CsVoiceUser](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

