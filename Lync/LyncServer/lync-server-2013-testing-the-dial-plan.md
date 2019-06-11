---
title: 'Lync Server 2013: ダイヤルプランのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2815248084e7591c11157cde3fb4851722315073
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a>Lync Server 2013 でのダイヤルプランのテスト

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
<p>Windows PowerShell のリモートインスタンスを使って実行する場合は、CsDialPlan コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

CsDialPlan コマンドレットを使用すると、特定の電話番号にダイヤルプランを適用した結果を確認できます。 [ダイヤルプラン] には、正規化ルールの適用方法など、エンタープライズボイスユーザーに電話をかけるために必要な情報が記載されています。 ダイヤル番号とダイヤルプランを指定すると、このコマンドレットによって、ダイヤルプラン内の正規化ルールが適用されるかどうか、および翻訳された番号がどのようになるかが確認されます。

このコマンドレットを使用すると、数値の翻訳に関する問題のトラブルシューティングや、特定の番号に対するルールの適用方法の確認を行うことができます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

CsDialPlan コマンドレットでは、次の2つの操作を行う必要があります。 まず、テストしているダイヤルプランのインスタンスを取得する必要があります。これは、CsDialPlan コマンドレットを使って行うことができます。 次に、正規化する必要がある電話番号を指定する必要があります。 電話番号に使用される形式は、ユーザーがダイヤル/入力した電話番号と一致する必要があります。 たとえば、次のコマンドは、ダイヤルプランのインスタンスを取得し、RedmondDialPlan を使用して電話番号12065551219を正規化できるかどうかを確認します。

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

国コード (この例では 1) と市外局番 (206) が自動的に追加される正規化ルールを使用している場合は、次のように電話番号5551219を確認することをお勧めします。

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

詳細については、「 [CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan)コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

CsDialPlan は、テストが成功したか失敗したかを間接的に示すだけであるため、Lync Server のテストコマンドレットの多くとは異なります。 CsDialPlan を使用すると、次のような結果が表示されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待ち時間:00:00: 06.8630376

誤差

診断

テスト-CsDialPlan が成功した場合は、指定した電話番号を正常に翻訳して使用できる正規化ルールに関する情報を受け取ることになります。

TranslatedNumber: + 12065551219

MatchingRule: Description =;Pattern = ^ (\\d (11)) $;翻訳 = + $ 1;

Name = Prefix AllIsInternalExtension = False

テスト-CsDialPlan が失敗した場合 (つまり、ダイヤルプランに、指定した電話番号を変換できる正規化ルールがない場合)、次のように "empty" の出力が表示されます。

TranslatedNumber :

MatchingRule :

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

次に、テスト-CsDialPlan が失敗する可能性がある一般的な理由を示します。

  - 電話番号の指定時に使用した形式が間違っている可能性があります。 ダイヤルプランには、Lync Server でダイヤルまたは入力された電話番号をユーザーによって翻訳できる正規化ルールが含まれています。 そのため、ダイヤルプランには、ユーザーがダイヤルする可能性のある数値と一致する正規化ルールを設定する必要があります。 たとえば、ユーザーが国コード、市外局番、電話番号をダイヤルする場合、次のような電話番号を処理するための正規化ルールがダイヤルプランに含まれている必要があります。
    
    12065551219
    
    ただし、誤った電話番号を入力した場合 (最終的な数字を除いた場合など)、CsDialPlan は失敗します。 これは、ダイヤルプランが故障しているのに、解釈できない電話番号が入力されたためです。

</div>

</div>

<span> </span>

</div>

</div>

</div>

