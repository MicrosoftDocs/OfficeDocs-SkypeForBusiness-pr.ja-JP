---
title: 今すぐ Skype for Business Online 管理センターを使用できないのはなぜですか?
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c182d564-1674-4491-b1d9-3e0cb657d4cc
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- Setup
- ms.lync.lac.TenantInMigration
description: 'Skype for Business 管理センターで使用できる機能とできない機能、およびサービスが別の Microsoft データセンターに移行される場合のその他の機能について説明します。 '
ms.openlocfilehash: 7258467929663c42bfb6088202511a04613db383
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164496"
---
# <a name="why-cant-i-use-the-skype-for-business-online-admin-center-right-now"></a><span data-ttu-id="7017d-103">今すぐ Skype for Business Online 管理センターを使用できないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="7017d-103">Why can't I use the Skype for Business Online admin center right now?</span></span>

<span data-ttu-id="7017d-104">作業を完了できないことがわかっているため、ここでは何が起こっているのかを説明します。</span><span class="sxs-lookup"><span data-stu-id="7017d-104">We know it's frustrating when you can't get your work done, so we're going to explain what's happening here and why it'll be worth the wait.</span></span> 
  
<span data-ttu-id="7017d-105">まず、次の技術的な説明について説明します。</span><span class="sxs-lookup"><span data-stu-id="7017d-105">First, here's the technical explanation:</span></span>
  
<span data-ttu-id="7017d-106">Skype for Business Online サービス (ユーザーと組織の設定) を別の Microsoft データセンターに移行しています。</span><span class="sxs-lookup"><span data-stu-id="7017d-106">We're migrating your Skype for Business Online service (meaning your users and organizational settings) to another Microsoft datacenter that's closer to you.</span></span> <span data-ttu-id="7017d-107">これにより、サービスが向上し、待機時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="7017d-107">This will improve your service and reduce latency.</span></span> 
  
