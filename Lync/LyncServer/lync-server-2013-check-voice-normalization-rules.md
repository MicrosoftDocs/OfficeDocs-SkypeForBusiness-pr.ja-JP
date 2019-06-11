---
title: 'Lync Server 2013: 音声正規化ルールを確認する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check voice normalization rules
ms:assetid: bf71a218-71cd-4b64-b8e8-b3a98b6e87a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725212(v=OCS.15)
ms:contentKeyID: 63969649
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 487415fccc1e779daa476a4e76aa99a891f6b7fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-voice-normalization-rules-in-lync-server-2013"></a>Lync Server 2013 で音声正規化ルールを確認する

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
<p>Windows PowerShell のリモートインスタンスを使って実行する場合は、CsVoiceNormalizationRule コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

音声正規化規則は、ユーザーがダイヤルした電話番号 (2065551219 など) を、Lync Server (+ 12065551219) で使用される E.i 形式に変換するために使用されます。 たとえば、国コードや市外局番を含めずに電話番号をダイヤルする習慣 (5551219 など) の場合、その番号を E.i 形式に変換するには、音声の正規化ルールを使用する必要があります (例: + 12065551219)。 このようなルールがないと、ユーザーは555-1219 に通話を発信できません。

CsVoiceNormalizationRule コマンドレットは、指定された音声正規化ルールが、指定された電話番号を正しく変換できることを確認します。 たとえば、このコマンドは、グローバル正規化ルール NoAreaCode が、ダイヤル文字列5551219を正規化して変換できるかどうかを確認します。

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a>テストの実行

CsVoiceNormalizationRule コマンドレットを実行するには、最初に Get-CsVoiceNormalizationRule コマンドレットを使って、テスト対象のルールのインスタンスを取得し、そのインスタンスをテスト-CsVoiceNormalizationRule にパイプします。 このような構文は、次のように動作しません。

CsVoiceNormalizationRule-Ednumber "12065551219" – NormalizationRule "global/Prefix All"

代わりに、CsVoiceNormalizationRule と CsVoiceNormalizationRule コマンドレットの両方を組み合わせた次のような構文を使用します。

Get-CsVoiceNormalizationRule-Identity "global/Prefix All" |CsVoiceNormalizationRule-の番号 "12065551219" のテスト

<div>


> [!NOTE]  
> . または、この方法を使用して、ルールのインスタンスを取得し、指定した電話番号に対してそのルールをテストすることもできます。



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

番号をダイヤルする場合と同じように、指定された番号パラメーターの値を入力します。 たとえば、指定された音声正規化ルールが国コード (値12065551219の最初の 1) を自動的に追加する場合は、国コードをオフにする必要があります。

`-DialedNumber "2065551219"`

ルールが正しく構成されている場合は、電話番号を Lync Server で使用される E.i 形式に変換するときに、国コードが自動的に追加されます。

詳細については、「CsVoiceNormalizationRule コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

指定した音声正規化ルールで指定した番号が翻訳された場合は、翻訳後の番号が画面に表示されます。

TranslatedNumber

\----------------

\+12065551219

テストが失敗すると、空白の翻訳された数値が返されます。

TranslatedNumber

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

CsVoiceNormalizationRule によって、指定された電話番号を、Lync Server で使用されている E.i 形式に変換できなかったことを示す、翻訳された数値が返される場合。 これを確認するには、まず電話番号を正しく入力したことを確認します。 たとえば、次のような数値の変換については、音声の正規化ルールで問題が発生していることが考えられます。

`-DialedNumber "1"`

番号が正しく入力されていることを前提として、次の手順は、指定された正規化ルールがその電話番号を処理するように設計されていることを確認する必要があります。 たとえば、1つの正規化ルールは12065551219の形式を処理するように設計されていますが、2つ目のルールは数値2065551219を処理するように設計されている可能性があります。 (これは同じ電話番号で、最初の国コード1を差し引いています)。音声正規化ルールに関する詳細情報を取得するには、次のようなコマンドを実行します。

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

すべての音声正規化ルールに関する詳細情報を取得するには、代わりに次のコマンドを実行します。

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a>関連項目


[テスト-CsVoiceNormalizationRule](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

