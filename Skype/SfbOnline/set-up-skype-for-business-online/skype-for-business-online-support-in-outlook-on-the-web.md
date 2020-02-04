---
title: Outlook on the web での Skype for Business Online のサポート
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 305984ec-3da8-4509-bb2b-6643dcf2cb7d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Office 365 の Outlook on the web (Outlook Web App) では、ナビゲーション バーから基本的な Skype for Business Web クライアントを利用できます。 この基本クライアントは、管理者が Office 365 組織のバニティ URL を構成していないオンラインユーザーに対して利用できます。 ユーザーのアカウントがオンラインであり、バニティの URL がない限り、組織のユーザーアカウントにオンプレミスのユーザーアカウントがある場合でも、エクスペリエンスは依然として表示されます。 オンプレミスの (バニティ URL を使用しているかどうかにかかわらず) ユーザーアカウントを持っているユーザー、または Microsoft によって管理されているユーザーには、Outlook web app で Lync エクスペリエンスが表示されます。
ms.openlocfilehash: 7eab3ce7c8d6ea8c1f004559ea92f64f554fb010
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692852"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="865f2-106">Outlook on the web での Skype for Business Online のサポート</span><span class="sxs-lookup"><span data-stu-id="865f2-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="865f2-107">Office 365 の Outlook on the web (Outlook Web App) では、ナビゲーション バーから基本的な Skype for Business Web クライアントを利用できます。</span><span class="sxs-lookup"><span data-stu-id="865f2-107">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="865f2-108">この基本クライアントは、管理者が Office 365 組織のバニティ URL を構成していないオンラインユーザーに対して利用できます。</span><span class="sxs-lookup"><span data-stu-id="865f2-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization.</span></span> <span data-ttu-id="865f2-109">ユーザーのアカウントがオンラインであり、バニティの URL がない限り、組織のユーザーアカウントにオンプレミスのユーザーアカウントがある場合でも、エクスペリエンスは依然として表示されます。</span><span class="sxs-lookup"><span data-stu-id="865f2-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="865f2-110">オンプレミスの (バニティ URL を使用しているかどうかにかかわらず) ユーザーアカウントを持っているユーザー、または Microsoft によって管理されているユーザーには、Outlook web app で Lync エクスペリエンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="865f2-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="865f2-111">次の表は、使用する可能性がある設定と、使用されている web クライアントの種類をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="865f2-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="865f2-112">**ユーザー アカウントの場所**</span><span class="sxs-lookup"><span data-stu-id="865f2-112">**User account is located**</span></span> <br/> |<span data-ttu-id="865f2-113">**バニティ URL が設定されているか、専用の組織がある**</span><span class="sxs-lookup"><span data-stu-id="865f2-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="865f2-114">**Skype for Business または Lync のエクスペリエンス**</span><span class="sxs-lookup"><span data-stu-id="865f2-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="865f2-115">オンライン</span><span class="sxs-lookup"><span data-stu-id="865f2-115">Online</span></span>  <br/> |<span data-ttu-id="865f2-116">いいえ</span><span class="sxs-lookup"><span data-stu-id="865f2-116">No</span></span>  <br/> |<span data-ttu-id="865f2-117">Skype for Business の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="865f2-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="865f2-118">オンライン</span><span class="sxs-lookup"><span data-stu-id="865f2-118">Online</span></span>  <br/> |<span data-ttu-id="865f2-119">はい</span><span class="sxs-lookup"><span data-stu-id="865f2-119">Yes</span></span>  <br/> |<span data-ttu-id="865f2-120">Lync の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="865f2-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="865f2-121">ハイブリッドでオンラインに存在する</span><span class="sxs-lookup"><span data-stu-id="865f2-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="865f2-122">いいえ</span><span class="sxs-lookup"><span data-stu-id="865f2-122">No</span></span>  <br/> |<span data-ttu-id="865f2-123">Skype for Business の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="865f2-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="865f2-124">ハイブリッドでオンラインに存在する</span><span class="sxs-lookup"><span data-stu-id="865f2-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="865f2-125">はい</span><span class="sxs-lookup"><span data-stu-id="865f2-125">Yes</span></span>  <br/> |<span data-ttu-id="865f2-126">Lync の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="865f2-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="865f2-127">ハイブリッドでオンプレミスに存在する</span><span class="sxs-lookup"><span data-stu-id="865f2-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="865f2-128">なし</span><span class="sxs-lookup"><span data-stu-id="865f2-128">No</span></span>  <br/> |<span data-ttu-id="865f2-129">Lync の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="865f2-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="865f2-130">ハイブリッドでオンプレミスに存在する</span><span class="sxs-lookup"><span data-stu-id="865f2-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="865f2-131">はい</span><span class="sxs-lookup"><span data-stu-id="865f2-131">Yes</span></span>  <br/> |<span data-ttu-id="865f2-132">Lync の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="865f2-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="865f2-133">ピュアオンプレミス</span><span class="sxs-lookup"><span data-stu-id="865f2-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="865f2-134">なし</span><span class="sxs-lookup"><span data-stu-id="865f2-134">No</span></span>  <br/> |<span data-ttu-id="865f2-135">Lync の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="865f2-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="865f2-136">ピュアオンプレミス</span><span class="sxs-lookup"><span data-stu-id="865f2-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="865f2-137">はい</span><span class="sxs-lookup"><span data-stu-id="865f2-137">Yes</span></span>  <br/> |<span data-ttu-id="865f2-138">Lync の Web エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="865f2-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="865f2-139">関連トピック</span><span class="sxs-lookup"><span data-stu-id="865f2-139">Related topics</span></span>
[<span data-ttu-id="865f2-140">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="865f2-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="865f2-141">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="865f2-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
