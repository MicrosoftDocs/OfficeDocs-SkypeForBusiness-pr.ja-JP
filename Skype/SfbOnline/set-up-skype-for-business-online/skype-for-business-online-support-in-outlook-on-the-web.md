---
title: Outlook on the web での Skype for Business Online のサポート
ms.author: tonysmit
author: tonysmit
manager: serdars
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
description: Office 365 の Outlook on the web (Outlook Web App) では、ナビゲーション バーから基本的な Skype for Business Web クライアントを利用できます。 このクライアントの基本的なユーザーが使用できるオンラインの管理者が Office 365 組織の修飾の URL を構成していません。 ユーザーのアカウントは、オンライン、修飾の URL を持っていない限りが表示されます、経験、組織はホーム設置は、一部のユーザー アカウントを持っている場合でも。 ユーザー アカウント、オンプレミス (かどうかがある修飾の URL か) があるか、または Microsoft によって管理されるユーザーは、Lync の経験、Outlook web app で表示されます。
ms.openlocfilehash: 03491bb0cb200cac8eecb0ae2282a7003a85f8dc
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2018
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="a047f-106">Outlook on the web での Skype for Business Online のサポート</span><span class="sxs-lookup"><span data-stu-id="a047f-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="a047f-107">Office 365 の Outlook on the web (Outlook Web App) では、ナビゲーション バーから基本的な Skype for Business Web クライアントを利用できます。</span><span class="sxs-lookup"><span data-stu-id="a047f-107">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="a047f-108">このクライアントの基本的なユーザーが使用できるオンラインの管理者が Office 365 組織の修飾の URL を構成していません。</span><span class="sxs-lookup"><span data-stu-id="a047f-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization.</span></span> <span data-ttu-id="a047f-109">ユーザーのアカウントは、オンライン、修飾の URL を持っていない限りが表示されます、経験、組織はホーム設置は、一部のユーザー アカウントを持っている場合でも。</span><span class="sxs-lookup"><span data-stu-id="a047f-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="a047f-110">ユーザー アカウント、オンプレミス (かどうかがある修飾の URL か) があるか、または Microsoft によって管理されるユーザーは、Lync の経験、Outlook web app で表示されます。</span><span class="sxs-lookup"><span data-stu-id="a047f-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="a047f-111">次の表では、する必要のある別の設定と使用されている web クライアントを使用しています。</span><span class="sxs-lookup"><span data-stu-id="a047f-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="a047f-112">**ユーザー アカウントの場所**</span><span class="sxs-lookup"><span data-stu-id="a047f-112">**User account is located**</span></span> <br/> |<span data-ttu-id="a047f-113">**バニティ URL が設定されているか、専用の組織がある**</span><span class="sxs-lookup"><span data-stu-id="a047f-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="a047f-114">**Skype for Business または Lync のエクスペリエンス**</span><span class="sxs-lookup"><span data-stu-id="a047f-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="a047f-115">オンライン</span><span class="sxs-lookup"><span data-stu-id="a047f-115">Online</span></span>  <br/> |<span data-ttu-id="a047f-116">なし</span><span class="sxs-lookup"><span data-stu-id="a047f-116">No</span></span>  <br/> |<span data-ttu-id="a047f-117">Skype for Business の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="a047f-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="a047f-118">オンライン</span><span class="sxs-lookup"><span data-stu-id="a047f-118">Online</span></span>  <br/> |<span data-ttu-id="a047f-119">はい</span><span class="sxs-lookup"><span data-stu-id="a047f-119">Yes</span></span>  <br/> |<span data-ttu-id="a047f-120">Lync の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="a047f-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="a047f-121">ハイブリッドでオンラインに存在する</span><span class="sxs-lookup"><span data-stu-id="a047f-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="a047f-122">なし</span><span class="sxs-lookup"><span data-stu-id="a047f-122">No</span></span>  <br/> |<span data-ttu-id="a047f-123">Skype for Business の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="a047f-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="a047f-124">ハイブリッドでオンラインに存在する</span><span class="sxs-lookup"><span data-stu-id="a047f-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="a047f-125">はい</span><span class="sxs-lookup"><span data-stu-id="a047f-125">Yes</span></span>  <br/> |<span data-ttu-id="a047f-126">Lync の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="a047f-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="a047f-127">ハイブリッドでオンプレミスに存在する</span><span class="sxs-lookup"><span data-stu-id="a047f-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="a047f-128">なし</span><span class="sxs-lookup"><span data-stu-id="a047f-128">No</span></span>  <br/> |<span data-ttu-id="a047f-129">Lync の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="a047f-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="a047f-130">ハイブリッドでオンプレミスに存在する</span><span class="sxs-lookup"><span data-stu-id="a047f-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="a047f-131">はい</span><span class="sxs-lookup"><span data-stu-id="a047f-131">Yes</span></span>  <br/> |<span data-ttu-id="a047f-132">Lync の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="a047f-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="a047f-133">Prem の純粋です</span><span class="sxs-lookup"><span data-stu-id="a047f-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="a047f-134">なし</span><span class="sxs-lookup"><span data-stu-id="a047f-134">No</span></span>  <br/> |<span data-ttu-id="a047f-135">Lync の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="a047f-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="a047f-136">Prem の純粋です</span><span class="sxs-lookup"><span data-stu-id="a047f-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="a047f-137">はい</span><span class="sxs-lookup"><span data-stu-id="a047f-137">Yes</span></span>  <br/> |<span data-ttu-id="a047f-138">Lync の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="a047f-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="a047f-139">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a047f-139">Related topics</span></span>
[<span data-ttu-id="a047f-140">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="a047f-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="a047f-141">Skype for Business ユーザーが Skype 連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="a047f-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 