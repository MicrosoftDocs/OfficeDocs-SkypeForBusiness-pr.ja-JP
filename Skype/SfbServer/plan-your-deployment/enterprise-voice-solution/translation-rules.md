---
title: Skype for Business Server の変換ルール
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: Skype for Business Server エンタープライズ VoIP での変換ルールとダイヤル文字列正規化について説明します。
ms.openlocfilehash: 0c00776dae502bfd28bbe27e90012fabb6e25c93
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802687"
---
# <a name="translation-rules-in-skype-for-business-server"></a><span data-ttu-id="f371e-103">Skype for Business Server の変換ルール</span><span class="sxs-lookup"><span data-stu-id="f371e-103">Translation rules in Skype for Business Server</span></span>

<span data-ttu-id="f371e-104">Skype for Business Server エンタープライズ VoIP での変換ルールとダイヤル文字列正規化について説明します。</span><span class="sxs-lookup"><span data-stu-id="f371e-104">Learn about translation rules and dial string normalization in Skype for Business Server Enterprise Voice.</span></span>

 <span data-ttu-id="f371e-105">エンタープライズ VoIP、逆引き番号検索 (RNL) を実行するために、すべてのダイヤル文字列を E.164 形式に正規化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f371e-105">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="f371e-106">変換ルールは、呼び出し元の番号と呼び出し元の番号の両方でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f371e-106">Translation rules are supported for both called numbers and calling numbers.</span></span> <span data-ttu-id="f371e-107">トランク ピア (つまり、関連付けられたゲートウェイ、PBX (PBX)、または SIP トランク) では、番号がローカル ダイヤル形式である必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f371e-107">Thetrunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="f371e-108">E.164 形式からローカルダイヤル形式に番号を変換するには、トランク ピアにルーティングする前に、1 つ以上の変換ルールを定義して要求 URI を操作できます。</span><span class="sxs-lookup"><span data-stu-id="f371e-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="f371e-109">たとえば、ダイヤル文字列の先頭から +44 を削除して 0144 に置き換える変換ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f371e-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="f371e-110">サーバーで発信ルート変換を実行すると、電話番号をローカルのダイヤル形式に変換するために、個々のトランク ピアの構成要件を減らできます。</span><span class="sxs-lookup"><span data-stu-id="f371e-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="f371e-111">特定の仲介サーバー クラスターに関連付けるゲートウェイとゲートウェイの数を計画する場合、同様のローカル ダイヤル要件を持つトランク ピアをグループ化すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f371e-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="f371e-112">これにより、必要な変換ルールの数と書き込みにかかる時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="f371e-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f371e-113">1 つ以上の変換ルールを エンタープライズ VoIP トランク構成に関連付け、トランク ピアで変換ルールを構成する代わりに使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f371e-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="f371e-114">2 つのルールが競合する可能性エンタープライズ VoIPトランク ピアで変換ルールを構成している場合は、変換ルールをトランク構成に関連付けない。</span><span class="sxs-lookup"><span data-stu-id="f371e-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>

## <a name="example-translation-rules"></a><span data-ttu-id="f371e-115">変換ルールの例</span><span class="sxs-lookup"><span data-stu-id="f371e-115">Example Translation Rules</span></span>

