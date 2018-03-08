---
title: "Skype for Business Online のサポート web 版 Outlook で"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 305984ec-3da8-4509-bb2b-6643dcf2cb7d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "Office 365 で (Outlook Web App) web 版 outlook では、ナビゲーション バーで基本的な Skype for Business web クライアントを提供します。この基本的なクライアントを管理者には、Office 365 の組織の修飾 URL が構成されているが変わっていないオンラインのユーザーは利用できません。ユーザーのアカウントがオンラインで、修飾 URL がない限り場合でも、自分の組織がある一部のユーザー アカウントをオンプレミスでホームが、エクスペリエンスも表示されます。ユーザー アカウント オンプレミス (かどうかがある修飾 URL かどうか) またはマイクロソフトが管理しているユーザーには、Outlook web app で Lync エクスペリエンスが表示されます。"
ms.openlocfilehash: 38502f19a1204ac18a372367cb1ec24dd422207f
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="899a5-106">Skype for Business Online のサポート web 版 Outlook で</span><span class="sxs-lookup"><span data-stu-id="899a5-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="899a5-p102">Office 365 で (Outlook Web App) web 版 outlook では、ナビゲーション バーで基本的な Skype for Business web クライアントを提供します。この基本的なクライアントを管理者には、Office 365 の組織の修飾 URL が構成されているが変わっていないオンラインのユーザーは利用できません。ユーザーのアカウントがオンラインで、修飾 URL がない限り場合でも、自分の組織がある一部のユーザー アカウントをオンプレミスでホームが、エクスペリエンスも表示されます。ユーザー アカウント オンプレミス (かどうかがある修飾 URL かどうか) またはマイクロソフトが管理しているユーザーには、Outlook web app で Lync エクスペリエンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="899a5-p102">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar. This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization. As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises. Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="899a5-111">次の表は、所有している別の設定と使用されている web クライアントを示します。</span><span class="sxs-lookup"><span data-stu-id="899a5-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="899a5-112">**ユーザー アカウントがあります。**</span><span class="sxs-lookup"><span data-stu-id="899a5-112">**User account is located**</span></span> <br/> |<span data-ttu-id="899a5-113">**修飾 URL が構成されているか、専用の組織**</span><span class="sxs-lookup"><span data-stu-id="899a5-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="899a5-114">**Skype for Business または Lync のエクスペリエンスにはよいですか。**</span><span class="sxs-lookup"><span data-stu-id="899a5-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="899a5-115">オンライン</span><span class="sxs-lookup"><span data-stu-id="899a5-115">Online</span></span>  <br/> |<span data-ttu-id="899a5-116">×</span><span class="sxs-lookup"><span data-stu-id="899a5-116">No</span></span>  <br/> |<span data-ttu-id="899a5-117">Skype for Business web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="899a5-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="899a5-118">オンライン</span><span class="sxs-lookup"><span data-stu-id="899a5-118">Online</span></span>  <br/> |<span data-ttu-id="899a5-119">○</span><span class="sxs-lookup"><span data-stu-id="899a5-119">Yes</span></span>  <br/> |<span data-ttu-id="899a5-120">Lync web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="899a5-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="899a5-121">ハイブリッドは、オンライン ホーム</span><span class="sxs-lookup"><span data-stu-id="899a5-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="899a5-122">×</span><span class="sxs-lookup"><span data-stu-id="899a5-122">No</span></span>  <br/> |<span data-ttu-id="899a5-123">Skype for Business web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="899a5-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="899a5-124">ハイブリッドは、オンライン ホーム</span><span class="sxs-lookup"><span data-stu-id="899a5-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="899a5-125">○</span><span class="sxs-lookup"><span data-stu-id="899a5-125">Yes</span></span>  <br/> |<span data-ttu-id="899a5-126">Lync web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="899a5-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="899a5-127">ハイブリッド prem が置かれています。</span><span class="sxs-lookup"><span data-stu-id="899a5-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="899a5-128">×</span><span class="sxs-lookup"><span data-stu-id="899a5-128">No</span></span>  <br/> |<span data-ttu-id="899a5-129">Lync web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="899a5-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="899a5-130">ハイブリッド prem が置かれています。</span><span class="sxs-lookup"><span data-stu-id="899a5-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="899a5-131">○</span><span class="sxs-lookup"><span data-stu-id="899a5-131">Yes</span></span>  <br/> |<span data-ttu-id="899a5-132">Lync web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="899a5-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="899a5-133">単純に prem</span><span class="sxs-lookup"><span data-stu-id="899a5-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="899a5-134">×</span><span class="sxs-lookup"><span data-stu-id="899a5-134">No</span></span>  <br/> |<span data-ttu-id="899a5-135">Lync web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="899a5-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="899a5-136">単純に prem</span><span class="sxs-lookup"><span data-stu-id="899a5-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="899a5-137">○</span><span class="sxs-lookup"><span data-stu-id="899a5-137">Yes</span></span>  <br/> |<span data-ttu-id="899a5-138">Lync web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="899a5-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="899a5-139">関連トピック</span><span class="sxs-lookup"><span data-stu-id="899a5-139">Related topics</span></span>
[<span data-ttu-id="899a5-140">Skype for Business Online をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="899a5-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="899a5-141">ビジネス ユーザー向けの Skype Skype の連絡先を追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="899a5-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)