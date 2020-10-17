---
title: 'Lync Server 2013: 音声構成のテスト'
description: 'Lync Server 2013: 音声構成をテストします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cc05286e5f534b4d469ef561d9ce009367e15be
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557073"
---
# <a name="test-voice-configuration-in-lync-server-2013"></a>Lync Server 2013 での音声構成のテスト

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsVoiceTestConfiguration コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Lync Server には、いくつかの Windows PowerShell コマンドレット (Test-CsVoiceRoute、Get-cstrunkconfiguration など) が含まれており、エンタープライズ Voip インフラストラクチャの個々の部分 (音声ルート、音声ポリシー、SIP トランク-) が期待どおりに動作していることを確認できます。

個人のすべての要素が機能することはエンタープライズ Voip にとって重要ですが、有効な音声ルート、有効な音声ポリシー、および有効な SIP トランクを持つことができますが、ユーザーは通話を発信または受信できません。 そのため、Lync Server では音声テスト構成を作成することもできます。 音声テスト構成は、一般的なエンタープライズ Voip シナリオを表します。たとえば、音声ルート、音声ポリシー、ダイヤルプランなどを指定し、それらの各アイテムが連携して電話サービスを提供できるようにすることができます。 さらに、特定のシナリオで期待値を検証することもできます。 たとえば、ダイヤルプラン A と音声ポリシー B の組み合わせによって、呼び出しがボイスルート C を経由してルーティングされると想定しているとします。音声ルート C を ExpectedRoute として入力できます。 テストを実行すると、音声ルート C が使用されていない場合、テストは失敗したとしてマークされます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Windows PowerShell を使用して音声構成コレクションをテストする前に、まず Get-CsVoiceTestConfiguration コマンドレットを使用してこれらの構成設定のインスタンスを取得する必要があります。 その後、そのインスタンスを Test-csvoicetestconfiguration にパイプ処理する必要があります。 以下に例を示します。

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

すべての音声テスト構成設定を同時に検証するには、代わりに次のコマンドを使用します。

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

詳細については、Test-CsVoiceTestConfiguration コマンドレットのヘルプドキュメントを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

Test-CsVoiceTestConfiguration コマンドレットは、テストが失敗したか成功したかを報告し、成功した各テスト (タスクを完了するために使用される変換ルール、ボイスルート、および PSTN 使用法など) に関する追加情報を提供します。

結果: 成功

TranslatedNumber: + 15551234

MatchingRule: Description =;Pattern = ^ ( \\ d {4} ) $;直線移動 = + 1 \\ d;Name = Test; IsInternalExtension = False

FirstMatchingRoute: サイト: Redmond

MatchingUsage: ローカル

テストが失敗した場合、結果は失敗として報告されます。

結果: Fail

TranslatedNumber:   

FirstMatchingRoute:

MatchingUsage:      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

音声テスト構成テストでは、音声ポリシー、ダイヤルプラン、音声ルートなど、いくつかの異なるアイテムがテストされるため、テストに失敗する可能性があるさまざまな要因があります。 テストが失敗した場合は、最初の手順として、Get-CsVoiceTestConfiguration コマンドレットを使用して構成設定を確認する必要があります。

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

設定が正しく構成されているように見える場合は、Verbose パラメーターを含めてテストを再実行します。

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

Verbose パラメーターは、次の例に示すように、Test-CsVoiceTestConfiguration によって実行される各アクションのステップバイステップのアカウントを提供します。

VERBOSE: ダイヤルプランの読み込み: "グローバル"

VERBOSE: 音声ポリシーの読み込み: "RedmondDialPlan"

このステップごとのアカウントでは、テストが実際に失敗した場所について有用な手掛かりが提供されることがあります。 それ以外の場合は、他の Windows PowerShell コマンドレット (Set-csvoicepolicy など) を使用し、入念に開始して、音声テスト構成設定に含まれている個々のコンポーネントを確認できます。

それに加えて、テストで呼び出しをルーティングでき、まだエラーとしてマークされている場合もあることに注意してください。これは、ExpectedRoute、ExpectedTranslatedNumber、および ExpectedUsage の値を入力し、これらの期待値が満たされていない場合に発生する可能性があります。 たとえば、予想される音声ルートとして音声ルート C を入力したものの、テストではボイスルート D を使用して通話を実際に完了したとします。その場合、予想される音声ルートが使用されていなかったため、テストは失敗としてマークされます。 テストが失敗した場合は、ExpectedRoute、ExpectedTranslatedNumber、および ExpectedUsage の値を削除してからテストを再実行することができます。 これは、呼び出しが完了できなかったこと、または1つの問題が発生して実際に別のものを受信したことが原因でエラーが発生したかどうかを判断するのに役立ちます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Test-csvoicetestconfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

