---
title: Skype for Business Server の翻訳ルール
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: Skype for Business Server Enterprise Voice での翻訳ルールとダイヤル文字列の正規化について説明します。
ms.openlocfilehash: 1f435db01b5b15c97ae577565e4ba43f5de554ea
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297366"
---
# <a name="translation-rules-in-skype-for-business-server"></a><span data-ttu-id="423c5-103">Skype for Business Server の翻訳ルール</span><span class="sxs-lookup"><span data-stu-id="423c5-103">Translation rules in Skype for Business Server</span></span>

<span data-ttu-id="423c5-104">Skype for Business Server Enterprise Voice での翻訳ルールとダイヤル文字列の正規化について説明します。</span><span class="sxs-lookup"><span data-stu-id="423c5-104">Learn about translation rules and dial string normalization in Skype for Business Server Enterprise Voice.</span></span>

 <span data-ttu-id="423c5-105">エンタープライズボイスでは、逆引き数値参照 (RNL) を実行するために、すべてのダイヤル文字列が E.i 形式に正規化されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="423c5-105">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="423c5-106">翻訳ルールは、電話番号と通話番号の両方でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="423c5-106">Translation rules are supported for both called numbers and calling numbers.</span></span> <span data-ttu-id="423c5-107">トランクピア (つまり、関連付けられているゲートウェイ、プライベートブランチ exchange (PBX)、または SIP トランク) では、電話番号が市内ダイヤル形式になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="423c5-107">Thetrunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="423c5-108">E.164 形式から地域のダイヤル形式に番号を変換するには、トランク ピアにルーティングする前に 1 つ以上の変換ルールを定義して要求 URI を操作することができます。</span><span class="sxs-lookup"><span data-stu-id="423c5-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="423c5-109">たとえば、ダイヤル文字列の先頭から +44 を削除して 0144 に置き換える変換ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="423c5-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="423c5-110">サーバーで送信ルートの翻訳を実行すると、電話番号をローカルのダイヤル形式に変換するために、個々のトランクピアの構成要件を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="423c5-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="423c5-111">ゲートウェイとゲートウェイの数を計画しているときに、特定の仲介サーバークラスターと関連付けるには、同様のローカルダイヤル要件でトランクピアをグループ化すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="423c5-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="423c5-112">これにより、必要な翻訳ルールの数と書き込みにかかる時間を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="423c5-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="423c5-113">1つまたは複数の翻訳ルールをエンタープライズボイストランク構成に関連付けることは、トランクピアでの翻訳ルールの設定の代わりとして使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="423c5-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="423c5-114">トランクピアで翻訳ルールを構成している場合は、2つのルールが競合する可能性があるため、翻訳ルールをエンタープライズボイストランク構成に関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="423c5-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>

## <a name="example-translation-rules"></a><span data-ttu-id="423c5-115">変換ルールの例</span><span class="sxs-lookup"><span data-stu-id="423c5-115">Example Translation Rules</span></span>

<span data-ttu-id="423c5-116">以下の変換ルールの例では、トランク ピアについて E.164 形式からローカル形式に番号を変換するルールをサーバー上に作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="423c5-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="423c5-117">変換ルールを実装する方法については、「展開」のドキュメントの「[Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="423c5-117">For details about how to implement translation rules, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

|<span data-ttu-id="423c5-118">**説明**</span><span class="sxs-lookup"><span data-stu-id="423c5-118">**Description**</span></span>|<span data-ttu-id="423c5-119">**先頭の数字**</span><span class="sxs-lookup"><span data-stu-id="423c5-119">**Starting Digits**</span></span>|<span data-ttu-id="423c5-120">**長さ**</span><span class="sxs-lookup"><span data-stu-id="423c5-120">**Length**</span></span>|<span data-ttu-id="423c5-121">**削除する数字**</span><span class="sxs-lookup"><span data-stu-id="423c5-121">**Digits to Remove**</span></span>|<span data-ttu-id="423c5-122">**追加する数字**</span><span class="sxs-lookup"><span data-stu-id="423c5-122">**Digits to Add**</span></span>|<span data-ttu-id="423c5-123">**照合パターン**</span><span class="sxs-lookup"><span data-stu-id="423c5-123">**Matching Pattern**</span></span>|<span data-ttu-id="423c5-124">**変換**</span><span class="sxs-lookup"><span data-stu-id="423c5-124">**Translation**</span></span>|<span data-ttu-id="423c5-125">**例**</span><span class="sxs-lookup"><span data-stu-id="423c5-125">**Example**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="423c5-126">米国内の従来の長距離電話ダイヤル</span><span class="sxs-lookup"><span data-stu-id="423c5-126">Conventional long-distance dialing in U.S.</span></span>  <br/> <span data-ttu-id="423c5-127">(「+」を取り除きます)</span><span class="sxs-lookup"><span data-stu-id="423c5-127">(strip out the '+')</span></span>  <br/> |<span data-ttu-id="423c5-128">+1</span><span class="sxs-lookup"><span data-stu-id="423c5-128">+1</span></span>  <br/> |<span data-ttu-id="423c5-129">ちょうど 12</span><span class="sxs-lookup"><span data-stu-id="423c5-129">Exactly 12</span></span>  <br/> |<span data-ttu-id="423c5-130">1</span><span class="sxs-lookup"><span data-stu-id="423c5-130">1</span></span>  <br/> |<span data-ttu-id="423c5-131">0</span><span class="sxs-lookup"><span data-stu-id="423c5-131">0</span></span>  <br/> |<span data-ttu-id="423c5-132">^\+(1 \ d{10}) $</span><span class="sxs-lookup"><span data-stu-id="423c5-132">^\+(1\d{10})$</span></span>  <br/> |<span data-ttu-id="423c5-133">$1</span><span class="sxs-lookup"><span data-stu-id="423c5-133">$1</span></span>  <br/> |<span data-ttu-id="423c5-134">+14255551010 を 14255551010 に変換</span><span class="sxs-lookup"><span data-stu-id="423c5-134">+14255551010 becomes 14255551010</span></span>  <br/> |
|<span data-ttu-id="423c5-135">米国長距離国際電話ダイヤル</span><span class="sxs-lookup"><span data-stu-id="423c5-135">U.S. international long-distance dialing</span></span>  <br/> <span data-ttu-id="423c5-136">(「+」をタップして、011を追加)</span><span class="sxs-lookup"><span data-stu-id="423c5-136">(strip out '+' and add 011)</span></span>  <br/> |+  <br/> |<span data-ttu-id="423c5-137">11 以上</span><span class="sxs-lookup"><span data-stu-id="423c5-137">At least 11</span></span>  <br/> |<span data-ttu-id="423c5-138">1</span><span class="sxs-lookup"><span data-stu-id="423c5-138">1</span></span>  <br/> |<span data-ttu-id="423c5-139">011</span><span class="sxs-lookup"><span data-stu-id="423c5-139">011</span></span>  <br/> |<span data-ttu-id="423c5-140">^\+(\d{9}\d +) $</span><span class="sxs-lookup"><span data-stu-id="423c5-140">^\+(\d{9}\d+)$</span></span>  <br/> |<span data-ttu-id="423c5-141">011$1</span><span class="sxs-lookup"><span data-stu-id="423c5-141">011$1</span></span>  <br/> |<span data-ttu-id="423c5-142">+441235551010 を 011441235551010 に変換</span><span class="sxs-lookup"><span data-stu-id="423c5-142">+441235551010 becomes 011441235551010</span></span>  <br/> |


