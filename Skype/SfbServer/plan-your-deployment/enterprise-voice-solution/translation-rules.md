---
title: Skype for Business Server 2015 での変換ルール
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: 変換規則について説明し、ビジネス サーバーのエンタープライズ VoIP の Skype で文字列の正規化をダイヤルします。
ms.openlocfilehash: c72e3909fdc0e4485683382b84a5d737fa75b8fc
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="translation-rules-in-skype-for-business-server-2015"></a><span data-ttu-id="8712d-103">Skype for Business Server 2015 での変換ルール</span><span class="sxs-lookup"><span data-stu-id="8712d-103">Translation rules in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8712d-104">変換規則について説明し、ビジネス サーバーのエンタープライズ VoIP の Skype で文字列の正規化をダイヤルします。</span><span class="sxs-lookup"><span data-stu-id="8712d-104">Learn about translation rules and dial string normalization in Skype for Business Server Enterprise Voice.</span></span>
  
 <span data-ttu-id="8712d-105">エンタープライズ VoIP では、すべてのダイヤル文字列が番号の逆引き参照 (RNL) を実行するための E.164 形式に正規化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8712d-105">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="8712d-106">翻訳ルールと呼ばれる番号と呼び出し元の番号の両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="8712d-106">Translation rules are supported for both called numbers and calling numbers.</span></span> <span data-ttu-id="8712d-107">Thetrunk ピア (つまり、関連付けられているゲートウェイ、構内交換機 (PBX)、または SIP トランク) は、ローカルのダイヤル形式の数値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8712d-107">Thetrunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="8712d-108">E.164 形式から地域のダイヤル形式に番号を変換するには、トランク ピアにルーティングする前に 1 つ以上の変換ルールを定義して要求 URI を操作することができます。</span><span class="sxs-lookup"><span data-stu-id="8712d-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="8712d-109">たとえば、ダイヤル文字列の先頭から +44 を削除して 0144 に置き換える変換ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8712d-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
<span data-ttu-id="8712d-110">発信ルート変換を実行するサーバー上で、電話番号をダイアル形式に変換するのにはそれぞれ個々 のトランク ピアの構成要件を削減できます。</span><span class="sxs-lookup"><span data-stu-id="8712d-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="8712d-111">どのゲートウェイとに関連付ける特定の仲介サーバー クラスターでは、どのように多くのゲートウェイを計画するときのようなローカルのトランク ピアのグループに役に立ちますダイヤル要件。</span><span class="sxs-lookup"><span data-stu-id="8712d-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="8712d-112">これは、必要な変換ルールの数とそれらの書き込みにかかる時間を短縮できます。</span><span class="sxs-lookup"><span data-stu-id="8712d-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8712d-113">トランク ピアで変換ルールを構成する代わりに、1 つまたは複数の変換ルールをエンタープライズ VoIP のトランク構成に関連付けるを使用してください。</span><span class="sxs-lookup"><span data-stu-id="8712d-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="8712d-114">関連づけられていない変換規則は、エンタープライズ VoIP のトランク構成と、トランク ピアに変換ルールを構成している場合 2 つのルールが競合する可能性がありますので。</span><span class="sxs-lookup"><span data-stu-id="8712d-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span> 
  
## <a name="example-translation-rules"></a><span data-ttu-id="8712d-115">変換ルールの例</span><span class="sxs-lookup"><span data-stu-id="8712d-115">Example Translation Rules</span></span>

<span data-ttu-id="8712d-116">以下の変換ルールの例では、トランク ピアについて E.164 形式からローカル形式に番号を変換するルールをサーバー上に作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8712d-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>
  
