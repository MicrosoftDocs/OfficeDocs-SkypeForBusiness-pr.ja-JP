---
title: 'Lync Server 2013: 音声ポリシーに対して電話番号をテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a234419dc6f06ae9bdc8d7c198873bdc3c706701
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "41985092"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a>Lync Server 2013 で音声ポリシーに対して電話番号をテストする

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合は、Set-csvoicepolicy コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

エンタープライズ Voip ユーザーが公衆交換電話網 (PSTN) のヒンジを経由して発信する機能 (大部分) は、次の3つの要素で構成されます。

  - ユーザーに割り当てられている音声ポリシー。

  - Lync Server から PSTN ネットワークへの通話をルーティングするために使用される音声ルート。

  - PSTN 使用法。音声ポリシーを音声ルートに接続する Lync Server プロパティ。

PSTN 使用法は特に重要です。これは、音声ポリシーを音声ルートに接続するプロパティです。 (音声ポリシーと音声ルートは、少なくとも1つの PSTN 使用法が共通である場合に接続されていると言われています)。音声ポリシーは、PSTN 使用法を指定せずに構成できます。 その場合、そのポリシーに割り当てられたユーザーは、PSTN ネットワーク経由での発信呼び出しを行うことができません。 同様に、少なくとも1つの PSTN 使用法が指定されていない音声ルートでは、通話を PSTN ネットワークにルーティングできません。

Set-csvoicepolicy コマンドレットは、指定された音声ポリシーに PSTN 使用法があり、少なくとも1つの音声ルートで使用が共有されていることを確認します。 Set-csvoicepolicy によって実行された検証が成功した場合、コマンドレットは、検出された最初の有効なボイスルートの名前と、そのポリシーをルートに接続する PSTN 使用法の名前に報告します。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Set-csvoicepolicy コマンドレットを実行するには、最初に Set-csvoicepolicy コマンドレットを使用して、テストする音声ポリシーのインスタンスを取得する必要があります。そのインスタンスを Set-csvoicepolicy にパイプ処理する必要があります。 例:

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

このコマンドは、Set-csvoicepolicy を使用して音声ポリシーインスタンスを取得しないため、失敗します。

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

指定した電話番号に対してすべての音声ポリシーを確認するには、次のようなコマンドを使用します。

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

TargetNumber は、e.164 形式で指定する必要があることに注意してください。 Set-csvoicepolicy は、電話番号を e.164 形式に正規化または翻訳しようとしません。

詳細については、Set-csvoicepolicy コマンドレットのヘルプドキュメントを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

音声ポリシーが一致する音声ルートと一致する PSTN 使用法の両方を見つけることができる場合、ルートと使用状況の両方が画面に表示されます。

FirstMatchingRoute MatchingUsage

\------------------ -------------

RedmondVoiceRoute RedmondPstnUsage

適切な音声ルートまたは適切な PSTN 使用法が見つからない場合は、空白のプロパティ値が画面に表示されます。

FirstMatchingRoute MatchingUsage

\------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

Set-csvoicepolicy が一致するものを返さない場合は、音声ポリシーがボイスルートとの PSTN 使用法を共有していないことを意味します。 これを確認するには、次のようなコマンドレットを使用して、音声ポリシーに割り当てられている PSTN 使用法を確認します。

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

次に、次のコマンドを実行して、各音声ルートに割り当てられている PSTN 使用法を確認します。

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

一致するものがある場合 (つまり、音声ポリシーで少なくとも1つの PSTN 使用法を共有する1つまたは複数の音声ルートが表示されている場合)、Get-csvoiceroute コマンドレットを実行して、指定した電話番号をボイスルートがダイヤルできることを確認する必要があります。

</div>

<div>

## <a name="see-also"></a>関連項目


[Set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

