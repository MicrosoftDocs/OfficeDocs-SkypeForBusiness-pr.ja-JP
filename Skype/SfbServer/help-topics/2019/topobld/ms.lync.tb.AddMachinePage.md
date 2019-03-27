---
title: サーバーの追加
ms.reviewer: ''
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
ms.openlocfilehash: 5db99c8cdd2a08722a27a9da437911dcf573d5bf
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875617"
---
# <a name="add-server"></a><span data-ttu-id="5fed9-103">サーバーの追加</span><span class="sxs-lookup"><span data-stu-id="5fed9-103">Add Server</span></span>
 
<span data-ttu-id="5fed9-104">プールは、次のいずれかの場所、サーバーの既存のプールに新しいサーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="5fed9-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="5fed9-105">エンタープライズ エディションのフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="5fed9-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="5fed9-106">ディレクター サーバー</span><span class="sxs-lookup"><span data-stu-id="5fed9-106">Director server</span></span>
    
- <span data-ttu-id="5fed9-107">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="5fed9-107">Mediation Server</span></span>
    
- <span data-ttu-id="5fed9-108">オーディオ/ビデオ会議サーバー</span><span class="sxs-lookup"><span data-stu-id="5fed9-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="5fed9-109">信頼されたアプリケーション サーバー</span><span class="sxs-lookup"><span data-stu-id="5fed9-109">Trusted Application server</span></span>
    
<span data-ttu-id="5fed9-110">各プールの新しいサーバーのさまざまな要件があります。</span><span class="sxs-lookup"><span data-stu-id="5fed9-110">Each of the new pool servers has different requirements.</span></span> <span data-ttu-id="5fed9-111">次のセクションで既存のプールに追加するサーバーの種類を見つけてサーバー タイプごとに定義されている要求された情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="5fed9-111">In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type.</span></span> <span data-ttu-id="5fed9-112">新しいプールのサーバーを定義するのには要求された情報を入力するとします。</span><span class="sxs-lookup"><span data-stu-id="5fed9-112">You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="5fed9-113">**エンタープライズ エディションのフロント エンド サーバー**</span><span class="sxs-lookup"><span data-stu-id="5fed9-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="5fed9-114">新しいサーバーのドメイン名 (FQDN) の完全修飾ドメイン ネーム システム (DNS) で定義されているようです。</span><span class="sxs-lookup"><span data-stu-id="5fed9-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="5fed9-115">**構成されているすべての IP アドレスを使用して**コンピューター上で定義されている任意の IP アドレスを使用できることを意味するを選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed9-115">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="5fed9-116">または、**選択した IP アドレスを使用するサービスの制限**を選択し、新しいサーバー上で特定のアドレスを入力できます。</span><span class="sxs-lookup"><span data-stu-id="5fed9-116">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="5fed9-117">入力した IP アドレスは、ホストされるサービスの応答が唯一の IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="5fed9-117">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="5fed9-118">仲介サーバーがフロント エンド サーバーに併設されている場合は、 **PSTN の IP アドレス**を定義します。</span><span class="sxs-lookup"><span data-stu-id="5fed9-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="5fed9-119">このサーバーの IPv6 を有効にするのには、 **IPv6 を有効にする**を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed9-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="5fed9-120">**ディレクター サーバー**</span><span class="sxs-lookup"><span data-stu-id="5fed9-120">**Director server**</span></span>
  
- <span data-ttu-id="5fed9-121">新しいサーバーの FQDN が DNS で定義されています。</span><span class="sxs-lookup"><span data-stu-id="5fed9-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="5fed9-122">**構成されているすべての IP アドレスを使用して**コンピューター上で定義されている任意の IP アドレスを使用することを意味するを選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed9-122">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used.</span></span> <span data-ttu-id="5fed9-123">または、**選択した IP アドレスを使用するサービスの制限**を選択し、新しいサーバー上の特定の IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="5fed9-123">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server.</span></span> <span data-ttu-id="5fed9-124">入力した IP アドレスは、ホストされるサービスの応答が唯一の IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="5fed9-124">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="5fed9-125">**仲介サーバー**</span><span class="sxs-lookup"><span data-stu-id="5fed9-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="5fed9-126">新しいサーバーの FQDN が DNS で定義されています。</span><span class="sxs-lookup"><span data-stu-id="5fed9-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="5fed9-127">**構成されているすべての IP アドレスを使用して**コンピューター上で定義されている任意の IP アドレスを使用できることを意味するを選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed9-127">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="5fed9-128">または、**選択した IP アドレスを使用するサービスの制限**と、プライマリ IP アドレスと、新しいサーバー上で特定の IP アドレスを入力および公衆交換電話網 (PSTN) の IP アドレスの IP アドレス入力」ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed9-128">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address.</span></span> <span data-ttu-id="5fed9-129">入力した IP アドレスは、指定されたサービスの応答が唯一の IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="5fed9-129">The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5fed9-130">仲介サーバーのプライマリ IP アドレスと PSTN の IP アドレスを入力した IP アドレスとは、既定では同じです。</span><span class="sxs-lookup"><span data-stu-id="5fed9-130">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default.</span></span> <span data-ttu-id="5fed9-131">IP アドレスは、同一のネットワーク インターフェイス上の専用ネットワーク ・ インタ フェースまたは別の IP アドレスを使用している場合、個別に定義できます。</span><span class="sxs-lookup"><span data-stu-id="5fed9-131">The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface.</span></span> <span data-ttu-id="5fed9-132">ローカル ネットワーク接続用と PSTN 接続用の 2 つのネットワーク ・ インタ フェースがある場合は、別の IP アドレスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fed9-132">If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="5fed9-133">**オーディオ/ビデオ会議サーバー**</span><span class="sxs-lookup"><span data-stu-id="5fed9-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="5fed9-134">新しいサーバーの FQDN が DNS で定義されています。</span><span class="sxs-lookup"><span data-stu-id="5fed9-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="5fed9-135">**構成されているすべての IP アドレスを使用して**コンピューター上で定義されている任意の IP アドレスを使用できることを意味するを選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed9-135">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="5fed9-136">または、**選択した IP アドレスを使用するサービスの制限**を選択し、新しいサーバー上で特定のアドレスを入力できます。</span><span class="sxs-lookup"><span data-stu-id="5fed9-136">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="5fed9-137">入力した IP アドレスは、ホストされるサービスの応答が唯一の IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="5fed9-137">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="5fed9-138">**信頼されたアプリケーション サーバー**</span><span class="sxs-lookup"><span data-stu-id="5fed9-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="5fed9-139">新しいサーバーの FQDN が DNS で定義されています。</span><span class="sxs-lookup"><span data-stu-id="5fed9-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