<span data-ttu-id="7017d-108">技術的な詳細については、「[データの移動中および移行後]( https://go.microsoft.com/fwlink/?LinkId=526418)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7017d-108">For more technical details, see [During and after your data move]( https://go.microsoft.com/fwlink/?LinkId=526418).</span></span>
  
## <a name="ok-so-what-does-that-mean"></a><span data-ttu-id="7017d-109">これはどういう意味ですか?</span><span class="sxs-lookup"><span data-stu-id="7017d-109">OK, so what does that mean?</span></span>

<span data-ttu-id="7017d-110">まず、いくつかの用語について説明します。</span><span class="sxs-lookup"><span data-stu-id="7017d-110">First, let's break down a few terms.</span></span>
  
- <span data-ttu-id="7017d-111">**データセンター**これは、ファイルやメールメッセージなど、Microsoft 365 または Office 365 からの情報が保存されている物理的な場所です。</span><span class="sxs-lookup"><span data-stu-id="7017d-111">**Data center** This is the physical location where the information from your Microsoft 365 or Office 365 is stored, such as your files and email messages.</span></span> <span data-ttu-id="7017d-112">Microsoft 365 と Office 365 のデータセンターについて詳しく調べたい場合は、こちらの[記事](https://www.microsoft.com/online/legal/v2/?docid=25)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7017d-112">If you really want to dig in to what Microsoft 365 and Office 365 datacenters are, check out[this article](https://www.microsoft.com/online/legal/v2/?docid=25).</span></span>
    
- <span data-ttu-id="7017d-113">**移行**これは、"移動" とほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="7017d-113">**Migrating** This is pretty much the same as "moving."</span></span> <span data-ttu-id="7017d-114">この場合、お客様の Skype for Business Online のユーザーと設定を、あるデータセンターから別のデータセンターに移動し、サービスの向上に向けてより近いものにしていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="7017d-114">In this case, it means we're moving your Skype for Business Online users and settings from one datacenter to another that's closer to you to improve your service.</span></span>
    
- <span data-ttu-id="7017d-115">**待機時間**これは、Microsoft 365 管理センターにアクセスし、設定を変更して、それらの変更を保存するために必要な時間の長さです。</span><span class="sxs-lookup"><span data-stu-id="7017d-115">**Latency** This is amount of time it takes you to access the Microsoft 365 admin center, make a settings change, and then save those changes.</span></span>
    
- <span data-ttu-id="7017d-116">**関連付け ID**これは、先ほど送信したメッセージの一覧に表示されていた可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7017d-116">**Correlation ID** You might have seen this listed in the message you just came from.</span></span> <span data-ttu-id="7017d-117">この情報は、Microsoft サポートエンジニアがエラーのトラブルシューティングを行うために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7017d-117">This information is used by Microsoft support engineers to help you troubleshoot an error.</span></span> <span data-ttu-id="7017d-118">Microsoft サポートに連絡する場合は、関連付け ID の確認を求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7017d-118">If you contact Microsoft support, you might be asked for the Correlation ID.</span></span>
    
<span data-ttu-id="7017d-119">これまでの意味では、Skype for Business Online のすべてのユーザーとサービス設定を、お客様により近い場所に移動するプロセスを進めています。</span><span class="sxs-lookup"><span data-stu-id="7017d-119">So what this all means is we're in the process of moving all your Skype for Business Online users and service settings to another location that's closer to you.</span></span> <span data-ttu-id="7017d-120">もっとうまくいきます。</span><span class="sxs-lookup"><span data-stu-id="7017d-120">The closer the better.</span></span> <span data-ttu-id="7017d-121">この短時間の間、Skype for Business Online サービスの品質が向上します。</span><span class="sxs-lookup"><span data-stu-id="7017d-121">The good news is that after this short period of time, your Skype for Business Online service will improve.</span></span>
  
![Microsoft 365 または Office 365 でのサービスの移行](../images/77502071-36fe-4833-a5ff-3b9ca7676542.png)
  
## <a name="what-skype-for-business-online-features-will-still-work"></a><span data-ttu-id="7017d-123">Skype for Business Online の機能について教えてください。</span><span class="sxs-lookup"><span data-stu-id="7017d-123">What Skype for Business Online features will still work?</span></span>

<span data-ttu-id="7017d-124">Skype for Business Online 管理センターにアクセスすることはできませんが、移行中に次の Skype for Business Online の機能は引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="7017d-124">Although you won't be able to access the Skype for Business Online admin center, the following Skype for Business Online features will still work during the migration:</span></span>
  
- <span data-ttu-id="7017d-125">オンライン会議</span><span class="sxs-lookup"><span data-stu-id="7017d-125">Online meetings</span></span>
    
- <span data-ttu-id="7017d-126">プレゼンス情報</span><span class="sxs-lookup"><span data-stu-id="7017d-126">Presence information</span></span>
    
## <a name="can-i-get-other-work-done"></a><span data-ttu-id="7017d-127">他の作業を行うことはできますか?</span><span class="sxs-lookup"><span data-stu-id="7017d-127">Can I get other work done?</span></span>

<span data-ttu-id="7017d-128">もちろん。</span><span class="sxs-lookup"><span data-stu-id="7017d-128">Sure.</span></span> <span data-ttu-id="7017d-129">Skype for Business Online サービスを移行している間も、Microsoft 365 の他の管理センター (たとえば、Microsoft 365 と Exchange 管理センター) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7017d-129">While we're migrating your Skype for Business Online service, you can still use the other admin centers in Microsoft 365 (for example, the Microsoft 365 and Exchange admin centers).</span></span> <span data-ttu-id="7017d-130">ただし、Skype for Business Online 管理センターと共に、移行中に Skype for Business Online リモート PowerShell コマンドレットを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="7017d-130">However, along with the Skype for Business Online admin center, you won't be able to use the Skype for Business Online Remote PowerShell cmdlets during the migration.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="7017d-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="7017d-131">Related topics</span></span>
[<span data-ttu-id="7017d-132">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="7017d-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="7017d-133">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="7017d-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
