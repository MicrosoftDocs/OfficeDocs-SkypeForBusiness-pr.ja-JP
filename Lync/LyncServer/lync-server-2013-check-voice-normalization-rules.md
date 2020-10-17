---
title: 'Lync Server 2013: 音声正規化ルールの確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check voice normalization rules
ms:assetid: bf71a218-71cd-4b64-b8e8-b3a98b6e87a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725212(v=OCS.15)
ms:contentKeyID: 63969649
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 547f117a9706aa0ab5bf1202c31d0bc9f8ce34fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526214"
---
# <a name="check-voice-normalization-rules-in-lync-server-2013"></a>Lync Server 2013 で音声正規化ルールをチェックする

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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsVoiceNormalizationRule コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

音声正規化ルールは、ユーザーがダイヤルした電話番号 (たとえば、2065551219) を Lync Server で使用される e.164 形式 (+ 12065551219) に変換するために使用されます。 たとえば、ユーザーが国コードや市外局番を含めずに電話番号をダイヤルする習慣になっている場合 (5551219 など)、その番号を e.164 形式に変換するための音声正規化ルールが必要です (例: + 12065551219)。 このようなルールがない場合、ユーザーは555-1219 を呼び出すことができません。

Test-CsVoiceNormalizationRule コマンドレットは、指定された音声正規化ルールが指定された電話番号を正常に変換できることを確認します。 たとえば、次のコマンドは、グローバル正規化ルール NoAreaCode が、ダイヤル文字列5551219を正規化して変換できるかどうかを確認します。

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Test-CsVoiceNormalizationRule コマンドレットを実行するには、まず Get-CsVoiceNormalizationRule コマンドレットを使用して、テスト対象のルールのインスタンスを取得し、そのインスタンスを Get-csvoicenormalizationrule にパイプ処理する必要があります。 このような構文は使用できません。

Test-CsVoiceNormalizationRule-tcp/ip Ednumber "12065551219" – NormalizationRule "global/Prefix All"

代わりに、次のような構文を使用して、Get-CsVoiceNormalizationRule と Test-CsVoiceNormalizationRule コマンドレットを組み合わせます。

Get-CsVoiceNormalizationRule-Identity "global/Prefix All" |Test-CsVoiceNormalizationRule-電話番号 "12065551219"

<div>


> [!NOTE]  
> . または、この方法を使用してルールのインスタンスを取得し、指定した電話番号に対してそのルールをテストすることもできます。



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

番号をダイヤルすることが予想されるとおりに、ダイヤル Ednumber パラメーターの値を正確に入力します。 たとえば、指定された音声正規化ルールが国コードを自動的に追加する (値12065551219の最初の 1) 場合は、国コードを省略する必要があります。

`-DialedNumber "2065551219"`

ルールが正しく構成されている場合は、Lync Server で使用されている e.164 形式に番号を変換するときに、国コードが自動的に追加されます。

詳細については、Test-CsVoiceNormalizationRule コマンドレットのヘルプドキュメントを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

指定した音声正規化ルールが指定した番号を翻訳できる場合は、変換後の番号が画面に表示されます。

TranslatedNumber

\----------------

\+12065551219

テストが失敗した場合は、空の変換された数値が返されます。

TranslatedNumber

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

Test-CsVoiceNormalizationRule が変換された番号を返す場合は、指定した音声正規化ルールが、指定された電話番号を Lync Server で使用されている e.164 形式に変換できなかったことを意味します。 これを確認するには、まず電話番号を正しく入力したことを確認してください。 たとえば、次のような数値を変換すると、音声正規化ルールで問題が発生することが予想されます。

`-DialedNumber "1"`

番号が正しく入力されていることを前提として、次の手順では、指定した正規化ルールがその電話番号を処理するように設計されていることを確認する必要があります。 たとえば、1つの正規化ルールは12065551219の形式を処理するように設計されていますが、2番目のルールは2065551219の番号を処理するように設計されている場合があります。 (これは同じ電話番号で、先頭に国コード1を引いたものです。)音声正規化ルールに関する詳細情報を取得するには、次のようなコマンドを実行します。

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

すべての音声正規化ルールに関する詳細情報を取得するには、代わりに次のコマンドを実行します。

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a>関連項目


[Get-csvoicenormalizationrule](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

