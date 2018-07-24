---
title: サーバーを追加します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
ROBOTS: NOINDEX, NOFOLLOW
description: プールは、次のいずれかの場所、サーバーの既存のプールに新しいサーバーを追加します。
ms.openlocfilehash: 57f791910ea81a552c58d94c865938c3c1f82e61
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21064886"
---
# <a name="add-server"></a><span data-ttu-id="1beb8-103">サーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="1beb8-103">Add Server</span></span>
 
<span data-ttu-id="1beb8-104">プールは、次のいずれかの場所、サーバーの既存のプールに新しいサーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="1beb8-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="1beb8-105">エンタープライズ エディションのフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1beb8-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="1beb8-106">ディレクター サーバー</span><span class="sxs-lookup"><span data-stu-id="1beb8-106">Director server</span></span>
    
- <span data-ttu-id="1beb8-107">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="1beb8-107">Mediation Server</span></span>
    
- <span data-ttu-id="1beb8-108">オーディオ/ビデオ会議サーバー</span><span class="sxs-lookup"><span data-stu-id="1beb8-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="1beb8-109">信頼されたアプリケーション サーバー</span><span class="sxs-lookup"><span data-stu-id="1beb8-109">Trusted Application server</span></span>
    
<span data-ttu-id="1beb8-110">各プールの新しいサーバーのさまざまな要件があります。</span><span class="sxs-lookup"><span data-stu-id="1beb8-110">Each of the new pool servers has different requirements.</span></span> <span data-ttu-id="1beb8-111">次のセクションで既存のプールに追加するサーバーの種類を見つけてサーバー タイプごとに定義されている要求された情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="1beb8-111">In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type.</span></span> <span data-ttu-id="1beb8-112">新しいプールのサーバーを定義するのには要求された情報を入力するとします。</span><span class="sxs-lookup"><span data-stu-id="1beb8-112">You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="1beb8-113">**エンタープライズ エディションのフロント エンド サーバー**</span><span class="sxs-lookup"><span data-stu-id="1beb8-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="1beb8-114">新しいサーバーのドメイン名 (FQDN) の完全修飾ドメイン ネーム システム (DNS) で定義されているようです。</span><span class="sxs-lookup"><span data-stu-id="1beb8-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="1beb8-115">**構成されているすべての IP アドレスを使用して**コンピューター上で定義されている任意の IP アドレスを使用できることを意味するを選択します。</span><span class="sxs-lookup"><span data-stu-id="1beb8-115">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="1beb8-116">または、**選択した IP アドレスを使用するサービスの制限**を選択し、新しいサーバー上で特定のアドレスを入力できます。</span><span class="sxs-lookup"><span data-stu-id="1beb8-116">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="1beb8-117">入力した IP アドレスは、ホストされるサービスの応答が唯一の IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="1beb8-117">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="1beb8-118">仲介サーバーがフロント エンド サーバーに併設されている場合は、 **PSTN の IP アドレス**を定義します。</span><span class="sxs-lookup"><span data-stu-id="1beb8-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="1beb8-119">このサーバーの IPv6 を有効にするのには、 **IPv6 を有効にする**を選択します。</span><span class="sxs-lookup"><span data-stu-id="1beb8-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
 <span data-ttu-id="1beb8-120">**ディレクター サーバー**</span><span class="sxs-lookup"><span data-stu-id="1beb8-120">**Director server**</span></span>
  
- <span data-ttu-id="1beb8-121">新しいサーバーの FQDN が DNS で定義されています。</span><span class="sxs-lookup"><span data-stu-id="1beb8-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="1beb8-122">**構成されているすべての IP アドレスを使用して**コンピューター上で定義されている任意の IP アドレスを使用することを意味するを選択します。</span><span class="sxs-lookup"><span data-stu-id="1beb8-122">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used.</span></span> <span data-ttu-id="1beb8-123">または、**選択した IP アドレスを使用するサービスの制限**を選択し、新しいサーバー上の特定の IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1beb8-123">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server.</span></span> <span data-ttu-id="1beb8-124">入力した IP アドレスは、ホストされるサービスの応答が唯一の IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="1beb8-124">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
 <span data-ttu-id="1beb8-125">**仲介サーバー**</span><span class="sxs-lookup"><span data-stu-id="1beb8-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="1beb8-126">新しいサーバーの FQDN が DNS で定義されています。</span><span class="sxs-lookup"><span data-stu-id="1beb8-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="1beb8-127">**構成されているすべての IP アドレスを使用して**コンピューター上で定義されている任意の IP アドレスを使用できることを意味するを選択します。</span><span class="sxs-lookup"><span data-stu-id="1beb8-127">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="1beb8-128">または、**選択した IP アドレスを使用するサービスの制限**と、プライマリ IP アドレスと、新しいサーバー上で特定の IP アドレスを入力および公衆交換電話網 (PSTN) の IP アドレスの IP アドレス入力」ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="1beb8-128">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address.</span></span> <span data-ttu-id="1beb8-129">入力した IP アドレスは、指定されたサービスの応答が唯一の IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="1beb8-129">The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1beb8-130">仲介サーバーのプライマリ IP アドレスと PSTN の IP アドレスを入力した IP アドレスとは、既定では同じです。</span><span class="sxs-lookup"><span data-stu-id="1beb8-130">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default.</span></span> <span data-ttu-id="1beb8-131">IP アドレスは、同一のネットワーク インターフェイス上の専用ネットワーク ・ インタ フェースまたは別の IP アドレスを使用している場合、個別に定義できます。</span><span class="sxs-lookup"><span data-stu-id="1beb8-131">The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface.</span></span> <span data-ttu-id="1beb8-132">ローカル ネットワーク接続用と PSTN 接続用の 2 つのネットワーク ・ インタ フェースがある場合は、別の IP アドレスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1beb8-132">If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
 <span data-ttu-id="1beb8-133">**オーディオ/ビデオ会議サーバー**</span><span class="sxs-lookup"><span data-stu-id="1beb8-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="1beb8-134">新しいサーバーの FQDN が DNS で定義されています。</span><span class="sxs-lookup"><span data-stu-id="1beb8-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="1beb8-135">**構成されているすべての IP アドレスを使用して**コンピューター上で定義されている任意の IP アドレスを使用できることを意味するを選択します。</span><span class="sxs-lookup"><span data-stu-id="1beb8-135">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="1beb8-136">または、**選択した IP アドレスを使用するサービスの制限**を選択し、新しいサーバー上で特定のアドレスを入力できます。</span><span class="sxs-lookup"><span data-stu-id="1beb8-136">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="1beb8-137">入力した IP アドレスは、ホストされるサービスの応答が唯一の IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="1beb8-137">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
 <span data-ttu-id="1beb8-138">**信頼されたアプリケーション サーバー**</span><span class="sxs-lookup"><span data-stu-id="1beb8-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="1beb8-139">新しいサーバーの FQDN が DNS で定義されています。</span><span class="sxs-lookup"><span data-stu-id="1beb8-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

