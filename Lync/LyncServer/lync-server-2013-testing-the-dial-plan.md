---
title: 'Lync Server 2013: ダイヤルプランのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14c8e53b0b18ae7813cf0f2d63aaa54ffbd4998b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a>Lync Server 2013 でのダイヤルプランのテスト

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合は、Get-csdialplan コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Get-csdialplan コマンドレットを使用すると、特定の電話番号にダイヤルプランを適用した結果を確認できます。 ダイヤルプランでは、エンタープライズ Voip ユーザーが電話をかけることができるようにするために必要な情報 (正規化ルールの適用方法など) が提供されます。 ダイヤル番号とダイヤルプランを指定すると、このコマンドレットにより、ダイヤルプラン内のどの正規化ルールが適用されるか、および翻訳された番号がどのようになるかが確認されます。

このコマンドレットを使用すると、数値変換に関する問題のトラブルシューティングを行ったり、特定の番号に対するルールの適用方法を確認したりすることができます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Get-csdialplan コマンドレットでは、2つの操作を行う必要があります。 最初に、テストしているダイヤルプランのインスタンスを取得する必要があります。これは、Get-csdialplan コマンドレットを使用して行うことができます。 次に、正規化する必要がある電話番号を指定する必要があります。 電話番号に使用される形式は、ユーザーがダイヤル/入力した番号と一致している必要があります。 たとえば、次のコマンドは、ダイヤルプラン RedmondDialPlan のインスタンスを取得し、電話番号12065551219を正規化できるかどうかを確認します。

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

国コード (この例では 1) と市外局番 (206) を自動的に追加する正規化ルールがある場合は、次のように電話番号5551219を確認する必要があります。

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

詳細については、 [get-csdialplan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan)コマンドレットのヘルプドキュメントを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

Get-csdialplan は、テストが成功したか失敗したかを間接的に示すだけなので、Lync Server test コマンドレットの多くとは異なります。 Get-csdialplan を使用している場合、次のような出力は返されず、わかりやすいラベルが表示されます。

TargetFqdn: atl-cs-001.litwareinc.com

結果: 成功

待機時間:00:00: 06.8630376

エラー

分析

代わりに、Get-csdialplan が正常に終了すると、指定した電話番号を正常に翻訳して使用できた正規化ルールに関する情報が表示されます。

TranslatedNumber: + 12065551219

MatchingRule: Description =;Pattern = ^ (\\d (11)) $;直線移動 = + $ 1;

Name = Prefix All;IsInternalExtension = False

Get-csdialplan が失敗した場合 (つまり、ダイヤルプランに、指定された電話番号を変換できる正規化ルールがない場合)、次のように "empty" 出力が表示されます。

TranslatedNumber :

MatchingRule :

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

Get-csdialplan が失敗する可能性のある一般的な原因を次に示します。

  - 電話番号を指定するときに、誤った形式を使用した可能性があります。 ダイヤルプランには、Lync Server がダイヤルまたはユーザーによって入力された電話番号を変換できるようにする正規化ルールが含まれています。 そのため、ダイヤルプランには、ユーザーがダイヤルすると思われる番号と一致する正規化ルールを設定する必要があります。 たとえば、ユーザーが国コード、市外局番、電話番号自体をダイヤルする場合、次のような電話番号を処理するための正規化ルールがダイヤルプランに必要になります。
    
    12065551219
    
    ただし、誤った電話番号を入力した場合 (たとえば、最後の数字を残した場合)、Get-csdialplan は失敗します。 これは、ダイヤルプランが正しくないため、解釈できない電話番号を入力したためです。

</div>

</div>

<span> </span>

</div>

</div>

</div>

