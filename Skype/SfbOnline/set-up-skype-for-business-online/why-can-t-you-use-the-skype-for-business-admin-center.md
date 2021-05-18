---
title: 現在、Skype for Business Online 管理センターを使用できない理由
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
description: 'サービスを別の Microsoft データ センターに移行するときに、Skype for Business 管理センターで使用できる機能と使用できない機能について説明します。 '
ms.openlocfilehash: 725a60be96a2d61bcec6367e1a0a33f2bc5dcee6
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238918"
---
# <a name="why-cant-i-use-the-skype-for-business-online-admin-center-right-now"></a><span data-ttu-id="aed73-103">現在、Skype for Business Online 管理センターを使用できない理由</span><span class="sxs-lookup"><span data-stu-id="aed73-103">Why can't I use the Skype for Business Online admin center right now?</span></span>

<span data-ttu-id="aed73-104">[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]?</span><span class="sxs-lookup"><span data-stu-id="aed73-104">[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]?</span></span>

<span data-ttu-id="aed73-105">作業を終えられないと、いら立ちを感じさせられないので、ここで何が起こっているのか、なぜ待つ価値があるのかを説明します。</span><span class="sxs-lookup"><span data-stu-id="aed73-105">We know it's frustrating when you can't get your work done, so we're going to explain what's happening here and why it'll be worth the wait.</span></span> 
  
<span data-ttu-id="aed73-106">まず、技術的な説明を次に示します。</span><span class="sxs-lookup"><span data-stu-id="aed73-106">First, here's the technical explanation:</span></span>
  
<span data-ttu-id="aed73-107">お客様の Skype for Business Online サービス (つまり、ユーザーと組織の設定) を、お客様に近い別の Microsoft データセンターに移行します。</span><span class="sxs-lookup"><span data-stu-id="aed73-107">We're migrating your Skype for Business Online service (meaning your users and organizational settings) to another Microsoft datacenter that's closer to you.</span></span> <span data-ttu-id="aed73-108">これにより、サービスが改善され、待ち時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="aed73-108">This will improve your service and reduce latency.</span></span> 
  
