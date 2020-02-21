---
title: 'Lync Server 2013: 変換ルール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1576b9c0c7286150c62f1491960bf9beef5d700
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a>Lync Server 2013 の変換ルール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-05_

Lync Server 2013 エンタープライズ Voip では、逆引き番号検索 (RNL) を実行するために、すべてのダイヤル文字列が e.164 形式に正規化されている必要があります。 Microsoft Lync Server 2010 では、変換ルールは、呼び出し先の番号に対してのみサポートされています。 Microsoft Lync Server 2013 の新製品では、電話番号の変換ルールもサポートされています。 *トランクピア*(つまり、関連付けられたゲートウェイ、構内交換 LAN (PBX)、または SIP トランク) では、番号が地域のダイヤル形式になっている必要があります。 番号を e.164 形式からローカルのダイヤル形式に変換するために、1つ以上の変換ルールを定義してから、トランクピアにルーティングする前に要求 URI を操作できます。 たとえば、ダイヤル文字列の先頭から +44 を削除して 0144 に置き換える変換ルールを作成できます。

サーバーで送信ルート変換を実行すると、電話番号をローカルのダイヤル形式に変換するために、個々のトランクピアの構成要件を減らすことができます。 特定の仲介サーバークラスターに関連付けるゲートウェイとゲートウェイの数を計画するときは、トランクピアを同じローカルダイヤル要件でグループ化すると便利な場合があります。 これにより、必要な変換ルールの数と、それを記述するのにかかる時間が短縮されます。

<div>


> [!IMPORTANT]  
> 1つ以上の変換ルールをエンタープライズ Voip トランク構成に関連付けることは、トランクピアで変換ルールを構成するための代替手段として使用する必要があります。 トランクピアで変換ルールを構成している場合は、2つのルールが競合する可能性があるため、変換ルールをエンタープライズ Voip トランク構成に関連付けないでください。



</div>

<div>

## <a name="example-translation-rules"></a>変換ルールの例

以下の変換ルールの例では、トランク ピアについて E.164 形式からローカル形式に番号を変換するルールをサーバー上に作成する方法を示しています。

変換ルールを実装する方法の詳細については、「展開」のドキュメントの「 [Lync Server 2013 で変換ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。


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
<th>Length</th>
<th>削除する数字</th>
<th>追加する数字</th>
<th>一致パターン</th>
<th>翻訳</th>
<th>例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>米国内の従来の長距離電話ダイヤル</p>
<p>("+" を削除)</p></td>
<td><p>+ 1</p></td>
<td><p>ちょうど 12</p></td>
<td><p>1-d</p></td>
<td><p>.0</p></td>
<td><p>^\+(1/d{10}) $</p></td>
<td><p>$1</p></td>
<td><p>+14255551010 を 14255551010 に変換</p></td>
</tr>
<tr class="even">
<td><p>米国長距離国際電話ダイヤル</p>
<p>("+" を削除し、011 を追加)</p></td>
<td><p>+</p></td>
<td><p>11 以上</p></td>
<td><p>1-d</p></td>
<td><p>011</p></td>
<td><p>^\+(\d{9}\d +) $</p></td>
<td><p>011 $ 1</p></td>
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

