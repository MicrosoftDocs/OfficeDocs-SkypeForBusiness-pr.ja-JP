---
title: Skype for Business Server 2015 での緊急電話の要件の定義
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: ビジネス サーバーのエンタープライズ VoIP の SIP トランク ~ 9-1-1 のサービス プロバイダーまたは ELIN ゲートウェイを使用するかどうかによって Skype で ~ 9-1-1 を有効にするために必要な手順をまとめたものです。
ms.openlocfilehash: 69f6f9189db9293e0c171072db4a6a6fcf7a935c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server-2015"></a><span data-ttu-id="25ce7-103">Skype for Business Server 2015 での緊急電話の要件の定義</span><span class="sxs-lookup"><span data-stu-id="25ce7-103">Define your requirements for emergency calls in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="25ce7-104">ビジネス サーバーのエンタープライズ VoIP の SIP トランク ~ 9-1-1 のサービス プロバイダーまたは ELIN ゲートウェイを使用するかどうかによって Skype で ~ 9-1-1 を有効にするために必要な手順をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="25ce7-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="25ce7-105">Skype ビジネス サーバー ~ 9-1-1 の展開を開始する前にする必要があります最初できる次のセクションで詳細な質問に回答します。</span><span class="sxs-lookup"><span data-stu-id="25ce7-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="25ce7-106">必要な計画は、展開する E9-1-1 ソリューションの種類 (SIP トランク E9-1-1 サービス プロバイダー、または緊急位置識別番号 (ELIN) ゲートウェイ) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="25ce7-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="25ce7-107">次の表は、これらのソリューションごとに確認する必要がありますこの計画ブック内のセクションを識別します。</span><span class="sxs-lookup"><span data-stu-id="25ce7-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="25ce7-108">**~ 9-1-1 ソリューションの種類によって、計画の手順**</span><span class="sxs-lookup"><span data-stu-id="25ce7-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="25ce7-109">**SIP トランク サービス プロバイダー**</span><span class="sxs-lookup"><span data-stu-id="25ce7-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="25ce7-110">**ELIN ゲートウェイ**</span><span class="sxs-lookup"><span data-stu-id="25ce7-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="25ce7-111">Skype でのビジネス サーバー 2015 ~ 9-1-1 の展開の範囲を定義します。</span><span class="sxs-lookup"><span data-stu-id="25ce7-111">Define the scope of the E9-1-1 deployment in Skype for Business Server 2015</span></span>](scope.md) <br/> |[<span data-ttu-id="25ce7-112">Skype でのビジネス サーバー 2015 ~ 9-1-1 の展開の範囲を定義します。</span><span class="sxs-lookup"><span data-stu-id="25ce7-112">Define the scope of the E9-1-1 deployment in Skype for Business Server 2015</span></span>](scope.md) <br/> |
|[<span data-ttu-id="25ce7-113">ビジネス サーバー 2015 の Skype での場所を決定するために使用するネットワーク要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="25ce7-113">Define the network elements used to determine location in Skype for Business Server 2015</span></span>](network-location.md) <br/> |[<span data-ttu-id="25ce7-114">ビジネス サーバー 2015 の Skype での場所を決定するために使用するネットワーク要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="25ce7-114">Define the network elements used to determine location in Skype for Business Server 2015</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="25ce7-115">ビジネス サーバー 2015 の Skype で ~ 9-1-1 のユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="25ce7-115">Enable users for E9-1-1 in Skype for Business Server 2015</span></span>](enable-users.md) <br/> |[<span data-ttu-id="25ce7-116">ビジネス サーバー 2015 の Skype で ~ 9-1-1 のユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="25ce7-116">Enable users for E9-1-1 in Skype for Business Server 2015</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="25ce7-117">ビジネス サーバー 2015 の Skype では、SIP トランク サービス プロバイダーの場所を管理します。</span><span class="sxs-lookup"><span data-stu-id="25ce7-117">Manage locations for SIP trunk service providers in Skype for Business Server 2015</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="25ce7-118">ビジネス サーバー 2015 の Skype の ELIN ゲートウェイの場所を管理します。</span><span class="sxs-lookup"><span data-stu-id="25ce7-118">Manage locations for ELIN gateways in Skype for Business Server 2015</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="25ce7-119">ビジネス サーバー 2015 の Skype 内の場所を手動で取得するためのユーザー エクスペリエンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="25ce7-119">Define the user experience for manually acquiring a location in Skype for Business Server 2015</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="25ce7-120">ビジネス サーバー 2015 の Skype 内の場所を手動で取得するためのユーザー エクスペリエンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="25ce7-120">Define the user experience for manually acquiring a location in Skype for Business Server 2015</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="25ce7-121">~ 9-1-1 では、Skype のビジネス サーバー 2015 の SIP トランクを設計します。</span><span class="sxs-lookup"><span data-stu-id="25ce7-121">Design the SIP trunk for E9-1-1 in Skype for Business Server 2015</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="25ce7-122">ビジネス サーバー 2015 の Skype のセキュリティ デスクが含まれます</span><span class="sxs-lookup"><span data-stu-id="25ce7-122">Include the security desk in Skype for Business Server 2015</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="25ce7-123">ビジネス サーバー 2015 の Skype のセキュリティ デスクが含まれます</span><span class="sxs-lookup"><span data-stu-id="25ce7-123">Include the security desk in Skype for Business Server 2015</span></span>](security-desk.md) <br/> |[<span data-ttu-id="25ce7-124">Skype のビジネス サーバー 2015 の場所のポリシーを計画します。</span><span class="sxs-lookup"><span data-stu-id="25ce7-124">Plan location policies for Skype for Business Server 2015</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="25ce7-125">ビジネス サーバー 2015 の Skype の ~ 9-1-1 サービス プロバイダーを選ぶ</span><span class="sxs-lookup"><span data-stu-id="25ce7-125">Choose an E9-1-1 service provider for Skype for Business Server 2015</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="25ce7-126">ビジネス サーバー 2015 の Skype での場所のポリシーのスコープを割り当てる</span><span class="sxs-lookup"><span data-stu-id="25ce7-126">Assign location policy scope in Skype for Business Server 2015</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="25ce7-127">Skype のビジネス サーバー 2015 の場所のポリシーを計画します。</span><span class="sxs-lookup"><span data-stu-id="25ce7-127">Plan location policies for Skype for Business Server 2015</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="25ce7-128">ビジネス サーバー 2015 の Skype での場所のポリシーのスコープを割り当てる</span><span class="sxs-lookup"><span data-stu-id="25ce7-128">Assign location policy scope in Skype for Business Server 2015</span></span>](location-policy-scope.md) <br/> ||
   