<span data-ttu-id="f371e-116">以下の変換ルールの例では、トランク ピアについて E.164 形式からローカル形式に番号を変換するルールをサーバー上に作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f371e-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="f371e-117">変換ルールを実装する方法については、「展開」のドキュメントの「[Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f371e-117">For details about how to implement translation rules, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

|<span data-ttu-id="f371e-118">**説明**</span><span class="sxs-lookup"><span data-stu-id="f371e-118">**Description**</span></span>|<span data-ttu-id="f371e-119">**先頭の数字**</span><span class="sxs-lookup"><span data-stu-id="f371e-119">**Starting Digits**</span></span>|<span data-ttu-id="f371e-120">**Length**</span><span class="sxs-lookup"><span data-stu-id="f371e-120">**Length**</span></span>|<span data-ttu-id="f371e-121">**削除する数字**</span><span class="sxs-lookup"><span data-stu-id="f371e-121">**Digits to Remove**</span></span>|<span data-ttu-id="f371e-122">**追加する数字**</span><span class="sxs-lookup"><span data-stu-id="f371e-122">**Digits to Add**</span></span>|<span data-ttu-id="f371e-123">**一致パターン**</span><span class="sxs-lookup"><span data-stu-id="f371e-123">**Matching Pattern**</span></span>|<span data-ttu-id="f371e-124">**翻訳**</span><span class="sxs-lookup"><span data-stu-id="f371e-124">**Translation**</span></span>|<span data-ttu-id="f371e-125">**例**</span><span class="sxs-lookup"><span data-stu-id="f371e-125">**Example**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f371e-126">米国内の従来の長距離電話ダイヤル</span><span class="sxs-lookup"><span data-stu-id="f371e-126">Conventional long-distance dialing in U.S.</span></span>  <br/> <span data-ttu-id="f371e-127">('+' を取り除く)</span><span class="sxs-lookup"><span data-stu-id="f371e-127">(strip out the '+')</span></span>  <br/> |<span data-ttu-id="f371e-128">+1</span><span class="sxs-lookup"><span data-stu-id="f371e-128">+1</span></span>  <br/> |<span data-ttu-id="f371e-129">ちょうど 12</span><span class="sxs-lookup"><span data-stu-id="f371e-129">Exactly 12</span></span>  <br/> |<span data-ttu-id="f371e-130">1 </span><span class="sxs-lookup"><span data-stu-id="f371e-130">1</span></span>  <br/> |<span data-ttu-id="f371e-131">0</span><span class="sxs-lookup"><span data-stu-id="f371e-131">0</span></span>  <br/> |<span data-ttu-id="f371e-132">^\+(1\d {10} )$</span><span class="sxs-lookup"><span data-stu-id="f371e-132">^\+(1\d{10})$</span></span>  <br/> |<span data-ttu-id="f371e-133">$1</span><span class="sxs-lookup"><span data-stu-id="f371e-133">$1</span></span>  <br/> |<span data-ttu-id="f371e-134">+14255551010 を 14255551010 に変換</span><span class="sxs-lookup"><span data-stu-id="f371e-134">+14255551010 becomes 14255551010</span></span>  <br/> |
|<span data-ttu-id="f371e-135">米国長距離国際電話ダイヤル</span><span class="sxs-lookup"><span data-stu-id="f371e-135">U.S. international long-distance dialing</span></span>  <br/> <span data-ttu-id="f371e-136">('+' を削除して 011 を追加)</span><span class="sxs-lookup"><span data-stu-id="f371e-136">(strip out '+' and add 011)</span></span>  <br/> |+  <br/> |<span data-ttu-id="f371e-137">11 以上</span><span class="sxs-lookup"><span data-stu-id="f371e-137">At least 11</span></span>  <br/> |<span data-ttu-id="f371e-138">1 </span><span class="sxs-lookup"><span data-stu-id="f371e-138">1</span></span>  <br/> |<span data-ttu-id="f371e-139">011</span><span class="sxs-lookup"><span data-stu-id="f371e-139">011</span></span>  <br/> |<span data-ttu-id="f371e-140">^\+(\d {9} \d+)$</span><span class="sxs-lookup"><span data-stu-id="f371e-140">^\+(\d{9}\d+)$</span></span>  <br/> |<span data-ttu-id="f371e-141">011$1</span><span class="sxs-lookup"><span data-stu-id="f371e-141">011$1</span></span>  <br/> |<span data-ttu-id="f371e-142">+441235551010 を 011441235551010 に変換</span><span class="sxs-lookup"><span data-stu-id="f371e-142">+441235551010 becomes 011441235551010</span></span>  <br/> |


