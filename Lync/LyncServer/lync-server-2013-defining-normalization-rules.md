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
ms.openlocfilehash: 935df08bd1ede124b048427de21594aa6e727e7c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504514"
---
# <a name="defining-normalization-rules-in-lync-server-2013"></a>Lync Server 2013 での正規化ルールの定義

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-04-22_

Lync Server 2013 の正規化ルールは、.NET Framework 正規表現を使用して、ダイヤルされた電話番号を e.164 形式に変換します。言い換えると、正規化ルールは、ユーザーがダイヤルした電話番号を取得し、その番号を Lync Server で内部的に使用される形式に変換します。 各ダイヤル プランには、正規化ルールを 1 つ以上割り当てる必要があります。

正規化ルールの詳細については、「計画」のドキュメントの「 [ダイヤルプランと正規化ルール (Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) )」を参照してください。

正規表現の記述方法の詳細については、「」の「.NET Framework の正規表現」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) 。

正規化ルールを定義または編集するには、次のいずれかの方法を使用できます。

  - [ **正規化ルールの構築** ] ツールを使用して、先頭の数字、長さ、削除する数字、追加する数字の値を指定し、Lync Server コントロールパネルで対応する一致パターンと変換ルールを生成するようにします。

  - 正規表現を手動で記述し、一致パターンと変換ルールを定義する。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [「Lync Server 2013 で正規化ルールを構築する」を使用して正規化ルールを作成または変更する](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [Lync Server 2013 で正規化ルールを手動で作成または変更する](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でダイヤルプランを作成する](lync-server-2013-create-a-dial-plan.md)  
[Lync Server 2013 でダイヤルプランを変更する](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

