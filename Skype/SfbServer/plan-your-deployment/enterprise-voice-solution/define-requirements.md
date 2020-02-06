---
title: Skype for Business Server での緊急通話の要件を定義する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: SIP トランク E9-1 サービスプロバイダと ELIN ゲートウェイのどちらを使用しているかに応じて、Skype for Business Server エンタープライズ Voip で E9-1-1 を有効にするために必要な手順について説明します。
ms.openlocfilehash: ffda7796390fea6c44d943770c9b4af6d299549a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803087"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="89606-103">Skype for Business Server での緊急通話の要件を定義する</span><span class="sxs-lookup"><span data-stu-id="89606-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="89606-104">SIP トランク E9-1 サービスプロバイダと ELIN ゲートウェイのどちらを使用しているかに応じて、Skype for Business Server エンタープライズ Voip で E9-1-1 を有効にするために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="89606-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="89606-105">Skype for Business Server E9 の展開を開始する前に、次のセクションで説明する質問に回答できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="89606-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="89606-106">必要な計画は、展開する E9-1-1 ソリューションの種類 (SIP トランク E9-1-1 サービス プロバイダー、または緊急位置識別番号 (ELIN) ゲートウェイ) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="89606-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="89606-107">次の表では、この計画ブック内で、各ソリューションを確認する必要があるセクションを示します。</span><span class="sxs-lookup"><span data-stu-id="89606-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="89606-108">**E9-1-1 ソリューションの種類別の計画手順**</span><span class="sxs-lookup"><span data-stu-id="89606-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="89606-109">**SIP トランク サービス プロバイダー**</span><span class="sxs-lookup"><span data-stu-id="89606-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="89606-110">**ELIN ゲートウェイ**</span><span class="sxs-lookup"><span data-stu-id="89606-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="89606-111">Skype for Business Server での E9 展開のスコープを定義する</span><span class="sxs-lookup"><span data-stu-id="89606-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="89606-112">Skype for Business Server での E9 展開のスコープを定義する</span><span class="sxs-lookup"><span data-stu-id="89606-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="89606-113">Skype for Business Server で場所を決定するために使用するネットワーク要素を定義する</span><span class="sxs-lookup"><span data-stu-id="89606-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="89606-114">Skype for Business Server で場所を決定するために使用するネットワーク要素を定義する</span><span class="sxs-lookup"><span data-stu-id="89606-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="89606-115">Skype for Business Server でユーザーの E9-1 を有効にする</span><span class="sxs-lookup"><span data-stu-id="89606-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="89606-116">Skype for Business Server でユーザーの E9-1 を有効にする</span><span class="sxs-lookup"><span data-stu-id="89606-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="89606-117">Skype for Business Server で SIP トランクサービスプロバイダーの場所を管理する</span><span class="sxs-lookup"><span data-stu-id="89606-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="89606-118">Skype for Business Server で ELIN ゲートウェイの場所を管理する</span><span class="sxs-lookup"><span data-stu-id="89606-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="89606-119">Skype for Business Server で場所を手動で取得するためのユーザーエクスペリエンスを定義する</span><span class="sxs-lookup"><span data-stu-id="89606-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="89606-120">Skype for Business Server で場所を手動で取得するためのユーザーエクスペリエンスを定義する</span><span class="sxs-lookup"><span data-stu-id="89606-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="89606-121">Skype for Business Server での E9-1 の SIP トランクの設計</span><span class="sxs-lookup"><span data-stu-id="89606-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="89606-122">Skype for Business Server にセキュリティデスクを追加する</span><span class="sxs-lookup"><span data-stu-id="89606-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="89606-123">Skype for Business Server にセキュリティデスクを追加する</span><span class="sxs-lookup"><span data-stu-id="89606-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="89606-124">Skype for Business Server の位置情報ポリシーを計画する</span><span class="sxs-lookup"><span data-stu-id="89606-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="89606-125">Skype for Business Server の E9-1-1 サービス プロバイダーの選択</span><span class="sxs-lookup"><span data-stu-id="89606-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="89606-126">Skype for Business Server で位置情報ポリシーのスコープを割り当てる</span><span class="sxs-lookup"><span data-stu-id="89606-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="89606-127">Skype for Business Server の位置情報ポリシーを計画する</span><span class="sxs-lookup"><span data-stu-id="89606-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="89606-128">Skype for Business Server で位置情報ポリシーのスコープを割り当てる</span><span class="sxs-lookup"><span data-stu-id="89606-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   

