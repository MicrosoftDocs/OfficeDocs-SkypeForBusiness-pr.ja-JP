---
title: "Outlook on the web での Skype for Business Online のサポート"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 305984ec-3da8-4509-bb2b-6643dcf2cb7d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Outlook を Office 365 に (Outlook Web App) では、ナビゲーション ・ バーから web クライアントのビジネスの基本的な Skype を提供します。 このクライアントの基本的なユーザーが使用できるオンラインの管理者が Office 365 組織の修飾の URL を構成していません。 ユーザーのアカウントは、オンライン、修飾の URL を持っていない限りが表示されます、経験、組織はホーム設置は、一部のユーザー アカウントを持っている場合でも。 ユーザー アカウント、オンプレミス (かどうかがある修飾の URL か) があるか、または Microsoft によって管理されるユーザーは、Lync の経験、Outlook web app で表示されます。"
ms.openlocfilehash: 8688123f0e19a648dae7706dc346a647ecd99211
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="014d8-106">Outlook on the web での Skype for Business Online のサポート</span><span class="sxs-lookup"><span data-stu-id="014d8-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="014d8-107">Outlook を Office 365 に (Outlook Web App) では、ナビゲーション ・ バーから web クライアントのビジネスの基本的な Skype を提供します。</span><span class="sxs-lookup"><span data-stu-id="014d8-107">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="014d8-108">このクライアントの基本的なユーザーが使用できるオンラインの管理者が Office 365 組織の修飾の URL を構成していません。</span><span class="sxs-lookup"><span data-stu-id="014d8-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization.</span></span> <span data-ttu-id="014d8-109">ユーザーのアカウントは、オンライン、修飾の URL を持っていない限りが表示されます、経験、組織はホーム設置は、一部のユーザー アカウントを持っている場合でも。</span><span class="sxs-lookup"><span data-stu-id="014d8-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="014d8-110">ユーザー アカウント、オンプレミス (かどうかがある修飾の URL か) があるか、または Microsoft によって管理されるユーザーは、Lync の経験、Outlook web app で表示されます。</span><span class="sxs-lookup"><span data-stu-id="014d8-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="014d8-111">次の表では、する必要のある別の設定と使用されている web クライアントを使用しています。</span><span class="sxs-lookup"><span data-stu-id="014d8-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="014d8-112">**ユーザー アカウントの場所**</span><span class="sxs-lookup"><span data-stu-id="014d8-112">**User account is located**</span></span> <br/> |<span data-ttu-id="014d8-113">**バニティ URL が設定されているか、専用の組織がある**</span><span class="sxs-lookup"><span data-stu-id="014d8-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="014d8-114">**Skype for Business または Lync のエクスペリエンス**</span><span class="sxs-lookup"><span data-stu-id="014d8-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="014d8-115">オンライン</span><span class="sxs-lookup"><span data-stu-id="014d8-115">Online</span></span>  <br/> |<span data-ttu-id="014d8-116">なし</span><span class="sxs-lookup"><span data-stu-id="014d8-116">No</span></span>  <br/> |<span data-ttu-id="014d8-117">Skype for Business の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="014d8-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="014d8-118">オンライン</span><span class="sxs-lookup"><span data-stu-id="014d8-118">Online</span></span>  <br/> |<span data-ttu-id="014d8-119">はい</span><span class="sxs-lookup"><span data-stu-id="014d8-119">Yes</span></span>  <br/> |<span data-ttu-id="014d8-120">Lync の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="014d8-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="014d8-121">ハイブリッドでオンラインに存在する</span><span class="sxs-lookup"><span data-stu-id="014d8-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="014d8-122">なし</span><span class="sxs-lookup"><span data-stu-id="014d8-122">No</span></span>  <br/> |<span data-ttu-id="014d8-123">Skype for Business の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="014d8-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="014d8-124">ハイブリッドでオンラインに存在する</span><span class="sxs-lookup"><span data-stu-id="014d8-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="014d8-125">はい</span><span class="sxs-lookup"><span data-stu-id="014d8-125">Yes</span></span>  <br/> |<span data-ttu-id="014d8-126">Lync の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="014d8-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="014d8-127">ハイブリッドでオンプレミスに存在する</span><span class="sxs-lookup"><span data-stu-id="014d8-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="014d8-128">なし</span><span class="sxs-lookup"><span data-stu-id="014d8-128">No</span></span>  <br/> |<span data-ttu-id="014d8-129">Lync の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="014d8-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="014d8-130">ハイブリッドでオンプレミスに存在する</span><span class="sxs-lookup"><span data-stu-id="014d8-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="014d8-131">はい</span><span class="sxs-lookup"><span data-stu-id="014d8-131">Yes</span></span>  <br/> |<span data-ttu-id="014d8-132">Lync の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="014d8-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="014d8-133">Prem の純粋です</span><span class="sxs-lookup"><span data-stu-id="014d8-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="014d8-134">なし</span><span class="sxs-lookup"><span data-stu-id="014d8-134">No</span></span>  <br/> |<span data-ttu-id="014d8-135">Lync の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="014d8-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="014d8-136">Prem の純粋です</span><span class="sxs-lookup"><span data-stu-id="014d8-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="014d8-137">はい</span><span class="sxs-lookup"><span data-stu-id="014d8-137">Yes</span></span>  <br/> |<span data-ttu-id="014d8-138">Lync の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="014d8-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="014d8-139">関連トピック</span><span class="sxs-lookup"><span data-stu-id="014d8-139">Related topics</span></span>
[<span data-ttu-id="014d8-140">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="014d8-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="014d8-141">Skype 連絡先を追加、ビジネス ・ ユーザーの Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="014d8-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)