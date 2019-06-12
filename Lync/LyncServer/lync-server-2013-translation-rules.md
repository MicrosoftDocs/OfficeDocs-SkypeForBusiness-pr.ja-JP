---
title: 'Lync Server 2013: 翻訳ルール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22b6fbacf068f6a1a388a968989259afec81d17a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a>Lync Server 2013 の翻訳ルール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-05_

Lync Server 2013 エンタープライズボイスでは、逆引き数値参照 (RNL) を実行するために、すべてのダイヤル文字列が E.i 形式に正規化されている必要があります。 Microsoft Lync Server 2010 では、翻訳ルールは、呼び出した番号に対してのみサポートされます。 Microsoft Lync Server 2013 の新機能には、翻訳ルールも含まれています。 *トランク ピア* (つまり、関連付けられたゲートウェイ、構内交換機 (PBX)、または SIP トランク) では、番号を地域のダイヤル形式にすることが必要な場合もあります。 E.164 形式から地域のダイヤル形式に番号を変換するには、トランク ピアにルーティングする前に 1 つ以上の変換ルールを定義して要求 URI を操作することができます。 たとえば、ダイヤル文字列の先頭から +44 を削除して 0144 に置き換える変換ルールを作成できます。

サーバーで送信ルートの翻訳を実行すると、電話番号をローカルのダイヤル形式に変換するために、個々のトランクピアの構成要件を減らすことができます。 ゲートウェイとゲートウェイの数を計画しているときに、特定の仲介サーバークラスターと関連付けるには、同様のローカルダイヤル要件でトランクピアをグループ化すると便利な場合があります。 これにより、必要な翻訳ルールの数と書き込みにかかる時間を減らすことができます。

<div>


> [!IMPORTANT]  
> 1つまたは複数の翻訳ルールをエンタープライズボイストランク構成に関連付けることは、トランクピアでの翻訳ルールの設定の代わりとして使用する必要があります。 トランクピアで翻訳ルールを構成している場合は、2つのルールが競合する可能性があるため、翻訳ルールをエンタープライズボイストランク構成に関連付けないでください。



</div>

<div>

## <a name="example-translation-rules"></a>変換ルールの例

以下の変換ルールの例では、トランク ピアについて E.164 形式からローカル形式に番号を変換するルールをサーバー上に作成する方法を示しています。

翻訳ルールの実装方法の詳細については、展開ドキュメントの「 [Lync Server 2013 で翻訳ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。


<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th>説明</th>
<th>先頭の数字</th>
<th>長さ</th>
<th>削除する数字</th>
<th>追加する数字</th>
<th>一致パターン</th>
<th>変換</th>
<th>例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>米国内の従来の長距離電話ダイヤル</p>
<p>("+" を削除)</p></td>
<td><p>+1</p></td>
<td><p>ちょうど 12</p></td>
<td><p>1</p></td>
<td><p>0</p></td>
<td><p>^\+(1 \ d{10}) $</p></td>
<td><p>$1</p></td>
<td><p>+14255551010 を 14255551010 に変換</p></td>
</tr>
<tr class="even">
<td><p>米国長距離国際電話ダイヤル</p>
<p>("+" を削除し、011 を追加)</p></td>
<td><p>+</p></td>
<td><p>11 以上</p></td>
<td><p>1</p></td>
<td><p>011</p></td>
<td><p>^\+(\d{9}\d +) $</p></td>
<td><p>011$1</p></td>
<td><p>+441235551010 を 011441235551010 に変換</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

