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
ms.openlocfilehash: 8dc22438a688239618fc7a73cf3aa30ec614568d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="called-id-presentation-in-lync-server-2013"></a><span data-ttu-id="35213-102">Lync Server 2013 の ID プレゼンテーション</span><span class="sxs-lookup"><span data-stu-id="35213-102">Called ID presentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35213-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="35213-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="35213-104">Lync Server 2010 を使用すると、通話先の国の電話番号 (電話番号) を、トランクのピアによって要求されるローカルのダイヤル形式 (関連付けられているゲートウェイ、構内交換機 (PBX)、SIP トランクなど) に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="35213-104">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="35213-105">これを行うためには、トランク ピアへのルーティングの前に要求 URI を変換する変換ルールを 1 つ以上定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35213-105">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="35213-106">エンタープライズボイストランク構成に1つまたは複数の翻訳ルールを関連付ける機能は、トランクピアでの翻訳ルールの設定の<EM>代わり</EM>として使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="35213-106">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an <EM>alternative</EM> to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="35213-107">2つのルールが競合する可能性があるため、トランクピアで翻訳ルールを構成している場合、翻訳ルールをエンタープライズボイストランク構成に関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="35213-107">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span>



</div>

<span data-ttu-id="35213-108">翻訳ルールを作成または変更するには、次のいずれかの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="35213-108">You can use either of the following methods to create or modify a translation rule:</span></span>

  - <span data-ttu-id="35213-109">[**翻訳ルールの作成**] ツールを使用して、開始番号、長さ、削除する数字の値、追加する数字を指定します。次に、Lync Server コントロールパネルで、対応する一致パターンと翻訳ルールを生成できます。</span><span class="sxs-lookup"><span data-stu-id="35213-109">Use the **Build a Translation Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="35213-110">一致するパターンと翻訳ルールを定義するために、正規表現を手動で記述します。</span><span class="sxs-lookup"><span data-stu-id="35213-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="35213-111">正規表現の記述方法については、「.NET Framework の正規表現」 <A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35213-111">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at <A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="35213-112">このセクション中</span><span class="sxs-lookup"><span data-stu-id="35213-112">In This Section</span></span>

  - [<span data-ttu-id="35213-113">Lync Server 2013 の翻訳ルールの作成ツールを使用して、翻訳ルールを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="35213-113">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [<span data-ttu-id="35213-114">Lync Server 2013 で翻訳ルールを手動で作成または変更する</span><span class="sxs-lookup"><span data-stu-id="35213-114">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="35213-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="35213-115">See Also</span></span>


[<span data-ttu-id="35213-116">Lync Server 2013 での発信者番号通知のプレゼンテーション</span><span class="sxs-lookup"><span data-stu-id="35213-116">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

