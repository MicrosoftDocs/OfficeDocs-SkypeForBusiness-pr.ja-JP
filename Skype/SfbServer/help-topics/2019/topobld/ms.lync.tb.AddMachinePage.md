---
title: サーバーの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
ROBOTS: NOINDEX, NOFOLLOW
description: 既存のサーバープールに新しいサーバーを追加するには、次のいずれかのプールを使います。
ms.openlocfilehash: 005c2e2e63668b7c17ee04d49de88811649fe914
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297738"
---
# <a name="add-server"></a><span data-ttu-id="9d85e-103">サーバーの追加</span><span class="sxs-lookup"><span data-stu-id="9d85e-103">Add Server</span></span>
 
<span data-ttu-id="9d85e-104">既存のサーバープールに新しいサーバーを追加するには、次のいずれかのプールを使います。</span><span class="sxs-lookup"><span data-stu-id="9d85e-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="9d85e-105">Enterprise Edition フロントエンドサーバー</span><span class="sxs-lookup"><span data-stu-id="9d85e-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="9d85e-106">ディレクターサーバー</span><span class="sxs-lookup"><span data-stu-id="9d85e-106">Director server</span></span>
    
- <span data-ttu-id="9d85e-107">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="9d85e-107">Mediation Server</span></span>
    
- <span data-ttu-id="9d85e-108">音声/ビデオ会議サーバー</span><span class="sxs-lookup"><span data-stu-id="9d85e-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="9d85e-109">信頼できるアプリケーションサーバー</span><span class="sxs-lookup"><span data-stu-id="9d85e-109">Trusted Application server</span></span>
    
<span data-ttu-id="9d85e-110">新しい各プールサーバーの要件はそれぞれ異なります。</span><span class="sxs-lookup"><span data-stu-id="9d85e-110">Each of the new pool servers has different requirements.</span></span> <span data-ttu-id="9d85e-111">次のセクションでは、既存のプールに追加するサーバーの種類を特定し、各サーバーの種類に対して定義された情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d85e-111">In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type.</span></span> <span data-ttu-id="9d85e-112">要求された情報を指定して、新しいプールサーバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="9d85e-112">You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="9d85e-113">**Enterprise Edition フロントエンドサーバー**</span><span class="sxs-lookup"><span data-stu-id="9d85e-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="9d85e-114">新しいサーバーの完全修飾ドメイン名 (FQDN) (ドメインネームシステム (DNS) で定義されているもの)。</span><span class="sxs-lookup"><span data-stu-id="9d85e-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="9d85e-115">[**構成さ**れているすべての ip アドレスを使用する] を選択します。これは、コンピューター上で定義された ip アドレスを使用できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="9d85e-115">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="9d85e-116">または、[**サービスの利用制限を選択した IP アドレスに制限**] を選択して、新しいサーバーで特定のアドレスを入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="9d85e-116">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="9d85e-117">入力された IP アドレスは、ホストされているサービスに応答する唯一の IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="9d85e-117">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="9d85e-118">仲介サーバーがフロントエンドサーバーに併置されているときに、 **PSTN IP アドレス**を定義します。</span><span class="sxs-lookup"><span data-stu-id="9d85e-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="9d85e-119">[ **Ipv6 を有効**にする] を選択して、このサーバーの ipv6 を有効にします。</span><span class="sxs-lookup"><span data-stu-id="9d85e-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="9d85e-120">**ディレクターサーバー**</span><span class="sxs-lookup"><span data-stu-id="9d85e-120">**Director server**</span></span>
  
- <span data-ttu-id="9d85e-121">DNS で定義されている新しいサーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="9d85e-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="9d85e-122">[**構成されているすべての ip アドレスを使用**する] を選択します。これは、コンピューター上で定義された ip アドレスが使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="9d85e-122">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used.</span></span> <span data-ttu-id="9d85e-123">または、[**サービス使用量を選択した ip アドレスに制限する**] を選択し、新しいサーバーに特定の ip アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="9d85e-123">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server.</span></span> <span data-ttu-id="9d85e-124">入力された IP アドレスは、ホストされているサービスに応答する唯一の IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="9d85e-124">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="9d85e-125">**仲介サーバー**</span><span class="sxs-lookup"><span data-stu-id="9d85e-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="9d85e-126">DNS で定義されている新しいサーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="9d85e-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="9d85e-127">[**構成さ**れているすべての ip アドレスを使用する] を選択します。これは、コンピューター上で定義された ip アドレスを使用できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="9d85e-127">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="9d85e-128">または、[**サービスの利用制限を選択した IP アドレス] まで**選択して、新しいサーバーの ip アドレスをプライマリ IP アドレスとして入力し、公衆交換電話網 (PSTN) ip アドレスの ip アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="9d85e-128">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address.</span></span> <span data-ttu-id="9d85e-129">入力された IP アドレスは、指定されたサービスに対して応答する唯一の IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="9d85e-129">The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9d85e-130">仲介サーバーの場合、プライマリ IP アドレスと PSTN IP アドレスに入力された IP アドレスは、既定で同じです。</span><span class="sxs-lookup"><span data-stu-id="9d85e-130">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default.</span></span> <span data-ttu-id="9d85e-131">専用のネットワークインターフェイスを使用している場合、または同一のネットワークインターフェイスで IP アドレスを個別に使用している場合は、IP アドレスを個別に定義できます。</span><span class="sxs-lookup"><span data-stu-id="9d85e-131">The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface.</span></span> <span data-ttu-id="9d85e-132">ローカルネットワーク接続用と PSTN 接続用の2つのネットワークインターフェイスがある場合は、異なる IP アドレスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d85e-132">If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="9d85e-133">**音声/ビデオ会議サーバー**</span><span class="sxs-lookup"><span data-stu-id="9d85e-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="9d85e-134">DNS で定義されている新しいサーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="9d85e-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="9d85e-135">[**構成さ**れているすべての ip アドレスを使用する] を選択します。これは、コンピューター上で定義された ip アドレスを使用できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="9d85e-135">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="9d85e-136">または、[**サービスの利用制限を選択した IP アドレスに制限**] を選択して、新しいサーバーで特定のアドレスを入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="9d85e-136">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="9d85e-137">入力された IP アドレスは、ホストされているサービスに応答する唯一の IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="9d85e-137">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="9d85e-138">**信頼できるアプリケーションサーバー**</span><span class="sxs-lookup"><span data-stu-id="9d85e-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="9d85e-139">DNS で定義されている新しいサーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="9d85e-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

