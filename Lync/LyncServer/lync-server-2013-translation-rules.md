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

# <a name="translation-rules-in-lync-server-2013"></a><span data-ttu-id="c845a-102">Lync Server 2013 の翻訳ルール</span><span class="sxs-lookup"><span data-stu-id="c845a-102">Translation rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c845a-103">_**最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="c845a-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="c845a-104">Lync Server 2013 エンタープライズボイスでは、逆引き数値参照 (RNL) を実行するために、すべてのダイヤル文字列が E.i 形式に正規化されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c845a-104">Lync Server 2013 Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="c845a-105">Microsoft Lync Server 2010 では、翻訳ルールは、呼び出した番号に対してのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c845a-105">In Microsoft Lync Server 2010, translation rules are supported only for called numbers.</span></span> <span data-ttu-id="c845a-106">Microsoft Lync Server 2013 の新機能には、翻訳ルールも含まれています。</span><span class="sxs-lookup"><span data-stu-id="c845a-106">New in Microsoft Lync Server 2013, translation rules are also supported for calling numbers.</span></span> <span data-ttu-id="c845a-107">*トランク ピア* (つまり、関連付けられたゲートウェイ、構内交換機 (PBX)、または SIP トランク) では、番号を地域のダイヤル形式にすることが必要な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="c845a-107">The *trunk peer* (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="c845a-108">E.164 形式から地域のダイヤル形式に番号を変換するには、トランク ピアにルーティングする前に 1 つ以上の変換ルールを定義して要求 URI を操作することができます。</span><span class="sxs-lookup"><span data-stu-id="c845a-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="c845a-109">たとえば、ダイヤル文字列の先頭から +44 を削除して 0144 に置き換える変換ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c845a-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="c845a-110">サーバーで送信ルートの翻訳を実行すると、電話番号をローカルのダイヤル形式に変換するために、個々のトランクピアの構成要件を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="c845a-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="c845a-111">ゲートウェイとゲートウェイの数を計画しているときに、特定の仲介サーバークラスターと関連付けるには、同様のローカルダイヤル要件でトランクピアをグループ化すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c845a-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="c845a-112">これにより、必要な翻訳ルールの数と書き込みにかかる時間を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="c845a-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c845a-113">1つまたは複数の翻訳ルールをエンタープライズボイストランク構成に関連付けることは、トランクピアでの翻訳ルールの設定の代わりとして使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c845a-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="c845a-114">トランクピアで翻訳ルールを構成している場合は、2つのルールが競合する可能性があるため、翻訳ルールをエンタープライズボイストランク構成に関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="c845a-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>



</div>

<div>

## <a name="example-translation-rules"></a><span data-ttu-id="c845a-115">変換ルールの例</span><span class="sxs-lookup"><span data-stu-id="c845a-115">Example Translation Rules</span></span>

<span data-ttu-id="c845a-116">以下の変換ルールの例では、トランク ピアについて E.164 形式からローカル形式に番号を変換するルールをサーバー上に作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c845a-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="c845a-117">翻訳ルールの実装方法の詳細については、展開ドキュメントの「 [Lync Server 2013 で翻訳ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c845a-117">For details about how to implement translation rules, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>


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
<th><span data-ttu-id="c845a-118">説明</span><span class="sxs-lookup"><span data-stu-id="c845a-118">Description</span></span></th>
<th><span data-ttu-id="c845a-119">先頭の数字</span><span class="sxs-lookup"><span data-stu-id="c845a-119">Starting Digits</span></span></th>
<th><span data-ttu-id="c845a-120">長さ</span><span class="sxs-lookup"><span data-stu-id="c845a-120">Length</span></span></th>
<th><span data-ttu-id="c845a-121">削除する数字</span><span class="sxs-lookup"><span data-stu-id="c845a-121">Digits to Remove</span></span></th>
<th><span data-ttu-id="c845a-122">追加する数字</span><span class="sxs-lookup"><span data-stu-id="c845a-122">Digits to Add</span></span></th>
<th><span data-ttu-id="c845a-123">一致パターン</span><span class="sxs-lookup"><span data-stu-id="c845a-123">Matching Pattern</span></span></th>
<th><span data-ttu-id="c845a-124">変換</span><span class="sxs-lookup"><span data-stu-id="c845a-124">Translation</span></span></th>
<th><span data-ttu-id="c845a-125">例</span><span class="sxs-lookup"><span data-stu-id="c845a-125">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c845a-126">米国内の従来の長距離電話ダイヤル</span><span class="sxs-lookup"><span data-stu-id="c845a-126">Conventional long-distance dialing in U.S.</span></span></p>
<p><span data-ttu-id="c845a-127">("+" を削除)</span><span class="sxs-lookup"><span data-stu-id="c845a-127">(strip out the ‘+’)</span></span></p></td>
<td><p><span data-ttu-id="c845a-128">+1</span><span class="sxs-lookup"><span data-stu-id="c845a-128">+1</span></span></p></td>
<td><p><span data-ttu-id="c845a-129">ちょうど 12</span><span class="sxs-lookup"><span data-stu-id="c845a-129">Exactly 12</span></span></p></td>
<td><p><span data-ttu-id="c845a-130">1</span><span class="sxs-lookup"><span data-stu-id="c845a-130">1</span></span></p></td>
<td><p><span data-ttu-id="c845a-131">0</span><span class="sxs-lookup"><span data-stu-id="c845a-131">0</span></span></p></td>
<td><p><span data-ttu-id="c845a-132">^\+(1 \ d{10}) $</span><span class="sxs-lookup"><span data-stu-id="c845a-132">^\+(1\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="c845a-133">$1</span><span class="sxs-lookup"><span data-stu-id="c845a-133">$1</span></span></p></td>
<td><p><span data-ttu-id="c845a-134">+14255551010 を 14255551010 に変換</span><span class="sxs-lookup"><span data-stu-id="c845a-134">+14255551010 becomes 14255551010</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c845a-135">米国長距離国際電話ダイヤル</span><span class="sxs-lookup"><span data-stu-id="c845a-135">U.S. international long-distance dialing</span></span></p>
<p><span data-ttu-id="c845a-136">("+" を削除し、011 を追加)</span><span class="sxs-lookup"><span data-stu-id="c845a-136">(strip out ‘+’ and add 011)</span></span></p></td>
<td><p>+</p></td>
<td><p><span data-ttu-id="c845a-137">11 以上</span><span class="sxs-lookup"><span data-stu-id="c845a-137">At least 11</span></span></p></td>
<td><p><span data-ttu-id="c845a-138">1</span><span class="sxs-lookup"><span data-stu-id="c845a-138">1</span></span></p></td>
<td><p><span data-ttu-id="c845a-139">011</span><span class="sxs-lookup"><span data-stu-id="c845a-139">011</span></span></p></td>
<td><p><span data-ttu-id="c845a-140">^\+(\d{9}\d +) $</span><span class="sxs-lookup"><span data-stu-id="c845a-140">^\+(\d{9}\d+)$</span></span></p></td>
<td><p><span data-ttu-id="c845a-141">011$1</span><span class="sxs-lookup"><span data-stu-id="c845a-141">011$1</span></span></p></td>
<td><p><span data-ttu-id="c845a-142">+441235551010 を 011441235551010 に変換</span><span class="sxs-lookup"><span data-stu-id="c845a-142">+441235551010 becomes 011441235551010</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