<span data-ttu-id="8712d-117">翻訳ルールを実装する方法の詳細については、展開に関するドキュメントの[変換ルールの定義](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8712d-117">For details about how to implement translation rules, see [Defining Translation Rules](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>
  
|<span data-ttu-id="8712d-118">**説明**</span><span class="sxs-lookup"><span data-stu-id="8712d-118">**Description**</span></span>|<span data-ttu-id="8712d-119">**開始桁の数字**</span><span class="sxs-lookup"><span data-stu-id="8712d-119">**Starting Digits**</span></span>|<span data-ttu-id="8712d-120">**長さ**</span><span class="sxs-lookup"><span data-stu-id="8712d-120">**Length**</span></span>|<span data-ttu-id="8712d-121">**桁を削除する**</span><span class="sxs-lookup"><span data-stu-id="8712d-121">**Digits to Remove**</span></span>|<span data-ttu-id="8712d-122">**数字を追加するには**</span><span class="sxs-lookup"><span data-stu-id="8712d-122">**Digits to Add**</span></span>|<span data-ttu-id="8712d-123">**パターンに一致します。**</span><span class="sxs-lookup"><span data-stu-id="8712d-123">**Matching Pattern**</span></span>|<span data-ttu-id="8712d-124">**変換**</span><span class="sxs-lookup"><span data-stu-id="8712d-124">**Translation**</span></span>|<span data-ttu-id="8712d-125">**例**</span><span class="sxs-lookup"><span data-stu-id="8712d-125">**Example**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8712d-126">米国内の従来の長距離電話ダイヤル</span><span class="sxs-lookup"><span data-stu-id="8712d-126">Conventional long-distance dialing in U.S.</span></span>  <br/> <span data-ttu-id="8712d-127">(取り除く、'+')</span><span class="sxs-lookup"><span data-stu-id="8712d-127">(strip out the '+')</span></span>  <br/> |<span data-ttu-id="8712d-128">+1</span><span class="sxs-lookup"><span data-stu-id="8712d-128">+1</span></span>  <br/> |<span data-ttu-id="8712d-129">ちょうど 12</span><span class="sxs-lookup"><span data-stu-id="8712d-129">Exactly 12</span></span>  <br/> |<span data-ttu-id="8712d-130">1</span><span class="sxs-lookup"><span data-stu-id="8712d-130">1</span></span>  <br/> |<span data-ttu-id="8712d-131">0</span><span class="sxs-lookup"><span data-stu-id="8712d-131">0</span></span>  <br/> |<span data-ttu-id="8712d-132">^\+(1\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="8712d-132">^\+(1\d{10})$</span></span>  <br/> |<span data-ttu-id="8712d-133">$1</span><span class="sxs-lookup"><span data-stu-id="8712d-133">$1</span></span>  <br/> |<span data-ttu-id="8712d-134">+14255551010 を 14255551010 に変換</span><span class="sxs-lookup"><span data-stu-id="8712d-134">+14255551010 becomes 14255551010</span></span>  <br/> |
|<span data-ttu-id="8712d-135">米国長距離国際電話ダイヤル</span><span class="sxs-lookup"><span data-stu-id="8712d-135">U.S. international long-distance dialing</span></span>  <br/> <span data-ttu-id="8712d-136">(取り除く '+' 011 を追加)</span><span class="sxs-lookup"><span data-stu-id="8712d-136">(strip out '+' and add 011)</span></span>  <br/> |+  <br/> |<span data-ttu-id="8712d-137">11 以上</span><span class="sxs-lookup"><span data-stu-id="8712d-137">At least 11</span></span>  <br/> |<span data-ttu-id="8712d-138">1</span><span class="sxs-lookup"><span data-stu-id="8712d-138">1</span></span>  <br/> |<span data-ttu-id="8712d-139">011</span><span class="sxs-lookup"><span data-stu-id="8712d-139">011</span></span>  <br/> |<span data-ttu-id="8712d-140">^\+(\d{9}\d+)$</span><span class="sxs-lookup"><span data-stu-id="8712d-140">^\+(\d{9}\d+)$</span></span>  <br/> |<span data-ttu-id="8712d-141">011$1</span><span class="sxs-lookup"><span data-stu-id="8712d-141">011$1</span></span>  <br/> |<span data-ttu-id="8712d-142">+441235551010 を 011441235551010 に変換</span><span class="sxs-lookup"><span data-stu-id="8712d-142">+441235551010 becomes 011441235551010</span></span>  <br/> |
   

