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
ms.openlocfilehash: dddb1902422cb3efc52f4f0b3271976ab9b9950e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508224"
---
# <a name="called-id-presentation-in-lync-server-2013"></a><span data-ttu-id="2f01d-102">Lync Server 2013 での ID のプレゼンテーションの呼び出し</span><span class="sxs-lookup"><span data-stu-id="2f01d-102">Called ID presentation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f01d-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="2f01d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="2f01d-104">Lync Server 2010 では、発信者の電話番号 (と呼ばれる電話番号) は、トランクピア (つまり、関連付けられたゲートウェイ、構内交換機 (PBX)、または SIP トランク) で必要とされるローカルのダイヤル形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="2f01d-104">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="2f01d-105">これを行うためには、トランク ピアへのルーティングの前に要求 URI を変換する変換ルールを 1 つ以上定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f01d-105">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2f01d-p102">1 つ以上の変換ルールをエンタープライズ VoIP のトランク構成と関連付ける機能は、トランク ピアに変換ルールを構成することの<EM>代替</EM>として使用されます。 トランク ピアで変換ルールを構成した場合は、2 つのルールが競合する可能性があるため、変換ルールをエンタープライズ VoIP トランク構成に関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="2f01d-p102">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an <EM>alternative</EM> to configuring translation rules on the trunk peer. Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span>



</div>

<span data-ttu-id="2f01d-108">次のいずれかの方法を使用して、変換ルールを作成または変更できます。</span><span class="sxs-lookup"><span data-stu-id="2f01d-108">You can use either of the following methods to create or modify a translation rule:</span></span>

  - <span data-ttu-id="2f01d-109">[ **変換ルールの構築** ] ツールを使用して、先頭の数字、長さ、削除する数字、追加する数字の値を指定し、Lync Server コントロールパネルで対応する一致パターンと変換ルールを生成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2f01d-109">Use the **Build a Translation Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="2f01d-110">正規表現を手動で記述し、一致パターンと変換ルールを定義する。</span><span class="sxs-lookup"><span data-stu-id="2f01d-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2f01d-111">正規表現を記述する方法については、「」の「.NET Framework 正規表現」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A> 。</span><span class="sxs-lookup"><span data-stu-id="2f01d-111">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2f01d-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2f01d-112">In This Section</span></span>

  - [<span data-ttu-id="2f01d-113">Lync Server 2013 で変換ルールの構築ツールを使用して変換ルールを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="2f01d-113">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [<span data-ttu-id="2f01d-114">Lync Server 2013 で変換ルールを手動で作成または変更する</span><span class="sxs-lookup"><span data-stu-id="2f01d-114">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2f01d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f01d-115">See Also</span></span>


[<span data-ttu-id="2f01d-116">Lync Server 2013 の発信者番号のプレゼンテーション</span><span class="sxs-lookup"><span data-stu-id="2f01d-116">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

