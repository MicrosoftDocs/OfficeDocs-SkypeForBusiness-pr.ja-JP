---
title: サーバーを追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
ROBOTS: NOINDEX, NOFOLLOW
description: サーバーの既存のプール (プールは以下のいずれか) に新しいサーバーを追加するには、以下の操作を行います。
ms.openlocfilehash: 853ed95ab456bcbbbeffec493effbe86d8894327
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811557"
---
# <a name="add-server"></a><span data-ttu-id="62d3e-103">サーバーの追加</span><span class="sxs-lookup"><span data-stu-id="62d3e-103">Add Server</span></span>
 
<span data-ttu-id="62d3e-104">サーバーの既存のプール (プールは以下のいずれか) に新しいサーバーを追加するには、以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="62d3e-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="62d3e-105">Enterprise Edition フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="62d3e-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="62d3e-106">ディレクター サーバー</span><span class="sxs-lookup"><span data-stu-id="62d3e-106">Director server</span></span>
    
- <span data-ttu-id="62d3e-107">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="62d3e-107">Mediation Server</span></span>
    
- <span data-ttu-id="62d3e-108">音声ビデオ会議サーバー</span><span class="sxs-lookup"><span data-stu-id="62d3e-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="62d3e-109">信頼済みアプリケーション サーバー</span><span class="sxs-lookup"><span data-stu-id="62d3e-109">Trusted Application server</span></span>
    
<span data-ttu-id="62d3e-p101">新しいプール サーバーには、それぞれに異なる要件があります。以下のセクションでは、既存のプールに追加するサーバーの種類を示し、定義するときに要求される情報をサーバーの種類別に提供します。要求される情報を入力して新しいプール サーバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="62d3e-p101">Each of the new pool servers has different requirements. In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type. You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="62d3e-113">**Enterprise Edition フロントエンド サーバー**</span><span class="sxs-lookup"><span data-stu-id="62d3e-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="62d3e-114">ドメイン ネーム システム (DNS) で定義するときの新しいサーバーの完全修飾ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="62d3e-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="62d3e-p102">[**すべての構成済み IP アドレスの使用**] をオンにします。これは、コンピューターで定義されているすべての IP アドレスを使用できることを意味します。あるいは、[**サービスでの使用を選択した IP アドレスに制限する**] をオンにし、新しいサーバー上の特定のアドレスを入力することもできます。入力する IP アドレスは、ホストされるサービスで応答する唯一の IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="62d3e-p102">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="62d3e-118">フロントエンド サーバーで仲介サーバーが共存する場合は、[**PSTN の IP アドレス**] を定義します。</span><span class="sxs-lookup"><span data-stu-id="62d3e-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="62d3e-119">[**IPv6 を有効にする**] を選択して、このサーバーに対して IPv6 を有効にします。</span><span class="sxs-lookup"><span data-stu-id="62d3e-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="62d3e-120">**ディレクター サーバー**</span><span class="sxs-lookup"><span data-stu-id="62d3e-120">**Director server**</span></span>
  
- <span data-ttu-id="62d3e-121">DNS で定義されている新しいサーバーの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="62d3e-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="62d3e-p103">[**すべての構成済み IP アドレスの使用**] をオンにします。これは、コンピューターで定義されているすべての IP アドレスが使用されることを意味します。あるいは、[**サービスでの使用を選択した IP アドレスに制限する**] をオンにし、新しいサーバー上の特定の IP アドレスを入力します。入力する IP アドレスは、ホストされるサービスで応答する唯一の IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="62d3e-p103">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used. Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="62d3e-125">**仲介サーバー**</span><span class="sxs-lookup"><span data-stu-id="62d3e-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="62d3e-126">DNS で定義されている新しいサーバーの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="62d3e-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="62d3e-p104">[**すべての構成済み IP アドレスの使用**] をオンにします。これは、コンピューターで定義されているすべての IP アドレスを使用できることを意味します。あるいは、[**サービスでの使用を選択した IP アドレスに制限する**] をオンにして新しいサーバー上の特定の IP アドレスをプライマリ IP アドレスとして入力し、公衆交換電話網 (PSTN) IP アドレスとしての IP アドレスを入力します。入力する IP アドレスは、指定されたサービスで応答する唯一の IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="62d3e-p104">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address. The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="62d3e-p105">仲介サーバーの場合、既定では、プライマリ IP アドレスとして入力した IP アドレスと PSTN IP アドレスは同じです。各 IP アドレスは、専用ネットワーク インターフェイスを使用するか、または同じネットワーク インターフェイスで別々の IP アドレスを使用する場合には、別々に定義できます。ローカル ネットワーク接続用に 1 つと、PSTN 接続用に 1 つの、合わせて 2 つのネットワーク インターフェイスがある場合は、異なる IP アドレスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="62d3e-p105">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default. The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface. If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="62d3e-133">**音声ビデオ会議サーバー**</span><span class="sxs-lookup"><span data-stu-id="62d3e-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="62d3e-134">DNS で定義されている新しいサーバーの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="62d3e-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="62d3e-p106">[**すべての構成済み IP アドレスの使用**] をオンにします。これは、コンピューターで定義されているすべての IP アドレスを使用できることを意味します。あるいは、[**サービスでの使用を選択した IP アドレスに制限する**] をオンにし、新しいサーバー上の特定のアドレスを入力することもできます。入力する IP アドレスは、ホストされるサービスで応答する唯一の IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="62d3e-p106">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="62d3e-138">**信頼済みアプリケーション サーバー**</span><span class="sxs-lookup"><span data-stu-id="62d3e-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="62d3e-139">DNS で定義されている新しいサーバーの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="62d3e-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

