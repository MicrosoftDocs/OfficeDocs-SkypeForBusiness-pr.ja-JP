---
title: 'Lync Server 2013: ID プレゼンテーションと呼ばれる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Called ID presentation
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49733826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea49c91269c0a9c4f74a1a226462fbda26aa2af4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="called-id-presentation-in-lync-server-2013"></a>Lync Server 2013 での ID のプレゼンテーションの呼び出し

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

Lync Server 2010 では、発信者の電話番号 (と呼ばれる電話番号) は、トランクピア (つまり、関連付けられたゲートウェイ、構内交換機 (PBX)、または SIP トランク) で必要とされるローカルのダイヤル形式に変換できます。 これを行うためには、トランク ピアへのルーティングの前に要求 URI を変換する変換ルールを 1 つ以上定義する必要があります。

<div>


> [!IMPORTANT]  
> 1 つ以上の変換ルールをエンタープライズ VoIP のトランク構成と関連付ける機能は、トランク ピアに変換ルールを構成することの<EM>代替</EM>として使用されます。 トランク ピアで変換ルールを構成した場合は、2 つのルールが競合する可能性があるため、変換ルールをエンタープライズ VoIP トランク構成に関連付けないでください。



</div>

次のいずれかの方法を使用して、変換ルールを作成または変更できます。

  - [**変換ルールの構築**] ツールを使用して、先頭の数字、長さ、削除する数字、追加する数字の値を指定し、Lync Server コントロールパネルで対応する一致パターンと変換ルールを生成できるようにします。

  - 正規表現を手動で記述し、一致パターンと変換ルールを定義する。

<div>


> [!NOTE]  
> 正規表現を記述する方法については、「」の「.NET Framework <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A>正規表現」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 で変換ルールの構築ツールを使用して変換ルールを作成または変更する](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [Lync Server 2013 で変換ルールを手動で作成または変更する](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の発信者番号のプレゼンテーション](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

