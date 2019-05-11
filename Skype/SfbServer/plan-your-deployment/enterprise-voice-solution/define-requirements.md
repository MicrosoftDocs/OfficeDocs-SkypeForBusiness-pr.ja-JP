---
title: Skype のビジネス サーバーの緊急通報の要件を定義します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: ビジネス サーバーのエンタープライズ VoIP の SIP トランク ~ 9-1-1 のサービス プロバイダーまたは ELIN ゲートウェイを使用するかどうかによって Skype で ~ 9-1-1 を有効にするために必要な手順をまとめたものです。
ms.openlocfilehash: f7a7d34339cb16851705712ef7911194cde1b9f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33925160"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="8cf31-103">Skype のビジネス サーバーの緊急通報の要件を定義します。</span><span class="sxs-lookup"><span data-stu-id="8cf31-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="8cf31-104">ビジネス サーバーのエンタープライズ VoIP の SIP トランク ~ 9-1-1 のサービス プロバイダーまたは ELIN ゲートウェイを使用するかどうかによって Skype で ~ 9-1-1 を有効にするために必要な手順をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="8cf31-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="8cf31-105">Skype ビジネス サーバー ~ 9-1-1 の展開を開始する前にする必要があります最初できる次のセクションで詳細な質問に回答します。</span><span class="sxs-lookup"><span data-stu-id="8cf31-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="8cf31-106">必要な計画は、展開する E9-1-1 ソリューションの種類 (SIP トランク E9-1-1 サービス プロバイダー、または緊急位置識別番号 (ELIN) ゲートウェイ) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="8cf31-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="8cf31-107">次の表は、これらのソリューションごとに確認する必要がありますこの計画ブック内のセクションを識別します。</span><span class="sxs-lookup"><span data-stu-id="8cf31-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="8cf31-108">**E9-1-1 ソリューションの種類別の計画手順**</span><span class="sxs-lookup"><span data-stu-id="8cf31-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="8cf31-109">**SIP トランク サービス プロバイダー**</span><span class="sxs-lookup"><span data-stu-id="8cf31-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="8cf31-110">**ELIN ゲートウェイ**</span><span class="sxs-lookup"><span data-stu-id="8cf31-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="8cf31-111">Skype のビジネス サーバーの ~ 9-1-1 の展開の範囲を定義します。</span><span class="sxs-lookup"><span data-stu-id="8cf31-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="8cf31-112">Skype のビジネス サーバーの ~ 9-1-1 の展開の範囲を定義します。</span><span class="sxs-lookup"><span data-stu-id="8cf31-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="8cf31-113">Skype ビジネス サーバーの場所を決定するためのネットワーク要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="8cf31-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="8cf31-114">Skype ビジネス サーバーの場所を決定するためのネットワーク要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="8cf31-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="8cf31-115">~ 9-1-1 では、Skype のビジネス サーバーに対してユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8cf31-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="8cf31-116">~ 9-1-1 では、Skype のビジネス サーバーに対してユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8cf31-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="8cf31-117">ビジネス サーバーの Skype では、SIP トランク サービス プロバイダーの場所を管理します。</span><span class="sxs-lookup"><span data-stu-id="8cf31-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="8cf31-118">ビジネス サーバーの Skype の ELIN ゲートウェイの場所を管理します。</span><span class="sxs-lookup"><span data-stu-id="8cf31-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="8cf31-119">ビジネス サーバーの Skype 内の場所を手動で取得するためのユーザー エクスペリエンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="8cf31-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="8cf31-120">ビジネス サーバーの Skype 内の場所を手動で取得するためのユーザー エクスペリエンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="8cf31-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="8cf31-121">~ 9-1-1 では、Skype のビジネス サーバーの SIP トランクを設計します。</span><span class="sxs-lookup"><span data-stu-id="8cf31-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="8cf31-122">Skype のビジネス サーバーのセキュリティ デスクが含まれます</span><span class="sxs-lookup"><span data-stu-id="8cf31-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="8cf31-123">Skype のビジネス サーバーのセキュリティ デスクが含まれます</span><span class="sxs-lookup"><span data-stu-id="8cf31-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="8cf31-124">Skype のビジネスのサーバーの場所のポリシーを計画します。</span><span class="sxs-lookup"><span data-stu-id="8cf31-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="8cf31-125">Skype for Business Server の E9-1-1 サービス プロバイダーの選択</span><span class="sxs-lookup"><span data-stu-id="8cf31-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="8cf31-126">ビジネスのサーバーの場所ポリシーのスコープでは、Skype を割り当てる</span><span class="sxs-lookup"><span data-stu-id="8cf31-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="8cf31-127">Skype のビジネスのサーバーの場所のポリシーを計画します。</span><span class="sxs-lookup"><span data-stu-id="8cf31-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="8cf31-128">ビジネスのサーバーの場所ポリシーのスコープでは、Skype を割り当てる</span><span class="sxs-lookup"><span data-stu-id="8cf31-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   

