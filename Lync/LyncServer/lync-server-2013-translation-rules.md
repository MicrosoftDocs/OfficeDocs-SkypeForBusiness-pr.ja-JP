---
title: 'Lync Server 2013: 変換ルール'
description: 'Lync Server 2013: 変換ルール。'
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
ms.openlocfilehash: 65ee21459123ea09f54eb52e65a4d9ecba61c386
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549043"
---
# <a name="translation-rules-in-lync-server-2013"></a><span data-ttu-id="08461-103">Lync Server 2013 の変換ルール</span><span class="sxs-lookup"><span data-stu-id="08461-103">Translation rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08461-104">_**トピックの最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="08461-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="08461-105">Lync Server 2013 エンタープライズ Voip では、逆引き番号検索 (RNL) を実行するために、すべてのダイヤル文字列が e.164 形式に正規化されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="08461-105">Lync Server 2013 Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="08461-106">Microsoft Lync Server 2010 では、変換ルールは、呼び出し先の番号に対してのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="08461-106">In Microsoft Lync Server 2010, translation rules are supported only for called numbers.</span></span> <span data-ttu-id="08461-107">Microsoft Lync Server 2013 の新製品では、電話番号の変換ルールもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="08461-107">New in Microsoft Lync Server 2013, translation rules are also supported for calling numbers.</span></span> <span data-ttu-id="08461-108">*トランクピア*(つまり、関連付けられたゲートウェイ、構内交換 LAN (PBX)、または SIP トランク) では、番号が地域のダイヤル形式になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="08461-108">The *trunk peer* (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="08461-109">番号を e.164 形式からローカルのダイヤル形式に変換するために、1つ以上の変換ルールを定義してから、トランクピアにルーティングする前に要求 URI を操作できます。</span><span class="sxs-lookup"><span data-stu-id="08461-109">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="08461-110">たとえば、ダイヤル文字列の先頭から +44 を削除して 0144 に置き換える変換ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="08461-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="08461-111">サーバーで送信ルート変換を実行すると、電話番号をローカルのダイヤル形式に変換するために、個々のトランクピアの構成要件を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="08461-111">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="08461-112">特定の仲介サーバークラスターに関連付けるゲートウェイとゲートウェイの数を計画するときは、トランクピアを同じローカルダイヤル要件でグループ化すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="08461-112">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="08461-113">これにより、必要な変換ルールの数と、それを記述するのにかかる時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="08461-113">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="08461-114">1つ以上の変換ルールをエンタープライズ Voip トランク構成に関連付けることは、トランクピアで変換ルールを構成するための代替手段として使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08461-114">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="08461-115">トランクピアで変換ルールを構成している場合は、2つのルールが競合する可能性があるため、変換ルールをエンタープライズ Voip トランク構成に関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="08461-115">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>



</div>

<div>

## <a name="example-translation-rules"></a><span data-ttu-id="08461-116">変換ルールの例</span><span class="sxs-lookup"><span data-stu-id="08461-116">Example Translation Rules</span></span>

<span data-ttu-id="08461-117">以下の変換ルールの例では、トランク ピアについて E.164 形式からローカル形式に番号を変換するルールをサーバー上に作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="08461-117">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="08461-118">変換ルールを実装する方法の詳細については、「展開」のドキュメントの「 [Lync Server 2013 で変換ルールを定義](lync-server-2013-defining-translation-rules.md) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08461-118">For details about how to implement translation rules, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>


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
<th><span data-ttu-id="08461-119">説明</span><span class="sxs-lookup"><span data-stu-id="08461-119">Description</span></span></th>
<th><span data-ttu-id="08461-120">先頭の数字</span><span class="sxs-lookup"><span data-stu-id="08461-120">Starting Digits</span></span></th>
<th><span data-ttu-id="08461-121">Length</span><span class="sxs-lookup"><span data-stu-id="08461-121">Length</span></span></th>
<th><span data-ttu-id="08461-122">削除する数字</span><span class="sxs-lookup"><span data-stu-id="08461-122">Digits to Remove</span></span></th>
<th><span data-ttu-id="08461-123">追加する数字</span><span class="sxs-lookup"><span data-stu-id="08461-123">Digits to Add</span></span></th>
<th><span data-ttu-id="08461-124">一致パターン</span><span class="sxs-lookup"><span data-stu-id="08461-124">Matching Pattern</span></span></th>
<th><span data-ttu-id="08461-125">変換</span><span class="sxs-lookup"><span data-stu-id="08461-125">Translation</span></span></th>
<th><span data-ttu-id="08461-126">例</span><span class="sxs-lookup"><span data-stu-id="08461-126">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08461-127">米国内の従来の長距離電話ダイヤル</span><span class="sxs-lookup"><span data-stu-id="08461-127">Conventional long-distance dialing in U.S.</span></span></p>
<p><span data-ttu-id="08461-128">("+" を削除)</span><span class="sxs-lookup"><span data-stu-id="08461-128">(strip out the ‘+’)</span></span></p></td>
<td><p><span data-ttu-id="08461-129">+ 1</span><span class="sxs-lookup"><span data-stu-id="08461-129">+1</span></span></p></td>
<td><p><span data-ttu-id="08461-130">ちょうど 12</span><span class="sxs-lookup"><span data-stu-id="08461-130">Exactly 12</span></span></p></td>
<td><p><span data-ttu-id="08461-131">1-d</span><span class="sxs-lookup"><span data-stu-id="08461-131">1</span></span></p></td>
<td><p><span data-ttu-id="08461-132">.0</span><span class="sxs-lookup"><span data-stu-id="08461-132">0</span></span></p></td>
<td><p><span data-ttu-id="08461-133">^\+(1 \ d {10} )$</span><span class="sxs-lookup"><span data-stu-id="08461-133">^\+(1\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="08461-134">$1</span><span class="sxs-lookup"><span data-stu-id="08461-134">$1</span></span></p></td>
<td><p><span data-ttu-id="08461-135">+14255551010 を 14255551010 に変換</span><span class="sxs-lookup"><span data-stu-id="08461-135">+14255551010 becomes 14255551010</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08461-136">米国長距離国際電話ダイヤル</span><span class="sxs-lookup"><span data-stu-id="08461-136">U.S. international long-distance dialing</span></span></p>
<p><span data-ttu-id="08461-137">("+" を削除し、011 を追加)</span><span class="sxs-lookup"><span data-stu-id="08461-137">(strip out ‘+’ and add 011)</span></span></p></td>
<td><p>+</p></td>
<td><p><span data-ttu-id="08461-138">11 以上</span><span class="sxs-lookup"><span data-stu-id="08461-138">At least 11</span></span></p></td>
<td><p><span data-ttu-id="08461-139">1-d</span><span class="sxs-lookup"><span data-stu-id="08461-139">1</span></span></p></td>
<td><p><span data-ttu-id="08461-140">011</span><span class="sxs-lookup"><span data-stu-id="08461-140">011</span></span></p></td>
<td><p><span data-ttu-id="08461-141">^\+(\d {9} \d +) $</span><span class="sxs-lookup"><span data-stu-id="08461-141">^\+(\d{9}\d+)$</span></span></p></td>
<td><p><span data-ttu-id="08461-142">011 $ 1</span><span class="sxs-lookup"><span data-stu-id="08461-142">011$1</span></span></p></td>
<td><p><span data-ttu-id="08461-143">+441235551010 を 011441235551010 に変換</span><span class="sxs-lookup"><span data-stu-id="08461-143">+441235551010 becomes 011441235551010</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

