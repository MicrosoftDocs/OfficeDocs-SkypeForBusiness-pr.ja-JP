---
title: 'Lync Server 2013: ボイス構成のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbe9be7e0f7962bbab546822e7ce6cd47e063540
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848502"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a>Lync Server 2013 での音声構成のテスト

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
<p>Windows PowerShell のリモートインスタンスを使って実行する場合は、CsVoiceTestConfiguration コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Lync Server には、複数の Windows PowerShell コマンドレット (CsVoiceRoute や CsVoicePolicy のテストなど) が含まれており、エンタープライズ Voip インフラストラクチャの個々の要素 (ボイスルーティング、音声) を確認できます。ポリシー、SIP trunks –期待どおりに機能しています。

エンタープライズ Voip では、個々の要素がすべて機能することが重要です。ただし、有効なボイスルート、有効な音声ポリシー、有効な SIP トランクを持っていても、ユーザーは電話をかけたり受けたりすることはできません。 そのため、Lync Server にはボイステスト構成を作成する機能もあります。 音声テスト構成は、一般的なエンタープライズ Voip シナリオを示します。このようなことは、ボイスルート、音声ポリシー、ダイヤルプランなどを指定できます。また、それらの項目が複数のユーザーが協力して電話サービスを提供できることを確認できます。 さらに、特定のシナリオで期待値を検証することもできます。 たとえば、ダイヤルプラン A とボイスポリシー B の組み合わせによって、ボイスルーティング C 経由で通話がルーティングされていると想定したとします。ボイスルーティング C を ExpectedRoute として入力できます。 テストを実行すると、voice route C が使用されていない場合、テストは失敗したとマークされます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Windows PowerShell を使用してボイス構成コレクションをテストする前に、まず CsVoiceTestConfiguration コマンドレットを使用してこれらの構成設定のインスタンスを取得する必要があります。 その後、そのインスタンスを CsVoiceTestConfiguration にパイプする必要があります。 次に例を示します。

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

すべての音声テストの構成設定を同時に検証するには、代わりに次のコマンドを使用します。

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

詳細については、「CsVoiceTestConfiguration コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

CsVoiceTestConfiguration コマンドレットは、テストが失敗したか成功したかを報告し、タスクを完了するために使用された翻訳ルール、ボイスルーティング、PSTN の使用状況などの各テストの成功に関する追加情報を提供します。

結果: 成功

TranslatedNumber: + 15551234

MatchingRule: Description =;Pattern = ^ (\\d{4}) $;翻訳 = + 1\\d;Name = Test; IsInternalExtension = False

FirstMatchingRoute: サイト: レドモンド

MatchingUsage: Local

テストが失敗した場合、結果は Fail として報告されます。

結果: Fail

TranslatedNumber:   

FirstMatchingRoute:

MatchingUsage:      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

ボイステスト構成テストでは、ボイスポリシー、ダイヤルプラン、音声ルートなど、さまざまな項目をテストするため、テストが失敗する原因となる可能性のある要素がいくつかあります。 テストに失敗した場合は、最初の手順として、CsVoiceTestConfiguration コマンドレットを使用して構成設定を確認する必要があります。

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

設定が正しく構成されているように見える場合は、Verbose パラメーターを含めてテストを再実行します。

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

Verbose パラメーターは、次の例に示すように、CsVoiceTestConfiguration によって実行される各アクションのステップバイステップのアカウントを提供します。

詳細: ダイヤルプランの読み込み: "グローバル"

詳細: 音声ポリシーを読み込み中: "RedmondDialPlan"

このステップバイステップのアカウントでは、テストが実際に失敗した場所について、役に立つ手掛かりを提供する場合があります。 それ以外の場合は、Windows PowerShell コマンドレット (CsVoicePolicy など) を使用して、ボイステスト構成の設定に含まれている個々のコンポーネントの確認を系統的に開始できます。

これに加えて、テストによって通話のルーティングが可能で、まだエラーとしてマークされている場合もあります。これは、ExpectedRoute、ExpectedTranslatedNumber、ExpectedUsage の値を入力した場合に発生する可能性があります。これらの期待値は満たされません。 たとえば、予想されるボイスルートとして「ボイスルーティング C」と入力しても、テストではボイスルーティング D を使って通話を完了しているとします。その場合、予期されるボイスルートが使用されなかったため、テストは失敗としてマークされます。 テストが失敗した場合は、ExpectedRoute、ExpectedTranslatedNumber、ExpectedUsage の値を削除して、テストを再実行することができます。 これは、通話が完了できなかったこと、または1つの問題が発生して、実際に他のユーザーが受信したためにエラーが発生したかどうかを判断するのに役立ちます。

</div>

<div>

## <a name="see-also"></a>関連項目


[テスト-CsVoiceTestConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

