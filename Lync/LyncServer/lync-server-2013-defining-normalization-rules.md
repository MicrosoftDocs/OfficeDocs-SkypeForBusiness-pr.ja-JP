---
title: 'Lync Server 2013: 正規化ルールの定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining normalization rules
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399071(v=OCS.15)
ms:contentKeyID: 48185741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b75883d99d218d711e9d96de7ebfd7d360972a6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-normalization-rules-in-lync-server-2013"></a>Lync Server 2013 の正規化ルールの定義

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-04-22_

Lync Server 2013 正規化ルールは、ダイヤルした電話番号を E-164 形式に変換するために .NET Framework の正規表現を使用します。つまり、正規化ルールは、ユーザーがダイヤルした電話番号を取得し、その番号を Lync Server が内部的に使用する形式に変換します。 各ダイヤル プランには、正規化ルールを 1 つ以上割り当てる必要があります。

正規化ルールの詳細については、計画ドキュメントの「 [Lync Server 2013 でのダイヤルプランと正規化ルール](lync-server-2013-dial-plans-and-normalization-rules.md)」を参照してください。

正規表現の記述方法の詳細については、「」の「.NET [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)Framework の正規表現」を参照してください。

正規化ルールを定義または編集するには、次のいずれかの方法を使用できます。

  - [**正規化ルールのビルド**] ツールを使用して、先頭の数字、長さ、削除する数字、追加する数字の値を指定します。これにより、Lync Server コントロールパネルで、対応する一致パターンと翻訳ルールを生成できます。

  - 一致するパターンと翻訳ルールを定義するために、正規表現を手動で記述します。

<div>

## <a name="in-this-section"></a>このセクション中

  - [「Lync Server 2013 で正規化ルールを作成する」を使用して正規化ルールを作成または変更する](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [Lync Server 2013 での手動による正規化ルールの作成または変更](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でダイヤルプランを作成する](lync-server-2013-create-a-dial-plan.md)  
[Lync Server 2013 でのダイヤル プランの変更](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