<span data-ttu-id="aed73-109">技術的な詳細については、「データ移動中と [移動後」を参照してください]( https://go.microsoft.com/fwlink/?LinkId=526418)。</span><span class="sxs-lookup"><span data-stu-id="aed73-109">For more technical details, see [During and after your data move]( https://go.microsoft.com/fwlink/?LinkId=526418).</span></span>
  
## <a name="ok-so-what-does-that-mean"></a><span data-ttu-id="aed73-110">では、これはどういう意味でしょうか。</span><span class="sxs-lookup"><span data-stu-id="aed73-110">OK, so what does that mean?</span></span>

<span data-ttu-id="aed73-111">最初に、いくつかの用語を分けとしましょう。</span><span class="sxs-lookup"><span data-stu-id="aed73-111">First, let's break down a few terms.</span></span>
  
- <span data-ttu-id="aed73-112">**データ センター** これは、ファイルやメール メッセージなど、Microsoft 365またはOffice 365の情報が格納される物理的な場所です。</span><span class="sxs-lookup"><span data-stu-id="aed73-112">**Data center** This is the physical location where the information from your Microsoft 365 or Office 365 is stored, such as your files and email messages.</span></span> <span data-ttu-id="aed73-113">データ センターとデータ センターのMicrosoft 365をOffice 365する場合は、この記事を[参照してください](https://www.microsoft.com/online/legal/v2/?docid=25)。</span><span class="sxs-lookup"><span data-stu-id="aed73-113">If you really want to dig in to what Microsoft 365 and Office 365 datacenters are, check out[this article](https://www.microsoft.com/online/legal/v2/?docid=25).</span></span>
    
- <span data-ttu-id="aed73-114">**移行** これは "移動" とほとんど同じです。</span><span class="sxs-lookup"><span data-stu-id="aed73-114">**Migrating** This is pretty much the same as "moving."</span></span> <span data-ttu-id="aed73-115">この場合、Skype for Business Online のユーザーと設定を、お客様のサービス向上に近い別のデータセンターに移動します。</span><span class="sxs-lookup"><span data-stu-id="aed73-115">In this case, it means we're moving your Skype for Business Online users and settings from one datacenter to another that's closer to you to improve your service.</span></span>
    
- <span data-ttu-id="aed73-116">**待機時間** この時間は、管理センターから管理センターにアクセスしMicrosoft 365設定を変更してから、それらの変更を保存するのにかかる時間です。</span><span class="sxs-lookup"><span data-stu-id="aed73-116">**Latency** This is amount of time it takes you to access the Microsoft 365 admin center, make a settings change, and then save those changes.</span></span>
    
- <span data-ttu-id="aed73-117">**関連付け ID** 先日のメッセージにこのメッセージが一覧表示されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aed73-117">**Correlation ID** You might have seen this listed in the message you just came from.</span></span> <span data-ttu-id="aed73-118">この情報は、エラーのトラブルシューティングに役立つ Microsoft サポート エンジニアによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="aed73-118">This information is used by Microsoft support engineers to help you troubleshoot an error.</span></span> <span data-ttu-id="aed73-119">Microsoft サポートにお問い合わせの場合は、関連付け ID の入力を求めされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="aed73-119">If you contact Microsoft support, you might be asked for the Correlation ID.</span></span>
    
<span data-ttu-id="aed73-120">つまり、すべての Skype for Business Online ユーザーとサービス設定を、より近い別の場所に移動しています。</span><span class="sxs-lookup"><span data-stu-id="aed73-120">So what this all means is we're in the process of moving all your Skype for Business Online users and service settings to another location that's closer to you.</span></span> <span data-ttu-id="aed73-121">近いほど良くなります。</span><span class="sxs-lookup"><span data-stu-id="aed73-121">The closer the better.</span></span> <span data-ttu-id="aed73-122">この短い期間を過ごした後は、オンライン サービスSkype for Business向上します。</span><span class="sxs-lookup"><span data-stu-id="aed73-122">The good news is that after this short period of time, your Skype for Business Online service will improve.</span></span>
  
![Microsoft 365 または Office 365 でのサービスの移行](../images/77502071-36fe-4833-a5ff-3b9ca7676542.png)
  
## <a name="what-skype-for-business-online-features-will-still-work"></a><span data-ttu-id="aed73-124">オンラインSkype for Business機能は引き続き動作しますか?</span><span class="sxs-lookup"><span data-stu-id="aed73-124">What Skype for Business Online features will still work?</span></span>

<span data-ttu-id="aed73-125">Skype for Business Online 管理センターにアクセスできない場合でも、移行中Skype for Businessオンライン機能は引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="aed73-125">Although you won't be able to access the Skype for Business Online admin center, the following Skype for Business Online features will still work during the migration:</span></span>
  
- <span data-ttu-id="aed73-126">オンライン会議</span><span class="sxs-lookup"><span data-stu-id="aed73-126">Online meetings</span></span>
    
- <span data-ttu-id="aed73-127">プレゼンス情報</span><span class="sxs-lookup"><span data-stu-id="aed73-127">Presence information</span></span>
    
## <a name="can-i-get-other-work-done"></a><span data-ttu-id="aed73-128">他の作業はできますか?</span><span class="sxs-lookup"><span data-stu-id="aed73-128">Can I get other work done?</span></span>

<span data-ttu-id="aed73-129">もちろん。</span><span class="sxs-lookup"><span data-stu-id="aed73-129">Sure.</span></span> <span data-ttu-id="aed73-130">Skype for Business Online サービスの移行中でも、Microsoft 365 の他の管理センター (Microsoft 365 管理センターや Exchange 管理センターなど) を引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="aed73-130">While we're migrating your Skype for Business Online service, you can still use the other admin centers in Microsoft 365 (for example, the Microsoft 365 and Exchange admin centers).</span></span> <span data-ttu-id="aed73-131">ただし、Skype for Business Online 管理センターと共に、移行中に Skype for Business Online リモート PowerShell コマンドレットを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="aed73-131">However, along with the Skype for Business Online admin center, you won't be able to use the Skype for Business Online Remote PowerShell cmdlets during the migration.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="aed73-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="aed73-132">Related topics</span></span>
[<span data-ttu-id="aed73-133">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="aed73-133">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="aed73-134">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="aed73-134">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
