---
title: Skype のビジネス サーバーの緊急通報の要件を定義します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: ビジネス サーバーのエンタープライズ VoIP の SIP トランク ~ 9-1-1 のサービス プロバイダーまたは ELIN ゲートウェイを使用するかどうかによって Skype で ~ 9-1-1 を有効にするために必要な手順をまとめたものです。
ms.openlocfilehash: 6e61a21f77f9ed099e48b10c06e7afd0bde434df
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20979104"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="69f1a-103">Skype のビジネス サーバーの緊急通報の要件を定義します。</span><span class="sxs-lookup"><span data-stu-id="69f1a-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="69f1a-104">ビジネス サーバーのエンタープライズ VoIP の SIP トランク ~ 9-1-1 のサービス プロバイダーまたは ELIN ゲートウェイを使用するかどうかによって Skype で ~ 9-1-1 を有効にするために必要な手順をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="69f1a-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="69f1a-105">Skype ビジネス サーバー ~ 9-1-1 の展開を開始する前にする必要があります最初できる次のセクションで詳細な質問に回答します。</span><span class="sxs-lookup"><span data-stu-id="69f1a-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="69f1a-106">必要な計画は、展開する E9-1-1 ソリューションの種類 (SIP トランク E9-1-1 サービス プロバイダー、または緊急位置識別番号 (ELIN) ゲートウェイ) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="69f1a-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="69f1a-107">次の表は、これらのソリューションごとに確認する必要がありますこの計画ブック内のセクションを識別します。</span><span class="sxs-lookup"><span data-stu-id="69f1a-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="69f1a-108">**E9-1-1 ソリューションの種類別の計画手順**</span><span class="sxs-lookup"><span data-stu-id="69f1a-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="69f1a-109">**SIP トランク サービス プロバイダー**</span><span class="sxs-lookup"><span data-stu-id="69f1a-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="69f1a-110">**ELIN ゲートウェイ**</span><span class="sxs-lookup"><span data-stu-id="69f1a-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="69f1a-111">Skype のビジネス サーバーの ~ 9-1-1 の展開の範囲を定義します。</span><span class="sxs-lookup"><span data-stu-id="69f1a-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="69f1a-112">Skype のビジネス サーバーの ~ 9-1-1 の展開の範囲を定義します。</span><span class="sxs-lookup"><span data-stu-id="69f1a-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="69f1a-113">Skype ビジネス サーバーの場所を決定するためのネットワーク要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="69f1a-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="69f1a-114">Skype ビジネス サーバーの場所を決定するためのネットワーク要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="69f1a-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="69f1a-115">~ 9-1-1 では、Skype のビジネス サーバーに対してユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="69f1a-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="69f1a-116">~ 9-1-1 では、Skype のビジネス サーバーに対してユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="69f1a-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="69f1a-117">ビジネス サーバーの Skype では、SIP トランク サービス プロバイダーの場所を管理します。</span><span class="sxs-lookup"><span data-stu-id="69f1a-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="69f1a-118">ビジネス サーバーの Skype の ELIN ゲートウェイの場所を管理します。</span><span class="sxs-lookup"><span data-stu-id="69f1a-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="69f1a-119">ビジネス サーバーの Skype 内の場所を手動で取得するためのユーザー エクスペリエンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="69f1a-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="69f1a-120">ビジネス サーバーの Skype 内の場所を手動で取得するためのユーザー エクスペリエンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="69f1a-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="69f1a-121">~ 9-1-1 では、Skype のビジネス サーバーの SIP トランクを設計します。</span><span class="sxs-lookup"><span data-stu-id="69f1a-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="69f1a-122">Skype のビジネス サーバーのセキュリティ デスクが含まれます</span><span class="sxs-lookup"><span data-stu-id="69f1a-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="69f1a-123">Skype のビジネス サーバーのセキュリティ デスクが含まれます</span><span class="sxs-lookup"><span data-stu-id="69f1a-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="69f1a-124">Skype のビジネスのサーバーの場所のポリシーを計画します。</span><span class="sxs-lookup"><span data-stu-id="69f1a-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="69f1a-125">ビジネス サーバーの Skype の ~ 9-1-1 サービス プロバイダーを選ぶ</span><span class="sxs-lookup"><span data-stu-id="69f1a-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="69f1a-126">ビジネスのサーバーの場所ポリシーのスコープでは、Skype を割り当てる</span><span class="sxs-lookup"><span data-stu-id="69f1a-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="69f1a-127">Skype のビジネスのサーバーの場所のポリシーを計画します。</span><span class="sxs-lookup"><span data-stu-id="69f1a-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="69f1a-128">ビジネスのサーバーの場所ポリシーのスコープでは、Skype を割り当てる</span><span class="sxs-lookup"><span data-stu-id="69f1a-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   

